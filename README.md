# raspberry
Using Raspberry Pi as embedded linux platform

Embedded devices normaly do not have keyboard and display (at least not ones usually used on desktop computers) and as such are usually named headless devices.
Raspberry Pi is designed to be used in both scenarios. In this description the focus is put on Raspberry Pi as headless device.

1. Selecting and downloading OS image

So, after purchasing Raspberry Pi device (RPi from now on), the first step is to select and install operating system (OS) that will manage all the hardware present on RPi. 
Since there wil be not HDMI monitor nor 101-key attached to RPi it is reasonable to install Raspberry Pi OS Lite, which is intended for headless RPi. It does't include many of the software packages available in full OS version and ith therefore of significantly smaller size.

Download appropriate OS image using the following URL:
https://www.raspberrypi.com/software/operating-systems/

2. Flashing OS image on SD card

OS image is literally a disk image consisting of a partition table and two partitions (boot and rootfs). The first partition (boot) is of fat32 type and this is where all files needed to boot OS are present, including the linux kernel and various configuration files. Rootfs partition contains all applications and system software used for configuring RPi. This is the place where additional application packages are installed later on by user, when he needs one.
OS image (.img) file is usually downloaded compressed in .zip file and needs to be unzipped before flashing it on SD card.

Among various applications for flashing OS image, balenaEtcher (https://www.balena.io/etcher/) is available for Windows, Linux and macOS. Usage is very simple: just select OS image you want to flash (you may even use URL, so it will be downloaded before flashing), select SD card that you previously put into SD reader device (be careful, so that you don't overwrite your computer's disk) and flash the image.

So called "Raspberry Pi Imager" appliacation is also avaiable for SD card flashing, and is available for all three platforms https://www.raspberrypi.com/software/.

In addition, on Linux one may use "dd" (disk dump) utility to flash sd card:

> dd if=<OS image filenam> of=(SD card device file) BS=1M
  
  e.g.: > sudo dd if=2022-01-28-raspios-bullseye-armhf-lite.img of=/dev/sdb bs=4M conv=fsync status=progress




 
