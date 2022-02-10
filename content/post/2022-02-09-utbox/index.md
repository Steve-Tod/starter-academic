---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Mount UT box with Commandline"
subtitle: ""
summary: "A short instruction on how to mount UT box to file system of a linux machine with commandline"
authors: []
tags: []
categories: []
date: 2022-02-09T18:02:22+08:00
lastmod: 2021-02-09T18:02:22+08:00
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

For information about UT Box and how to access Box with `lftp`, please refer to [previous post](https://zhenyujiang.me/post/2021-04-13-utbox/).

# Prerequisite

We need `sudo` to install packages and modify /etc/fstab. After setup, we don't need `sudo` to mount the Box.

# Setup

## Install `davfs2`

```
sudo apt-get install davfs2
```

## Modify /etc/fstab

```
sudo vim /etc/fstab
```

We need to add the following line to this file:

```
https://dav.box.com/dav /path/to/mount/point davfs rw,user,noauto 0 0
```

Remember to reload this file by running `sudo mount -a`.

## Add user to `davfs2` group

```
sudo usermod -aG davfs2 username
```


# Mounting

After setting up, mounting is very simple and does not require `sudo`.

First, login as the `username` and make sure you are in the group `davfs2` by running `groups`.

If `davfs2` is in the results, run `mount /path/to/mount/point`, then input your username and password for Box (refer to [previous post](https://zhenyujiang.me/post/2021-04-13-utbox/) to find more information about these).

Now your Box is mounted to `/path/to/mount/point`!