---
slug: installation-guide-for-macs-with-t2-chip
title: Installation Guide for Macs with T2 chip
authors: [rs2009, noa, asterisk, svgaming]
tags: [install, blend-inst, new-user]
sidebar_position: 2
---

<div class="gap"></div>

![Guide banner](./laptop-banner.svg)

Learn how to install blendOS on your computer through this guide!

## What you'll need

* A minimum of 25 GBs of storage.
* A spare USB drive, with a minimum size of 4GBs.

<!--truncate-->

## Installation

You can skip to a particular step from the outline on the right, if you're on a computer.

### Step 1: Download the latest blendOS ISO file

:::tip

If you're coming from Windows or macOS, it's recommended that you download the [**KDE Plasma**](https://kde.org/plasma-desktop/) edition of blendOS. It is extremely intuitive, and has a similar workflow to other operating systems.


However, if you prefer a functional default layout and are open to something new, the [**GNOME**](https://www.gnome.org/) edition may be for you.
:::

<div class="gap"></div>

:::danger

**Warning about downloads:**

The links below are the only certified places to get the ISO, **DO NOT DOWNLOAD IT FROM ANYWHERE ELSE!**
:::
<div class="gap"></div>

1. KDE Plasma Edition:
    * Coming soon!

2. GNOME Edition:
    * [Download from GitHub](https://github.com/NoaHimesaka1873/blendos-gnome-t2/releases/latest)
    * [Download from YuruMirror](https://mirror.funami.tech/blendos/iso/blendOS-2023.04.22-x86_64-gnome.iso)

### Step 2: Download balenaEtcher

In this guide, we will be using balenaEtcher to burn the ISO file to the USB drive.

Regardless of whether you're currently using Linux, macOS or Windows, you can download and install balenaEtcher from [here](https://www.balena.io/etcher).

![balenaEtcher screenshot](./etcher-1.png)

### Step 3: Burn the ISO to your USB drive

:::danger

Make sure to select the correct USB drive, as balenaEtcher will **erase** ALL THE FILES on the drive.

:::

<div class="gap"></div>

Click on **Flash from file**, and select the ISO file you downloaded earlier. You can then select the USB drive you would like to flash the ISO drive to. After
selecting the drive, you can click on **Flash** to flash/burn the ISO to the USB drive.



:::info

The computer/Mac you used to flash the ISO file to the USB drive may be the same as the Mac you want to install blendOS.

:::

<div class="gap"></div>

### Step 4-ish: Disabling Secure Boot (do this first)

Turn on your Mac, then press and hold <kbd>⌘</kbd>-<kbd>R</kbd> immediately after you see the Apple logo. Your Mac starts up from macOS Recovery.

When you're asked to select a user you know the password for, select the user, click *Next*, then enter their administrator password. 

When you see the *macOS utilities* window, choose *Utilities* > *Startup Security Utility* from the menu bar.

When you're asked to authenticate, click *Enter macOS Password*, then choose an administrator account and enter its password.

When you see the *Startup Security Utility* windows, choose *No Security* option. You can then now reboot by choosing *Apple menu* > *Restart*.

:::info

**What did I just turn off?**

**Secure Boot** is a system implemented by Apple which makes it so your computer can only boot *signed* EFI files. 

The ones in blendOS are not signed by Apple nor Microsoft so you must turn this off in order to proceed.
:::

### Step 4: Boot from the USB drive

Insert the USB drive into the computer that you wish to install blendOS to, and power it off. After a few seconds, power it on and hold <kbd>⌥</kbd> until you arrive at your Mac's boot menu.

Once at the boot menu, select the USB drive you flashed blendOS to. You will be greeted by another menu, where you can press <kbd>Enter</kbd> to proceed with booting the live installation media.

:::info

**The menu didn't load!**

[Learn to read.](#step-4-ish-disabling-secure-boot-do-this-first)


Make sure you do step 4-ish even if it just shows a black screen or boots into another OS.
:::
### Step 5: Opening the Installer

:::info

You may see some flashing text come up during boot, it's normal! (Just a Linux thing)

:::

You should arrive at the **desktop**, which should look like this:

#### GNOME:

![blend-i-g](./blend-i-g.png)


#### KDE:

![blend-i-k](./blend-i-k.png)

<div class="gap"></div>

The **blendOS Installer** should pop up. If it doesn't, open it from the **Application Menu** (press the Windows key) and type "installer":
<div class="gap"></div>

![gnome-search](./gnome-search.png)

![kde-search](./kde-search.png)
<div class="gap"></div>
<div class="gap"></div>

### Step 5 Extra: Copying Wi-Fi firmware over to blendOS live installer

Your Mac needs Wi-Fi firmware for Wi-Fi. Sadly, this firmware is copyrighted so you manually have to copy them over by yourself.

Fortunately, there is a [guide](https://wiki.t2linux.org/guides/wifi-bluetooth/) on T2Linux wiki, so just follow this.

### Step 6: Running the installer

:::info

Before you run the installer, make sure you are connected to the internet.

:::

Click **Start** in the installer to begin the install process.

![blend-install-1](./blend-installer-1.png)

**1.** You'll first be asked to select a keyboard layout:

![blend-install-2](./blend-installer-2.png)
<div class="gap"></div>

Click **Search** to choose a keyboard layout (even though it says timezone):

![blend-install-2a](./blend-installer-2-sub.png)

**2.** After choosing your keyboard layout, select your **timezone**:

![blend-install-3](./blend-installer-3.png)
<div class="gap"></div>

Hit **Search** to see timezone options:

![blend-install-3a](./blend-installer-3-sub.png)
<div class="gap"></div>

**3.** After you set your region, it's time to set your **locale**:

:::info
**WHAT IS A LOCALE?**

A locale is basically the thing that the system checks to set your currency, time/date layout (dd/mm/yyyy or mm/dd/yyyy) and language.

It also sets your text encoding (UTF-8 is the main one, you need at least one UTF-8 locale)

they're typed like this: `<lang>_<country_code>.<text_encoding>` (ex. `en_US.UTF8`)
:::
<div class="gap"></div>

![blend-install-4](./blend-installer-4.png)
<div class="gap"></div>

Hit **Search**, then choose a locale, and tick **Use as main locale** (the circle) then double click the locale name or else install will not proceed:

![blend-install-4a](./blend-installer-4-sub.png)
<div class="gap"></div>

**4.** Make your **user account**:

![blend-user](./blend-user.png)
<div class="gap"></div>



**5.** Next, choose the disk you'd like to wipe and partition, or choose [**Manual Partitioning**](#appendices):

:::danger

**WARNING!!**

THIS WILL ERASE ALL DATA ON THE SELECTED DISK!!
:::

![blend-part](./blend-part.png)
<div class="gap"></div>

**Manual Partitioning** (consult [Appendix A](#appendicies) for how to do this):

![blend-part-sub](./blend-part-sub.png)
<div class="gap"></div>

**6.** Then, check that everything is good in the **Summary**:

![blend-summary](./blend-summary.png)
<div class="gap"></div>

Then, hit **Next** and wait for the installer to finish:

![blend-install-8](./blend-installer-8.png)
<div class="gap"></div>

Once the installer finishes, you'll be greeted with an option to reboot:

![blend-finish](./blend-installer-9.png)
<div class="gap"></div>

## Post-Install

### Step 1: Copying Wi-Fi and Bluetooth (on some models) over to your system

Once you reboot, you should boot off of your **hard disk**.

Now follow the [guide](https://wiki.t2linux.org/guides/wifi-bluetooth/) again, but you can skip *On macOS* part if you still have your files. 

*Wait, didn't I copy the firmware over? Why should I do this again?*

Because the firmware you copied was for the live system. Those files don't carry on to your installation.

### Step 2: Updating the system


Open the **Terminal** again.

**GNOME:**

![blend-gnome](./blend-postinst-term-1-gnome.png)
<div class="gap"></div>

**KDE:**

![blend-kde](./blend-postinst-term-1-plasma.png)

Then, type `sudo pacman -Syu` and enter your user password at the prompt.

**GNOME:**

![blend-g-1](./blend-postinst-term-2-gnome.png)

**KDE:**

![blend-k-1](./blend-postinst-term-2-plasma.png)

`pacman` will show the list of avalible upgrades, hit <kbd>y</kbd>:

**GNOME:**

![blend-g-2](./blend-postinst-term-3-gnome.png)
<div class="gap"></div>

**KDE:**

![blend-k-2](./blend-postinst-term-3-plasma.png)
<div class="gap"></div>

It should start upgrading:

![blend-g-3](./blend-postinst-term-4-gnome.png)
<div class="gap"></div>

![blend-k-3](./blend-postinst-term-4-plasma.png)

### Step 3: Installing `linux-xanmod-t2` for Waydroid support

Open the **terminal** again, and type `sudo pacman -S linux-xanmod-t2 linux-xanmod-t2-headers` (hit <kbd>y</kbd> at the prompt)

![xanmod1](./blend-xanmod-1.png)

Then, run: `sudo grub-mkconfig -o /boot/grub/grub.cfg` to update **GRUB** (the **GR**and **U**nified **B**ootloader)

![xanmod2](./blend-xanmod-2.png)

:::tip

This is the equivalent of `update-grub` on other distros. You can install it into the host (you have to install it to the host) with `sudo pacman -S update-grub` (if it's not found there try the AUR).

:::

After both packages have installed, **reboot**. At the "Choose Boot Option" menu, choose `Advanced Options for blendOS`, then `blendos - linux-xanmod-t2 6.1` (or similar).

![xanmod3](./blend-xanmod-3.png)
<div class="gap"></div>

![xanmod4](./blend-xanmod-4.png)

:::danger

**MAKE SURE YOU ARE IN THE XANMOD KERNEL BEFORE PROCEEDING!!**

You don't want to remove the runnning kernel. To check if you are using `linux-xanmod-t2`, run the following: `uname -a | grep "xanmod"`

**With Xanmod:**

![xanmod5](./blend-xanmod-5.png)

**Without Xanmod:**

![xanmod6](./blend-xanmod-6.png)

:::

Once you're back in the OS, remove the Linux kernel `sudo pacman -Rcns linux-t2 linux-t2-headers` (hit <kbd>y</kbd> at all prompts). 

![xanmod7](./blend-xanmod-7.png)

Then, run: `sudo grub-mkconfig -o /boot/grub/grub.cfg` and update GRUB again.

![xanmod2a](./blend-xanmod-2.png)

#### You're done!

### Step 3: [Containers](/guides/container-guide)

Start reading the [Container management guide](/guides/container-guide)

## Appendices

<details>
<summary>Appendix A: Manual Partitioning (UEFI)</summary>

<!-- No headers in dropdowns -->
**How to manually partition on a UEFI system:**

:::danger

If you are using VirtualBox or VMWare (or any legacy BIOS system/hypervisor) this guide is not for you, you're on your own.

:::

1. In the installer, choose **Manual Partitioning**, then **Open GParted**:
![blend-inst-p](./blend-installer-mpart-1.png)

Now you should see something like this (but with your partitions):

Choose the disk you'd like to use in the upper right.

:::danger

**MAKE SURE YOU CHOOSE THE RIGHT DISK!!**

If you do not choose the correct disk, you may do unwanted damage.

The install livecd will also be shown here (as the last disk, usually `/dev/sdb` or `/dev/sdc`, it has an ISO partition and an EFI partition.)

Do not format the livecd.
:::

![blend-inst-2](./blend-installer-mpart-2.png)

2. If you wish to wipe your drive go to `Device > Create Partition Table`:
![blend-inst-3](./blend-installer-mpart-3.png)

:::danger

------------------ **WARNING!!** ---------------------

**THIS WILL WIPE ALL DATA AND PARTITIONS ON YOUR DRIVE!**

:::

3. For the partition table choose **GPT** (you *do* have a UEFI system, right?) (most PCs have UEFI)




![blend-inst-m-4](./blend-installer-mpart-4.png)

1. Make a new **EFI** partition (`Partition > New` or clicking the `New` icon on the top bar):
![blend-inst-m-5](./blend-installer-mpart-5.png)

In the box, set the `New Size` to 512 and drag the partition to the left side.

Set `File System` to fat32, `Label` it what you want, and hit `Add`.

:::tip

**Changes are not saved in GParted until you hit apply**, so you can tweak all this to your liking.

:::

You should now see this:

![blend-m-7](./blend-installer-mpart-7.png)

The box on the bottom shows **pending changes**, so you can see what you've done.

**NOTE:** The following step is optional, open the dropdown below to see it.
<details>
<summary>Appendix A.1: Making a swap partition</summary>

**Why would I want a swap partition?**

Swap is like memory but on your disk, useful if you have a low amount of RAM or do a lot of containerization / virtualization.
It's also helpful to have *some* swap.

<!-- you can't do headers in a dropdown -->

**Making a swap partition**

This is not your only option (you can also [**swap to a file**](https://wiki.archlinux.org/title/Swap#Swap_file) post-install), but here's how to do it:

Make a **new partition** (`Partition > New`) and set it up like the image below:

![blend-inst-m-8](./blend-installer-mpart-8.png)

Set `File System` to `linux-swap`, size to whatever you want (1028 MB = 1 GB in this case)

:::tip

If you don't know what size your swap should be, consult the table below:

![swap-size](./swap_size.png)

*Image taken from this [**It's FOSS article**](https://itsfoss.com/swap-size)*
:::

`Label` it what you want, and hit `Add`.

(you'll see something like this):

![blend-inst-m-9](./blend-installer-mpart-9.png)


</details>

1. Make your main partition:

Make a new partition with the following settings:

* File System: `ext4`
* Space: The rest of your drive (unless you want a seperate `/home`, `/usr`, and/or `/tmp` partition)
* Label: whatever you want

![blend-inst-10](./blend-installer-mpart-10.png)
<div class="gap"></div>

![blend-inst-mpart-11](./blend-installer-mpart-11.png)

6. Finalizing

Hit `Apply` (the green checkmark)

:::danger

**THIS WILL MAKE WRITE CHANGES TO YOUR DISK!!!**

Make sure that eveything is good before you proceed.

![blend-mmmmm](./blend-installer-mpart-12.png)

:::

Hit `Apply` again to proceed and wait for the operations to complete.

Once completed, hit `Close`.

![blend-inst-m-13](./blend-installer-mpart-13.png)

Now, go back to the **installer** (hit the refresh icon)

You should see your new partitions below:

![blend-inst-m-14](./blend-installer-mpart-14.png)

Set the following: (open the terminal and run `lsblk` to see disks and partitions on your system)

(You may see something different, like `/dev/nvme0n1p1` for partition 1 of NVMe drive 1, but the procedure is the same)

Make sure that you pick the right disk, note down the id of the disk you used (ex. `/dev/sda`) (may also be `/dev/sdb1`, `/dev/sdc1`, etc, but the procedure is the same)

![blend-inst-mpart-15](./blend-installer-mpart-15.png)
<div class="gap"></div>


:::info

`/dev/sda3` in the table will be `/dev/sda2` for you if you didn't make a swap space.

The biggest partition should be mounted at `/` and not formatted (it's your `/dev/sda3`).

:::

| Drive     | Format? | Mount Point |
| --------- | ------- | ----------- |
| /dev/sda1 | No      | `/boot/efi` |
| /dev/sda2 | No      | None        |
| /dev/sda3 | No      | `/`         |



</details>  

<div class="gap"></div>  

PluoxHost mirror provided by: [Pluox Hosting](https://pluoxhost.xyz) | 24/7 Freemium Host
