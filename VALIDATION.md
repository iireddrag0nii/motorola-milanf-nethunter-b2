# B2 Kernel Validation

## Test environment

- Device: Motorola Moto G Stylus 5G (2022)
- Model: XT2215-4
- Codename: milanf
- Android: LineageOS 23.2 / Android 16
- Kernel: Linux 5.4.302-moto
- Root: Magisk
- Kali environment: ARM64
- Desktop: Xfce through NetHunter KeX

## Passed

| Test | Result |
|---|---|
| Android boot | Passed |
| Touchscreen and stylus | Passed |
| Battery and charging | Passed |
| Cellular functionality | Passed |
| Built-in Wi-Fi | Passed |
| Bluetooth | Passed |
| Magisk root | Passed |
| Kali terminal | Passed |
| KeX desktop | Passed |
| Wireless ADB | Passed |
| USB ADB on macOS | Passed |
| Wired KeX via ADB forwarding | Passed |
| Burp Suite GUI | Passed |
| Burp HTTP proxy | Passed |
| Burp HTTPS inspection | Passed |
| Burp Repeater | Passed |

## Not fully tested

- External USB wireless adapter operation
- Wi-Fi monitor mode
- Packet injection
- USB HID features
- Compatibility with other Motorola variants
- Reproducibility on a clean development machine

## Known observations

An earlier USB connection failed to enumerate reliably on Windows.
A different USB-C data cable successfully established USB ADB on macOS.
The original cable and Windows USB-C connection require further testing.

Burp Suite's bundled browser failed to start in the ARM64 environment.
Firefox was successfully configured to use Burp's proxy.

Burp's Java text rendering improved when launched with:

`_JAVA_OPTIONS="-Dawt.useSystemAAFontSettings=on -Dswing.aatext=true"`

## Build integrity

See `validation/B2-SHA256SUMS.txt` for SHA-256 fingerprints of:

- Final B2 kernel configuration
- ARM64 Image
- ARM64 Image.gz

These fingerprints describe locally built artifacts, not the complete
Android boot image installed on the Motorola.
