# AYANEO Air / Air Pro

![](../../_inc/images/devices/ayaneo-air.png){ .off-glb }

## Overview

| Device | CPU / Architecture | Kernel | GL driver | Interface |
| -- | -- | -- | -- | -- |
| Air | Amd Ryzen 5 5560U (x86_64) | Mainline Linux | Radeonsi | Weston + Emulation Station |
| Air Pro | Amd Ryzen 5 5560U (x86_64) | Mainline Linux | Radeonsi | Weston + Emulation Station |
| Air Pro | AMD Ryzen 7 5825U (x86_64) | Mainline Linux | Radeonsi | Weston + Emulation Station |

## Features

| Feature&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Notes |
| -- | -- |
| :material-harddisk: Storage | JELOS can be run from an SD Card, USB Drive or installed directly to the internal NVME. <br> When installed directly to the NVME; an SD Card can be used for game storage. |
| :material-wifi: Wifi | Can be turned on in Emulation Station under Main Menu > Network Settings |
| :simple-bluetooth: Bluetooth | Supports bluetooth audio and controllers |
| :material-fan: Fan | Can be set globally, per system or per game. |
| :material-lightning-bolt-circle: TPD Limit | Can be set globally, per system or per game. |
| :material-vibrate: Rumble | Enables the device rumble motor in emulators that support it. |
| :material-lightbulb-on: RGB | Supports selecting from a set of colors and brightness levels or turning the RGB off (choice persists through reboots) <br> Does not support other effects. |

## Notes

| DMI_SYS_VENDOR | DMI_PRODUCT_NAME |
| -- | -- |
| `AYANEO ` | `AIR` |
| `AYANEO ` | `AIR Pro` |

### Installation

Download the latest `AMD64` version of JELOS from the button below and follow the instructions listed on the [Install](../../../play/install/) page.

