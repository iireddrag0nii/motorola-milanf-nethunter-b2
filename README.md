# Motorola milanf — Kali NetHunter B2 Kernel Configuration

An experimental, community-derived Linux kernel configuration for the
Motorola Moto G Stylus 5G (2022), model XT2215-4, codename `milanf`.

Developed and validated with LineageOS 23.2 (Android 16), Magisk root,
and a Kali NetHunter ARM64 userspace.

## Project overview

This project documents two kernel configuration iterations:

- **B1:** Added USB ConfigFS networking options for RNDIS and ECM.
- **B2:** Retained the B1 configuration and enabled selected Atheros,
  Ralink, and MediaTek USB wireless drivers.

The final B2 kernel uses Linux 5.4.302 with the local version `-moto`.

## Verified functionality

- Android boots with the custom B2 kernel
- Touchscreen and stylus operation
- Battery reporting and charging
- Cellular connectivity
- Built-in Wi-Fi and Bluetooth
- Magisk root
- Kali ARM64 environment
- NetHunter KeX graphical desktop
- Wireless ADB and KeX remote access
- Wired USB ADB and KeX remote access on macOS
- Burp Suite Community Edition
- HTTP/HTTPS proxy inspection and Repeater

## Configured but not yet validated

- External Atheros USB wireless adapters
- External Ralink USB wireless adapters
- External MediaTek USB wireless adapters
- Monitor mode and packet injection
- USB HID attack features

Enabling kernel options does not guarantee hardware compatibility
or successful operation of these features.

## Source and attribution

This project is derived from the work of TigerClips1:

https://github.com/TigerClips1/Kernel-milanf-nethunter-builder

Builder revision:
`fa3e256c9c154881f5a4cef8981456ec577859a9`

Kernel source revision:
`c63a2b5a1b970f8b9a231ea6a536a14bad15eab2`

Compiler:
Android Clang 21.0.0, based on r563880c.

This repository documents our experimental configuration and
validation. It is not an official Kali NetHunter release.

## Repository contents

- `configs/` — B1, B2, and complete final B2 kernel configurations
- `docs/` — Kernel configuration differences
- `validation/` — Build artifact checksums and test documentation

## Important warnings

This configuration is specific to the tested Motorola device and
software environment.

Do not flash a kernel or boot image without verifying device
compatibility, boot partition layout, Android version, and recovery
procedures.

No personal Magisk-patched boot image is distributed by this project.

## Project website

https://hbtechsolutions.com
