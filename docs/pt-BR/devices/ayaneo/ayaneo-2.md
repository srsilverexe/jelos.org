# AYANEO 2

![](../../_inc/images/devices/ayaneo-2.png){ .off-glb }

## Overview

| Device | CPU / Architecture | Kernel | GL driver | Interface |
| -- | -- | -- | -- | -- |
| AYANEO 2 | Amd Ryzen 7 6800U / (x86_64) | Mainline Linux | Radeonsi | Weston + Emulation Station |

## Features

| Feature&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Notes |
| -- | -- |
| :material-harddisk: Storage | JELOS can be run from an SD Card, USB Drive or installed directly to the internal NVME. <br> When installed directly to the NVME; an SD Card can be used for game storage. |
| :material-wifi: Wifi | Can be turned on in Emulation Station under Main Menu > Network Settings |
| :simple-bluetooth: Bluetooth | Supports bluetooth audio and controllers |
| :material-lightning-bolt-circle: TPD Limit | Can be set globally, per system or per game. |
| :material-vibrate: Rumble | Enables the device rumble motor in emulators that support it. |

## Notes

| DMI_SYS_VENDOR | DMI_PRODUCT_NAME |
| -- | -- |
| `AYANEO ` | `AYANEO 2` |

### Installation

Download the latest `AMD64` version of JELOS from the button below and follow the instructions listed on the [Install](../../../play/install/) page.

[![Latest Version](https://img.shields.io/github/release/JustEnoughLinuxOS/distribution.svg?labelColor=111111&color=5998FF&label=Latest&style=flat#only-light)](https://github.com/JustEnoughLinuxOS/distribution/releases/latest)
[![Latest Version](https://img.shields.io/github/release/JustEnoughLinuxOS/distribution.svg?labelColor=dddddd&color=5998FF&label=Latest&style=flat#only-dark)](https://github.com/JustEnoughLinuxOS/distribution/releases/latest)

### Booting from an SD Card

To boot JELOS from the SD Card, hold ++"LC"+"Volume Up"++ and press the ++"Power"++ button, continue holding ++"LC"+"Volume Up"++ until the Ayaneo logo appears.  Select the storage device with JELOS from the boot menu using the Ayaneo button, and then press volume up to boot the distribution.

## Additional References

- [Platform Documentation (AMD64)](https://github.com/JustEnoughLinuxOS/distribution/blob/main/documentation/PER_DEVICE_DOCUMENTATION/AMD64)
- [Device Quirks](https://github.com/JustEnoughLinuxOS/distribution/tree/main/packages/hardware/quirks/devices/AYANEO%20AIR) (*shares the same quirks as the [AYANEO Air](air.md)*)
- [Panel Rotation](https://github.com/JustEnoughLinuxOS/distribution/blob/main/packages/kernel/linux/patches/AMD64/002-display-quirks.patch)