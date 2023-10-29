# :material-controller: Controls

## RetroArch Hotkeys

| Button Combo | Action |
| -- | -- |
| ++"SELECT"+"START"++ <sup>(x2)</sup> | Quit Game |
| ++"SELECT"+"R1"++ | Save State |
| ++"SELECT"+"L1"++ | Load State |
| ++"SELECT"+"X(NORTH)"++ | Open RA Menu |
| ++"SELECT"+"Y(WEST)"++ | Show FPS |
| ++"SELECT"+"R2"++ | Fast-Forward |

By default JELOS will detect your controller and configure RetroArch hotkeys automatically.  If this behavior is not desired it can be disabled in the System Settings menu by disabling the "AUTOCONFIGURE RETROARCH HOTKEYS" option.

## Standalone (SA) Emulators

### Dolphin ([Gamecube](../../systems/gc))

| Button Combo | Action |
| -- | -- |
| ++"SELECT"+"START"++ | Quit Game |
| ++"SELECT"+"R1"++ | Save State |
| ++"SELECT"+"L1"++ | Load State |
| ++"SELECT"+"A(SOUTH)"++ | Screenshot |
| ++"SELECT"+"B(EAST)"++ | Change Internal Resolution |
| ++"SELECT"+"X(NORTH)"++ | Change Aspect Ratio |
| ++"SELECT"+"Y(WEST)"++ | Show FPS |
| ++"SELECT"+"D-Pad Up"++ | Increase current state slot |
| ++"SELECT"+"D-Pad Down"++ | Decrease current state slot |
| ++"SELECT"+"R2"++ | Fast-Forward |

### Mupen64Plus ([Nintendo 64](../../systems/n64))

| Button Combo | Action |
| -- | -- |
| ++"START"++ | Start |
| ++"B(EAST)"++ | A |
| ++"Y(WEST)"++ | B |
| ++"Right Analog Up"++ | C Up |
| ++"Right Analog Down"++ | C Down |
| ++"Right Analog Left"++ | C Left |
| ++"Right Analog Right"++ | C Right |
| ++"L2"++ <sup>*</sup> | Z |
| ++"L1"++ <sup>*</sup> | L |
| ++"R1"++ | R |
| ++"SELECT"+"START"++ | Quit Game |
| ++"SELECT"+"R1"++ | Save State |
| ++"SELECT"+"L1"++ | Load State |
| ++"SELECT"+"Y(WEST)"++ | Take Screenshot |
| ++"SELECT"+"B(SOUTH)"++ | Reset Game |

#### Additional Notes:

The Z and L button assignment can be changed in EmulationStation

* Highlight the game and press ++"X(NORTH)"++
* Select ADVANCED GAME OPTIONS (A to confirm)
* Set EMULATOR to MUPEN64PLUSSA
* Then change INPUT CONFIGURATION
    * DEFAULT:       L1 = L, L2 = Z
    * Z & L SWAP:    L1 = Z, L2 = L
    * CUSTOM:        You can create your own custom controller layout and add it to `/storage/.configs/game/configs/mupen64plussa`

### PPSSPP ([PSP](../../systems/psp))

| Button Combo | Action |
| -- | -- |
| ++"START"++ | Start |
| ++"SELECT"++ | Select |
| ++"A(SOUTH)"++ | Circle |
| ++"B(EAST)"++ | Cross |
| ++"X(NORTH"++ | Triangle |
| ++"Y(WEST)"++ | Square |
| ++"L1"++ | L |
| ++"R1"++ | R |
| ++"R3"++ | Open Menu |

### PCSX2 ([PS2](../../systems/ps2))

| Button Combo | Action |
| -- | -- |
| ++"SELECT"+"START"++ | Quit Game |
| ++"SELECT"+"R1"++ | Save State |
| ++"SELECT"+"L1"++ | Load State |
| ++"SELECT"+"X(NORTH)"++ | Open Menu |
| ++"SELECT"+"B(EAST)"++ | Take Screenshot |
| ++"SELECT"+"R2"++ | Fast-Forward |

