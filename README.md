# Surface Pro 3 Kernel

Ubuntu Trusty kernel with patches for the Microsoft Surface 3

Upstream: git://kernel.ubuntu.com/ubuntu/ubuntu-trusty.git.

## Binary packages

http://surface3.rbel.co/kernel

## Patches

Type Cover 3 Support:

Patch from: http://ubuntuforums.org/showthread.php?t=2231207&page=2&p=13070900#post13070900

## Building

```
sudo apt-get install git build-essential kernel-package fakeroot libncurses5-dev bc

make -j `getconf _NPROCESSORS_ONLN` deb-pkg LOCALVERSION=-surface3
```

See https://wiki.ubuntu.com/KernelTeam/GitKernelBuild

## Touchpad support

Copy the `misc/xorg.conf` configuration to `/etc/X11/xorg.conf` and restart the session.

## Bluetooth/WiFi

Updating the firmware from the Marvell git repository fixes WiFi quirks and the bluetooth device is recognized (btusb), though not fully functional apparently.

```
git clone git://git.marvell.com/mwifiex-firmware.git
sudo cp mwifiex-firmware/mrvl/* /lib/firmware/mrvl/
```

and reboot.

## Reading

https://github.com/rubiojr/surface3-ubuntu-trusty
