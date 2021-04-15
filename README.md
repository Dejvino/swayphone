# swayphone
Sway configured for a phone.

*TODO: screenshot*

This is a repository with PKGBUILDs; useful for building Arch Linux ARM packages.

## Overview
*TODO: what is provided?*

## Packages
*TODO: details and logic behind packages*

* pptk ... [PinePhone Toolkit](https://github.com/Dejvino/pinephone-toolkit/)

## Building
To build AArch64 (ARM) packages on an x86_64 machine, consider using [armutils](https://gitlab.com/mipimipi/armutils). This creates an AArch64 chroot and runs the compilation emulated in QEMU. E.g. for building a package located in `./pkg`: 

```
$ mkarmroot -u http://os.archlinuxarm.org/os/ArchLinuxARM-aarch64-latest.tar.gz ./aarch64/root base-devel
$ cd pkg
$ sudo makearmpkg -r ../aarch64 -- --noconfirm
```

Otherwise, you can just build this package directly on the target device as usual:

```
$ cd pkg
$ makepkg -si
```