### Yabasanshiro ([Sega Saturn](../../systems/saturn))

| Button Combo | Action |
| -- | -- |
| ++"START"++ | Start |
| ++"SELECT"++ | Open Menu |
| ++"Y(WEST)"++ | A |
| ++"B(EAST)"++ | B |
| ++"A(SOUTH)"++ | C |
| ++"X(NORTH"++ | X |
| ++"L1"++ | Y |
| ++"R1"++ | Z |
| ++"L2"++ | L |
| ++"R2"++ | R |
| ++"START"+"SELECT"+"R1"++ | Quit Game |

### Hypseus-singe ([Daphne](../../systems/daphne))

| Button Combo | Action |
| -- | -- |
| ++"SELECT"+"START"++ | Quit Game |
| ++"SELECT"++ | Coin |
| ++"START"++ | Start |
| ++"A(SOUTH)"++ | Button 1 |
| ++"B(EAST)"++ | Button 2 |
| ++"X(NORTH"++ | Button 3 |

#### Additional Notes:

To add/change mapping you can edit `/storage/.config/game/configs/hypseus/hypinput.ini` under `[KEYBOARD]` section by changing third number for a function from `0` (disabled) to a corresponding joystick value.  You can identify joystick values by running `jstest /dev/input/js0` over ssh.

For example the following would assign `quit` to ++"L1"++ and `pause` to ++"R1"++

``` bash
[KEYBOARD]
KEY_QUIT = SDLK_ESCAPE 0 5
KEY_PAUSE = SDLK_p 0 6

```

### Open Beats of Rage ([OpenBOR](../../systems/openbor))

| Button Combo | Action |
| -- | -- |
| ++"START"++ | Confirm |
| ++"SELECT"++ | Cancel |
| ++"A(SOUTH)"++ | Attack 1 |
| ++"B(EAST)"++ | Jump |
| ++"X(NORTH"++ | Attack 2 |
| ++"Y(WEST)"++ | Special |

> note: pressing A on title screen will exit


### Vice ([Commodore 64](../../systems/c64))

| Button Combo | Action |
| -- | -- |
| ++"START"++ | Open Menu |
| ++"SELECT"++ | Display Keyboard |
| ++"A(SOUTH)"++ | Back |
| ++"B(EAST)"++ | Fire / Confirm |
| ++"L1"++ | Back |
| ++"L2"++ | Assign Hotkey |
| ++"L3"++ | Fire (Joy 2) |
| ++"R1"++ | Confirm |
| ++"R2"++ | Swap Joystick Port |

#### Additional Notes:

Games will require keyboard key presses to progress through messages and to launch 
(e.g. SPACE, RSTR [run/start], F3, F7). 

SELECT to show onscreen keyboard, left analog/d-pad to move cursor, B to confirm 

C= on keyboard resets the machine

L2 to assign highlighted key or menu function to gamepad button (save config to retain)

To cancel onscreen keyboard, move cursor to blank area and A/L1 to close keyboard
or click on X in top left corner of keyboard

Joystick can be assigned to port 1 or 2. R2 to switch ports.
port 1: [left analog] + [B = fire]
port 2: [right analog] + [L3 = fire].

To quit emulator, START, highlight Exit Emulator, B to confirm



## Per Device Global Hotkeys

### HDMI Output

!!! note "These instruction only work for aarm64 devices.  This is not implemented for x86_64 devices."

Press ++"L1"++ + ++"START"++ + ++"SELECT"++ while in EmulationStation to swtich between Screen and HDMI output. 

While this should work; it doesn't always result in the correct resolution. The best way to get consistent results is to turn off the device, plug in an HDMI cable and reboot.  

"Why doesn't hot-plugging just work?"... Hot-plug HDMI switching is a fairly complex action to accomplish and not something we have implemented on any device.  If you are a developer and interested in helping to build this functionality please start here: [Contribute](../contribute)

### Additional Keys

