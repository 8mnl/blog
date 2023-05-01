---
title: "Preparing a bootable Windows 10 USB Stick on macOS Ventura"
excerpt_separator: "<!--more-->"
tags:
  - macos
  - tutorial
---

> Tested on macOS Ventura 13.3

## Find the correct USB device:

    diskutil

## Format the USB device:

    sudo diskutil eraseDisk FAT32 WINDOWS MBRFormat /dev/disk4

## Mount the Windows 10 ISO:

    hdiutil mount ~/Downloads/Win10_22H2_EnglishInternational_x64.iso

## Copy ISO contents to the USB device:

    rsync -avh --progress --exclude=sources/install.wim /Volumes/CCCOMA_X64FRE_EN-GB_DV9/ /Volumes/WINDOWS

## Install wimlib via brew:

    brew install wimlib

## Split install.wim with wimlib and copy it to the USB device:

    wimlib-imagex split /Volumes/CCCOMA_X64FRE_EN-GB_DV9/sources/install.wim /Volumes/WINDOWS/sources/install.swm 4000


*When booting from the USB device and the screen turns black, just wait until the Windows installation GUI appears.*