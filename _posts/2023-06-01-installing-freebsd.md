---
layout: post
category: freebsd
title: Installing FreeBSD
---

I recently installed FreeBSD on a Lenovo IdeaPad N581. Here are some solutions to the paint points I had.

## Determine PC Architecture(Debian)
Determine the architecture of the hardware FreeBSD is to be installed on.
On Debian systems, you can get this info by running `dpkg --print-architecture`.

## Calculate and verify checksum(MacOS)
Verify that the downloaded image file is not corrupted.
On a Mac, with a checksum file downloaded to the same directory as the image file,
run `shasum -a 512 FreeBSD-13.2-RELEASE-amd64-memstick.img | shasum -c`
to calculate the checksum of the image and compare it to the data in the checksum file
generated using the same algorithm, in this case `SHA-512`.

## Write image to USB stick(MacOS)
- Use `Disk Utility` to find USB stick device name
- Write image to stick using `dd`

## Disable the console system beep
By default, FreeBSD console has an annoying system beep enabled.
I disabled it using `kbdcontrol -b quiet.off` as described [here](https://unix.stackexchange.com/a/219826)

## Read the Handbook
Overall, it was a smooth experience installing FreeBSD for the second time. The [Installing FreeBSD section of the handbook](https://docs.freebsd.org/en/books/handbook/bsdinstall/) is very detailed and approachable. It answered a lot of my questions related to setting up WiFi, Windows manager, downloading packages etc.