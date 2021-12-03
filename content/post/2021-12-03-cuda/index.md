---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Install cuda and cudnn without root"
subtitle: ""
summary: "A short instruction on installing cuda and cudnn without root, using cuda 10.1 as an example"
authors: []
tags: []
categories: []
date: 2021-12-03T18:02:22+08:00
lastmod: 2021-12-03T18:02:22+08:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

We use cuda 10.1 and cudnn 8.0.5 as an example.

# Install cuda

First we need to download the local run file of cuda 10.1. We can find that in the [official site](https://developer.nvidia.com/cuda-toolkit-archive), or using the following commands.

```Bash
# 14.04
wget https://developer.download.nvidia.com/compute/cuda/10.1/Prod/local_installers/cuda_10.1.243_418.87.00_linux.run

# 16.04
wget https://developer.download.nvidia.com/compute/cuda/10.1/Prod/local_installers/cuda_10.1.243_418.87.00_linux.run

# 18.04
wget https://developer.download.nvidia.com/compute/cuda/10.1/Prod/local_installers/cuda_10.1.243_418.87.00_linux.run
```

Then we can start the installation, here we install it in `/mnt/data2/cuda-10.1/`

```Bash
bash ./cuda_10.1.243_418.87.00_linux.run --toolkit --toolkitpath=/mnt/data2/cuda-10.1/ --defaultroot=/mnt/data2/cuda-10.1/
```

Mention, during installation, we will need to select what to install, we only need to select CUDA here.

{{< figure src="select.jpeg" id="select" >}}

Installation succeeds, the results are:

```
===========
= Summary =
===========

Driver:   Not Selected
Toolkit:  Installed in /mnt/data2/cuda-10.1/
Samples:  Not Selected

Please make sure that
 -   PATH includes /mnt/data2/cuda-10.1/bin
 -   LD_LIBRARY_PATH includes /mnt/data2/cuda-10.1/lib64, or, add /mnt/data2/cuda-10.1/lib64 to /etc/ld.so.conf and run ldconfig as root

To uninstall the CUDA Toolkit, run cuda-uninstaller in /mnt/data2/cuda-10.1/bin

Please see CUDA_Installation_Guide_Linux.pdf in /mnt/data2/cuda-10.1/doc/pdf for detailed information on setting up CUDA.
***WARNING: Incomplete installation! This installation did not install the CUDA Driver. A driver of version at least 418.00 is required for CUDA 10.1 functionality to work.
To install the driver using this installer, run the following command, replacing <CudaInstaller> with the name of this run file:
    sudo <CudaInstaller>.run --silent --driver

Logfile is /tmp/cuda-installer.log
```

## Modify environment variables

I'm using `zsh`, so I change the variable in `~/.zshrc`. And add the following line to the end of `~/.zshrc`:

```bash
alias cu101='export PATH=/mnt/data2/cuda-10.1/bin:$PATH; export LD_LIBRARY_PATH=/mnt/data2/cuda-10.1/lib64:$LD_LIBRARY_PATH'
```

After `source ~/.zshrc`, we can type `cu101` to change our cuda to the installed one.

We can test with `nvcc --version`. The output should be like:

```
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2019 NVIDIA Corporation
Built on Sun_Jul_28_19:07:16_PDT_2019
Cuda compilation tools, release 10.1, V10.1.243
```

We can see it shows `10.1`, which means our installation is successful.

# Install cudnn

We need to find the cudnn version corresponding to our cuda version. The official download address is [https://developer.nvidia.com/rdp/cudnn-download](https://developer.nvidia.com/rdp/cudnn-download). You need to login to download cudnn. Here we use cuDNN v8.0.5 (November 9th, 2020) for CUDA 10.1.

After downloading cuDNN, we can start installation. First we decompress the file. Then we copy the files into cuda directory.

```Bash
# decompress
tar -xzvf cudnn-10.1-linux-x64-v8.0.5.39.tgz

# copy files to CUDA installation directory
cp cuda/include/cudnn* ~/cuda_10.1/include/
cp cuda/lib64/lib* /mnt/data2/cuda-10.1/lib64/
```

Finally, we add read permission to all users:

```Bash
chmod a+r -R /mnt/data2/cuda-10.1/
```

Most content of the post comes from [this one](https://www.fatalerrors.org/a/installation-of-cuda10.1-and-cudnn-for-non-root-users-of-ubuntu.html).