|Device|Brightness Up|Brightness Down|Battery Status|WIFI Toggle|
|----|----|----|----|----|
|Anbernic RG351M|Select & Vol +|Select & Vol -|Start  & Vol +|Start & Vol -|
|Anbernic RG353M|Select & Vol +|Select & Vol -|Fn & Vol +|Fn & Vol -|
|Anbernic RG353P|Select & Vol +|Select & Vol -|Fn & Vol +|Fn & Vol -|
|Anbernic RG353V|Select & Vol +|Select & Vol -|Fn & Vol +|Fn & Vol -|
|Anbernic RG503|Select & Vol +|Select & Vol -|Fn & Vol +|Fn & Vol -|
|Anbernic RG552|Select & Vol +|Select & Vol -|Fn & Vol +|Fn & Vol -|
|ATARI VCS 800 Onyx|NA|NA|NA|NA|
|AYANEO AIR|Aya Button & Vol + | Aya Button & Vol - | = Button & Vol + | = Button & Vol -|
|AYANEO AIR Plus|Aya Button & Vol + | Aya Button & Vol - | = Button & Vol + | = Button & Vol -|
|AYANEO AIR Pro|Aya Button & Vol + | Aya Button & Vol - | = Button & Vol + | = Button & Vol -|
|AYANEO AYANEO 2|Aya Button & Vol + | Aya Button & Vol - | = Button & Vol + | = Button & Vol -|
|AYANEO AYA NEO 2021|Aya Button & Vol + | Aya Button & Vol - | = Button & Vol + | = Button & Vol -|
|AYANEO AYANEO 2021|Aya Button & Vol + | Aya Button & Vol - | = Button & Vol + | = Button & Vol -|
|AYANEO AYANEO 2021 Pro|Aya Button & Vol + | Aya Button & Vol - | = Button & Vol + | = Button & Vol -|
|AYANEO AYANEO 2021 Pro Retro Power|Aya Button & Vol + | Aya Button & Vol - | = Button & Vol + | = Button & Vol -|
|AYA NEO AYA NEO Founder|Aya Button & Vol + | Aya Button & Vol - | = Button & Vol + | = Button & Vol -|
|AYANEO AYANEO NEXT Pro|Aya Button & Vol + | Aya Button & Vol - | = Button & Vol + | = Button & Vol -|
|AYANEO GEEK|Aya Button & Vol + | Aya Button & Vol - | = Button & Vol + | = Button & Vol -|
|AYANEO NEXT|Aya Button & Vol + | Aya Button & Vol - | = Button & Vol + | = Button & Vol -|
|AYANEO NEXT Advance|Aya Button & Vol + | Aya Button & Vol - | = Button & Vol + | = Button & Vol -|
|AYANEO NEXT Pro|Aya Button & Vol + | Aya Button & Vol - | = Button & Vol + | = Button & Vol -|
|GPD G1619-04|TBD|TBD|TBD|TBD|
|Hardkernel ODROID-GO-Ultra|F1 & Vol +|F1 & Vol -|F2 & Vol +|F2 & Vol -|
|Indiedroid Nova|NA|NA|NA|NA|
|LENOVO 81TC|NA|NA|NA|NA|
|ODROID-GO Advance|Select & Vol +|Select & Vol -|Start & Vol +|Start & Vol -|
|ODROID-GO Advance Black Edition|Select & Vol +|Select & Vol -|Start & Vol +|Start & Vol -|
|ODROID-GO Super|Select & Vol +|Select & Vol -|Start & Vol +|Start & Vol -|
|Orange Pi 5|NA|NA|NA|NA|
|Powkiddy RGB10 MAX 3|F1 & Vol +|F1 & Vol -|F2 & Vol +|F2 & Vol -|
|Powkiddy RK2023|Select & Vol +|Select & Vol -|Start & Vol +|Start & Vol -|
|Powkiddy x55|Select & Vol +|Select & Vol -|Start & Vol +|Start & Vol -|
|Valve Jupiter|Steam Button & Vol + | Steam Button & Vol - | ... Button & Vol + | ... Button & Vol -|