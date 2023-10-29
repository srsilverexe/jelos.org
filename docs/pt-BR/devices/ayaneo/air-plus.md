# AYANEO Air Plus

![](../../_inc/images/devices/ayaneo-air-plus.png){ .off-glb }

## Overview

| Device | CPU / Architecture | Kernel | GL driver | Interface |
| -- | -- | -- | -- | -- |
| Air Plus | Amd Ryzen 7 6800U / (x86_64) | Mainline Linux | Radeonsi | Weston + Emulation Station |

## Features

| Feature&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Notes |
| -- | -- |
| :material-harddisk: Storage | JELOS can be run from a USB Drive or installed directly to the internal NVME. When installed directly to the NVME; an SD Card can be used for game storage. <br> JELOS **can't** be run from an SD Card on the AYANEO Air Plus due to a limitation in the device's bios that we unfortunately can't change. |
| :material-wifi: Wifi | Can be turned on in Emulation Station under Main Menu > Network Settings |
| :simple-bluetooth: Bluetooth | Supports bluetooth audio and controllers |
| :material-fan: Fan | Controlled by system firmware. |
| :material-lightning-bolt-circle: TPD Limit | Can be set globally, per system or per game. |
| :material-vibrate: Rumble | Enables the device rumble motor in emulators that support it. |
| :material-lightbulb-on: RGB | Supports selecting from a set of colors and brightness levels or turning the RGB off (choice persists through reboots) <br> Does not support other effects. |

## Notes

| DMI_SYS_VENDOR | DMI_PRODUCT_NAME |
| -- | -- |
| `AYANEO ` | `AIR Plus` |

### Installation

Download the latest `AMD64` version of JELOS from the button below and follow the instructions listed on the [Install](../../../play/install/) page.

[![Latest Version](https://img.shields.io/github/release/JustEnoughLinuxOS/distribution.svg?labelColor=111111&color=5998FF&label=Latest&style=flat#only-light)](https://github.com/JustEnoughLinuxOS/distribution/releases/latest)
[![Latest Version](https://img.shields.io/github/release/JustEnoughLinuxOS/distribution.svg?labelColor=dddddd&color=5998FF&label=Latest&style=flat#only-dark)](https://github.com/JustEnoughLinuxOS/distribution/releases/latest)

### Booting from an USB Drive

To boot JELOS from the USB Drive, hold ++"LC"+"Volume Up"++ and press the ++"Power"++ button, continue holding ++"LC"+"Volume Up"++ until the Ayaneo logo appears.  Select the storage device with JELOS from the boot menu using the Ayaneo button, and then press volume up to boot the distribution.

## Additional References

- [Platform Documentation (AMD64)](https://github.com/JustEnoughLinuxOS/distribution/blob/main/documentation/PER_DEVICE_DOCUMENTATION/AMD64)
- [Device Quirks](https://github.com/JustEnoughLinuxOS/distribution/tree/main/packages/hardware/quirks/devices/AYANEO%20AIR%20Plus)
- [Panel Rotation](https://github.com/JustEnoughLinuxOS/distribution/blob/main/packages/kernel/linux/patches/AMD64/002-display-quirks.patch)
