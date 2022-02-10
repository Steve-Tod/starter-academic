---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Use UT box with Commandline"
subtitle: ""
summary: "A short instruction on the usage of UT box with commandline"
authors: []
tags: []
categories: []
date: 2021-04-13T18:02:22+08:00
lastmod: 2021-04-13T18:02:22+08:00
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

# What is UT Box

UTBox is a campus-wide service that allows faculty, staff, and students at the University of Texas at Austin to use Box cloud-based file sharing for business and academic purposes.

UTBox can be accessed via [https://utexas.box.com](https://utexas.box.com) or from [https://utbox.utexas.edu](https://utexas.box.com).

By default, faculty, staff and student users are provisioned accounts with **no quota limits**, althought it only supports a maximum file size of 50 GB for each single file.

# How to use it

## Prerequisite

### lftp

`lftp` is needed. It can be installed simply with `sudo apt-get install lftp`.

### Account

To access Box by FTP, you must create an external password at [Box](https://utexas.box.com).

After login to the web portal of UT box, from the drop-down menu on the top right, click Account Settings.

{{< figure src="menu.png" id="menu" >}}

Then scroll down to the bottom, you'll see an option of create external password (I've already created the password, so I can only change the existing password here). Create an external password.

{{< figure src="passwd.png" id="passwd" >}}

## Connect to ftp server

1. Open a terminal, type in `lftp`.

2. Connect to the server: `open ftp.box.com`

3. Login: `login yourEID@eid.utexas.edu` (replace yourEID with your actual UT EID)

4. Enter the external password you created.

5. Now you should successfully login to the ftp server. You can try `ls` to see if you succeed.

## Upload and download files

`lftp` supports some common shell commands like `ls, cd, mkdir`, you can type in `help` to see all the commands. You can further type `help {command}` to see the instruction for a certain command.

### Upload

`put [OPTS] <lfile> [-o <rfile>]`: Upload `<lfile>` with remote name `<rfile>`. The relative path to `<lfile>` is with respect to the directory where you run `lftp`.

You can type `help put` to see a more detailed instruction.

### Download

`get [OPTS] <rfile> [-o <lfile>]`: Retrieve remote file `<rfile>` and store it to local file `<lfile>`. The relative path to `<lfile>` is with respect to the directory where you run `lftp`.

You can type `help get` to see a more detailed instruction.

