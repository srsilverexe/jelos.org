# Doom

## .doom files
These files must be created for each **WAD** that you want to load with gzdoom or lzdoom. The file contains `IWAD` variables and optional `MOD` variables. Multiple `IWAD` and `MOD` variables can be used in the same file to load multiple wads, mods and packages. Therefore, multiple **.doom** files can be created for the same **WAD** for each configuration of the game. It is recommended to store **WAD** files in a **iwads** subfolder and `MODs` in a **mods** subfolder and include the full path to each file in the **.doom** file.

Example: `/roms/doom/doom.doom` contains
```
IWAD=/roms/doom/iwads/doom.wad
```
to load vanilla doom
> Note: don't leave any space between `GRP` or `PATH` and `=` and enclose filenames containing spaces with "quotes"

Example: `/roms/doom/heretic-mod.doom` contains
```
IWAD=/roms/doom/iwads/heretic.wad
IWAD=/roms/doom/iwads/IWMPP_Heretic.wad
MOD=/roms/doom/mods/precise-crosshair-v1.4.1.pk3
MOD=/roms/doom/mods/target-spy-v2.0.1.pk3
-- end --
```
to load Heretic with additional patches and mods.
> Note: add `-- end --` to the end of the file when it contains multiple lines