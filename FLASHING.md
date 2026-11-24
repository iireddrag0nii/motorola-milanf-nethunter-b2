# Flashing and Recovery

## Supported test device

Motorola Moto G Stylus 5G (2022)
Model: XT2215-4
Codename: milanf

Tested with LineageOS 23.2 / Android 16.

## Important warning

Flashing a kernel or Android boot image can prevent a device
from booting.

Do not use this configuration on another device or Android
version without verifying compatibility.

## Installation approach used during development

The B2 kernel was compiled separately from the Android boot image.

During development:

1. The matching Android boot image was preserved.
2. The compiled kernel was incorporated into a boot image.
3. The existing ramdisk and Magisk functionality were preserved.
4. The resulting image was tested using temporary booting.
5. Android hardware functionality was validated.
6. The working image was installed to the tested boot slot.
7. USB ADB and KeX functionality were validated.

The original device was using the A slot during validation.

## Recovery considerations

Maintain an independently verified recovery image before
testing or installing another kernel.

Verify bootloader unlock status, active boot slot, matching
Android build, image integrity, and recovery procedures.

Do not assume a boot image from another Motorola device is safe.

## Distribution policy

This repository does not distribute the developer's personal
Magisk-patched boot image.

No generic flashable release is provided at this stage.

Future binary releases will require separate compatibility,
licensing, packaging, and recovery validation.
