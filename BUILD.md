# Building the Motorola milanf B2 Kernel

## Tested environment

- Device: Motorola Moto G Stylus 5G (2022), XT2215-4
- Codename: milanf
- Android: LineageOS 23.2 / Android 16
- Kernel: Linux 5.4.302-moto
- Architecture: ARM64
- Compiler: Android Clang 21.0.0 (r563880c)

## Upstream builder

This project uses the community kernel builder maintained by TigerClips1:

https://github.com/TigerClips1/Kernel-milanf-nethunter-builder

Tested builder revision:

fa3e256c9c154881f5a4cef8981456ec577859a9

Kernel source revision:

c63a2b5a1b970f8b9a231ea6a536a14bad15eab2

## Configuration history

### B1

B1 introduced USB ConfigFS networking support:

- CONFIG_USB_CONFIGFS_RNDIS=y
- CONFIG_USB_CONFIGFS_ECM=y
- CONFIG_USB_CONFIGFS_ECM_SUBSET=y

### B2

B2 retained the B1 configuration and enabled:

- CONFIG_ATH9K_HTC=y
- CONFIG_RT2800USB=y
- CONFIG_MT76x2U=y

The complete configuration used for the successful B2
build is preserved in:

configs/milanf-b2-final.config

This complete configuration is the authoritative reference.
The B1 and B2 fragments document the development history.

## Original build outputs

The verified local build produced:

- arch/arm64/boot/Image
- arch/arm64/boot/Image.gz

SHA-256 checksums are recorded in:

validation/B2-SHA256SUMS.txt

## Rebuilding

The upstream builder provides:

- build.sh
- scripts/05_configure.sh
- scripts/06_build.sh

The builder supports separate configuration and compilation stages.

A new build must use a compatible source revision, compiler,
device configuration, and kernel configuration.

The original B2 build was completed successfully on Dragon.

A clean-room rebuild using only this repository's instructions
has not yet been independently validated.

Do not assume that copying the B2 fragment alone reproduces
the final kernel configuration.

## Important limitation

This repository initially distributes configuration files
and technical documentation, not a flashable Android boot image.

The installed Motorola boot image was prepared separately
while preserving its Android ramdisk and Magisk root environment.
