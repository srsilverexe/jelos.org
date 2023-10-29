#  :material-update: Updating JELOS

JELOS can be updated "Over the Air" (OTA) or by manually downloading an update .tar file, adding to your device storage and rebooting.

## Option 1: OTA Update

If your device has access to the internet you can update JELOS directly from EmulationStation.

1. In EmulationStation open the main menu by pressing the ++"Start"++ button on your controller.
2. Select `System Settings`
3. Scroll to the `System Update` header and select `Start Update`

!!! info "You can also view the change log for the latest release by selecting the `Change Log` before you update."

## Option 2: Manual Update

If you device does not have access to the internet you can still update manually

1. Download the latest update (.tar) of JELOS for your device from the [releases page](https://github.com/JustEnoughLinuxOS/distribution/releases/latest).
	* You'll find download links for each device/platform we support under the "`Update Package Downloads`" header.
    * Make sure to download the correct .tar file for your device.  For example; if you are installing JELOS on a [Loki Zero](../devices/ayn/loki-zero.md) you would download the `JELOS-AMD64` file.
    * If you have any questions you can check the [Device Support](../devices/index.md) section to confirm which .tar you should download for your specific device.
2. Copy the update to your device's update share.
3. Reboot the device, and the update will begin automatically.