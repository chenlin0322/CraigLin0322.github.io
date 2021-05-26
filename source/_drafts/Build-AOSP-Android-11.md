---
title: Build AOSP Android 11
tags: AOSP
categories: 'Android'
---

Encapsulate about how to build your own Android 11 from AOSP on Ubuntu 18.04

---

#### Envrionment set up

##### OS

It's recommended to use Linux as your compile OS, since MAC is no longer supprted from June 22, 2021, [see here](https://source.android.com/setup/build/requirements). And please make sure that at least 250GB of free disk space on your computer to check out the code and an extra 150 GB to build it.

> If you're developing against the AOSP `master` branch, use Unbuntu 18.04

For me, I use 18.04 Ubuntu. Install requires packages:

> sudo apt-get install git-core gnupg flex bison build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig

##### JDK

The master branch of AOSP come with a prebuilt OpenJDK, so no addition installation of JDK is needed, but for those older version, please check it out on the Official Document and use the required version.

##### Python

Use Python2.7 on your OS if you don't have.

> sudo apt install python2.7 python-pip

----

#### Download AOSP

First and formost, install the **Repo**. Reop unifies Git repositories when necessary, performs uploads to the [Gerrit revision control system](https://android-review.googlesource.com/), and automates parts of the Android development workflow:

```shell
mkdir ~/bin
PATH=~/bin:$PATH

curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
chmod a+x ~/bin/repo
```

Then create a empty directory on your working files, like:

> mkdir DIR
>
> cd DIR

Run `repo init` to get the latest version of Repo with its most recent bug fixes:

```shell
repo init -u https://android.googlesource.com/platform/manifest
```

If you want to specify the version, add the corresponding branch with -b:

```shell
repo init -u https://android.googlesource.com/platform/manifest -b master
```

See the [Source code and tag](https://source.android.com/setup/start/build-numbers#source-code-tags-and-builds). For me, I use the latest Android 11 branch:

```sh
repo init -u https://android.googlesource.com/platform/manifest -b android-11.0.0_r36
```

Then we run `repo sync` to download the AOSP, o speed syncs, pass the `-c` (current branch) and `-jthreadcount` flags:

```sh
repo sync -c -j8
```

It will take 2-3 hours to download the entire codes, it depends on network speed.

AOSP can't be used from pure source code only and requires additional hardware-related proprietary libraries to run, such as for hardware graphics acceleration. Accordingly, you might as well download the related driver version from [this site](https://developers.google.com/android/drivers), please keep in mind that you should download driver which should be same  Build ID as the branch you download on AOSP.

For me, as I use **android-11.0.0_r36**, and my device is Pixel3, so here the drive version I use:

> ```
> https://developers.google.com/android/drivers#crosshatchrq2a.210505.002
> ```



---

#### Build

When the work is done, firstly we extract the proprietary binaries which we had download.

> Each set of binaries comes as a self-extracting script in a compressed archive. Uncompress each archive, run the included self-extracting script from the root of the source tree, then confirm you agree to the terms of the enclosed license agreement. The binaries and their matching makefiles are installed in the `vendor/` hierarchy of the source tree.

All things are considered! Let's begin build our own system, execute commands on AOSP root dir

```shell
#Initialize environment
source build/envsetup.sh
#Choose which target to build with lunch, check target on this site https://source.android.com/setup/build/building#choose-a-target
aosp_blueline-userdebug
# Start build with m
m
```

---

#### Flash to device





