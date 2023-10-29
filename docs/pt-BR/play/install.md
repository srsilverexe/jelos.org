# :material-progress-check: Instalando o JELOS

JELOS é instalado baixando a imagem para o seu dispositivo, gravando-o em um cartão SD (Ou no armazenamento interno do seu dispositivo) e ligando o dispositivo para que ele inicie o processo de instalação.

## Primeiro passo: Download

[![Latest](https://img.shields.io/github/release/JustEnoughLinuxOS/distribution.svg?labelColor=111111&color=5998FF&label=Latest&style=flat#only-light)](https://github.com/JustEnoughLinuxOS/distribution/releases/latest)[![Latest](https://img.shields.io/github/release/JustEnoughLinuxOS/distribution.svg?labelColor=dddddd&color=5998FF&label=Latest&style=flat#only-dark)](https://github.com/JustEnoughLinuxOS/distribution/releases/latest)

* Baixe a ultima versão do JELOS para o seu dispositivo, esse download pode ser encontrado na [pagina de lançamentos](https://github.com/JustEnoughLinuxOS/distribution/releases/latest).



    * You'll find download links for each device/platform we support under the "`Installation Package Downloads`" header.
    * Make sure to download the correct image for your device.  For example; if you are installing JELOS on a [Loki Zero](../devices/ayn/loki-zero.md) you would download the `JELOS-AMD64` image.
    * If you have any questions you can check the [Device Support](../devices/index.md) section to confirm which image you should download for your specific device.

## Step 2: Flash

* First decompress the image.
* Then write the image to an SD Card using an imaging tool.
    * Common imaging tools include [Balena Etcher](https://www.balena.io/etcher/), [Raspberry Pi Imager](https://www.raspberrypi.com/software/), and [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/).  If you're skilled with the command line, `dd` can also be used.

## Step 3: Boot your device

* Insert your SD Card into your device while its off and then turn it on
* Note: Some devices may require you to set the boot order so your SD Card is loaded first.  Please see documentation for your specific device to see if this applies to you.
* JELOS will run through its install process and then reboot your device after its complete.
* When your device reboots it will load directly into EmulationStation; at this point you are good to go!

---

## Additional Notes

* JELOS operating system is stored on an Ext4 partition that can be read by LINUX but is not natively readable on Windows. Currently it is not possible to access the primary JELOS Ext4 partition on Windows to add games.
* On devices that support a second sd card, the sd card can be formatted as Ext4, FAT32, or exFAT. JELOS will automatically detect the second SD card on boot and configure the relevant folders for storing roms.
* On x86 devices JELOS includes an installation tool.  The installation tool can be found in the tools menu, which is one of the systems listed within ES.

## Next Steps

* [Add Games](/play/add-games)
* [Set up Networking](/configure/networking)
* [Themes](/configure/themes)