[![Latest Version](https://img.shields.io/github/release/JustEnoughLinuxOS/distribution.svg?labelColor=111111&color=5998FF&label=Latest&style=flat#only-light)](https://github.com/JustEnoughLinuxOS/distribution/releases/latest)
[![Latest Version](https://img.shields.io/github/release/JustEnoughLinuxOS/distribution.svg?labelColor=dddddd&color=5998FF&label=Latest&style=flat#only-dark)](https://github.com/JustEnoughLinuxOS/distribution/releases/latest)

### Booting from an SD Card

To boot JELOS from the SD Card, hold ++"LC"+"Volume Up"++ and press the ++"Power"++ button, continue holding ++"LC"+"Volume Up"++ until the Ayaneo logo appears.  Select the storage device with JELOS from the boot menu using the Ayaneo button, and then press volume up to boot the distribution.

### Changing the RGB 

In EmulationStation press the ++"Start"++ button to open the Main Menu.  Then select `System Settings` and scroll until you see `Device LEDS`.  Under that setting you can choose to turn RGB Off or select from a set of pre-defined colors.  The value you set will persist through all future reboots but note your RGB setting will only take effect after JELOS boots.

## Controls

### `evtest` Output

??? abstract "Main Controls"

	``` bash title="/dev/input/event6: Microsoft X-Box 360 pad"
	Input driver version is 1.0.1
	Input device ID: bus 0x3 vendor 0x45e product 0x28e version 0x110
	Input device name: "Microsoft X-Box 360 pad"
	Supported events:
	  Event type 0 (EV_SYN)
	  Event type 1 (EV_KEY)
	    Event code 304 (BTN_SOUTH)
	    Event code 305 (BTN_EAST)
	    Event code 307 (BTN_NORTH)
	    Event code 308 (BTN_WEST)
	    Event code 310 (BTN_TL)
	    Event code 311 (BTN_TR)
	    Event code 314 (BTN_SELECT)
	    Event code 315 (BTN_START)
	    Event code 316 (BTN_MODE)
	    Event code 317 (BTN_THUMBL)
	    Event code 318 (BTN_THUMBR)
	  Event type 3 (EV_ABS)
	    Event code 0 (ABS_X)
	      Value      0
	      Min   -32768
	      Max    32767
	      Fuzz      16
	      Flat     128
	    Event code 1 (ABS_Y)
	      Value      0
	      Min   -32768
	      Max    32767
	      Fuzz      16
	      Flat     128
	    Event code 2 (ABS_Z)
	      Value      0
	      Min        0
	      Max      255
	    Event code 3 (ABS_RX)
	      Value      0
	      Min   -32768
	      Max    32767
	      Fuzz      16
	      Flat     128
	    Event code 4 (ABS_RY)
	      Value     -1
	      Min   -32768
	      Max    32767
	      Fuzz      16
	      Flat     128
	    Event code 5 (ABS_RZ)
	      Value      0
	      Min        0
	      Max      255
	    Event code 16 (ABS_HAT0X)
	      Value      0
	      Min       -1
	      Max        1
	    Event code 17 (ABS_HAT0Y)
	      Value      0
	      Min       -1
	      Max        1
	  Event type 21 (EV_FF)
	    Event code 80 (FF_RUMBLE)
	    Event code 81 (FF_PERIODIC)
	    Event code 88 (FF_SQUARE)
	    Event code 89 (FF_TRIANGLE)
	    Event code 90 (FF_SINE)
	    Event code 96 (FF_GAIN)
	```

??? abstract "AYA Button"

	``` bash title="/dev/input/event4: AT Translated Set 2 keyboard"
	Event: time 1695145934.368865, type 4 (EV_MSC), code 4 (MSC_SCAN), value 9d
	Event: time 1695145934.368865, type 1 (EV_KEY), code 97 (KEY_RIGHTCTRL), value 1
	Event: time 1695145934.368865, -------------- SYN_REPORT ------------
	Event: time 1695145934.374867, type 4 (EV_MSC), code 4 (MSC_SCAN), value db
	Event: time 1695145934.374867, type 1 (EV_KEY), code 125 (KEY_LEFTMETA), value 1
	Event: time 1695145934.374867, -------------- SYN_REPORT ------------
	Event: time 1695145934.377854, type 4 (EV_MSC), code 4 (MSC_SCAN), value 58
	Event: time 1695145934.377854, type 1 (EV_KEY), code 88 (KEY_F12), value 1
	```

??? abstract "= Button"

	``` bash title="/dev/input/event4: AT Translated Set 2 keyboard"
	Event: time 1695146001.237895, type 4 (EV_MSC), code 4 (MSC_SCAN), value db
	Event: time 1695146001.237895, type 1 (EV_KEY), code 125 (KEY_LEFTMETA), value 1
	Event: time 1695146001.237895, -------------- SYN_REPORT ------------
	Event: time 1695146001.241670, type 4 (EV_MSC), code 4 (MSC_SCAN), value 20
	Event: time 1695146001.241670, type 1 (EV_KEY), code 32 (KEY_D), value 1
	```

??? abstract "LC Button"

	``` bash title="/dev/input/event4: AT Translated Set 2 keyboard"
	Event: time 1695146086.777678, type 4 (EV_MSC), code 4 (MSC_SCAN), value 9d
	Event: time 1695146086.777678, type 1 (EV_KEY), code 97 (KEY_RIGHTCTRL), value 1
	Event: time 1695146086.777678, -------------- SYN_REPORT ------------
	Event: time 1695146086.783607, type 4 (EV_MSC), code 4 (MSC_SCAN), value db
	Event: time 1695146086.783607, type 1 (EV_KEY), code 125 (KEY_LEFTMETA), value 1
	Event: time 1695146086.783607, -------------- SYN_REPORT ------------
	Event: time 1695146086.786592, type 4 (EV_MSC), code 4 (MSC_SCAN), value 57
	Event: time 1695146086.786592, type 1 (EV_KEY), code 87 (KEY_F11), value 1
	```

??? abstract "RC Button"

	``` bash title="/dev/input/event4: AT Translated Set 2 keyboard"
	Event: time 1695146121.656854, type 4 (EV_MSC), code 4 (MSC_SCAN), value 9d
	Event: time 1695146121.656854, type 1 (EV_KEY), code 97 (KEY_RIGHTCTRL), value 1
	Event: time 1695146121.656854, -------------- SYN_REPORT ------------
	Event: time 1695146121.663265, type 4 (EV_MSC), code 4 (MSC_SCAN), value db
	Event: time 1695146121.663265, type 1 (EV_KEY), code 125 (KEY_LEFTMETA), value 1
	Event: time 1695146121.663265, -------------- SYN_REPORT ------------
	Event: time 1695146121.665821, type 4 (EV_MSC), code 4 (MSC_SCAN), value 44
	Event: time 1695146121.665821, type 1 (EV_KEY), code 68 (KEY_F10), value 1
	```

## Additional References

- [Platform Documentation (AMD64)](https://github.com/JustEnoughLinuxOS/distribution/blob/main/documentation/PER_DEVICE_DOCUMENTATION/AMD64)
- [Device Quirks](https://github.com/JustEnoughLinuxOS/distribution/tree/main/packages/hardware/quirks/devices/AYANEO%20AIR)
- [Panel Rotation](https://github.com/JustEnoughLinuxOS/distribution/blob/main/packages/kernel/linux/patches/AMD64/002-display-quirks.patch)
