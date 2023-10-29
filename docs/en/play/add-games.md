# :material-layers-plus: Adding Games to JELOS

JELOS has a few options for adding games and the option you choose will depend on the device you have and its available functionality *(For example, some devices do not have networking capabilites so those devices will not be able to use the network transfer option)*.  

This page will aim to document all possible options and indicate when you might use a given one over another.

!!! note "For details on which specific files each system requires please see the corresponding pages in the systems section of this wiki."

## Option 1: Network Transfer

Network transfer can be used on any device that can connect to the internet (this includes devices with native networking capabilites and ones where networking can be added through an external dongle).

This option first requires you to set up networking on your device.  Please see [Networking](../../configure/networking) for details.  Once you have completed those steps make note of your IP Address in the Network Settings menu.

In addition to your IP you will also need your root password.  This can be found in the Main Menu by pressing ++"START"++ in EmulationStation and navigating to `System Settings`.  You will see your root password under the `Authentication` header.

!!! note "By default the root password is set up to rotate to a unique string of characters after every reboot. You can leave it like this and make note of the current password, or you can turn it off and set it to something that will persist."

### SMB

- Windows:
    - open a Windows Explorer window, and type in `\\[YOUR IP ADDRESS]`; replace `[YOUR IP ADDRESS]` with the IP Address seen in the Network Settings menu.
    - You will be prompted for a username and password. 
    - The username is `root` and your password will be the value from `Root Password` in the System Settings menu.
- MacOS: 
    - open Finder and select `Go > Connect to Server` from the top menu.
    - In the address bar that appears, type `smb://[YOUR IP ADDRESS]`; replace `[YOUR IP ADDRESS]` with the IP Address seen in the Network Settings menu.
    - You will be prompted for a username and password.
    - For name enter `root` and your password will be the value from `Root Password` in the System Settings menu.

### FTP

Using your FTP program of choice; set up an SFTP connection to the IP Address seen in the Network Settings menu.  Make sure the Port is set to `22`.  The username is `root` and your password will be the value from `Root Password` in the System Settings menu. 

### After connecting

- You will see a list of folders after you have connected via network.  
- Open the `roms` folder and you will see a list of folders where games and bios files can be placed. *(Please see the systems section of the wiki for details on where each system's files should be placed)*
- After you have added your games you can get them to display in EmulationStation by pressing ++"START"++ to open the Main Menu, then open `Game Settings` then select `Update Gamelists` under the Tools header.

## Option 2: SD Card

Games can also be added via an SD card.  There are 2 primary methods for this depending on your device.

### If your device has 2 SD card slots

- With your device turned off; insert a FAT32/ExFAT/ext4 formated SD card into slot 2 of your device.
- Turn your device on.
- When JELOS completes its boot process it will generate a set of folders on the SD card in slot 2.
- Now you can turn off your device, remove your SD card from slot 2 and open it on your PC.
- You PC will display a list of folders for each system where you can place your games and bios files.
- Add your games and place your SD card back into slot 2 and boot up JELOS.

If your device does not see your SD card (or write the needed folders to it) please open `System Settings` and make sure `Autodetect Games Card` is turned on (located under the Preferences header) then reboot your device.

### If your device has 1 SD card slot

!!! warning "This option is only for devices where you have installed JELOS to the internal drive of the device. In this scenario an SD card can be used directly for storage"

- With JELOS installed to your internal drive press ++"START"++ to open the Main Menu, then open `System Settings` and turn on `Autodetect Games Card` under the Preferences header.
- Turn your device off
- Insert a FAT32/ExFAT/ext4 formated SD card into your device.
- Turn your device on
- When JELOS completes its boot process it will generate a set of folders on the SD card.
- Now you can turn off your device, remove your SD card and open it on your PC.
- You PC will display a list of folders, open the `roms` directory and you will see a list of folders for each system where you can place your games and bios files.
- Add your games and place your SD card back into your device and boot up JELOS.

## Option 3: External USB Drive

JELOS has a built in File Manager and you can use it to access connected USB drives and transfer files. 

1. Connect your USB Drive to your device
2. Open the Tools system and select File Manager
3. Navigate up to `/` and then select `media` - you should see your drive listed after opening media
4. Open your drive and you should see its contents
5. From here you can navigate to the file(s) you would like to copy and then navigate back to the `storage/roms` directory and paste your copied files in the approrpiate folder.

## Option 4: Linux OS

JELOS' storage drive is formated as ext4 which can be read navtively by linux operating systems.  Plugging in your SD card into an linux OS will enable you to browse the directories and add files directly.