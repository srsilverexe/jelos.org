# ECWolf

## .ecwolf files
These files must be created for each Wolfenstein 3D compatible game. The file contains `PATH` variable that points to the subfolder containing the game's game files, `DATA` variable with the extension of the game files and `PK3` variables for each separate package file to load. `PK3` variables must be sequentially numbered with **_1**, **_2** etc.

Example: `/roms/ecwolf/wolfenstein3d.ecwolf` contains
```
PATH=Wolfenstein 3D
DATA=WL6
PK3_1=/roms/ecwolf/ecwolf.pk3
-- end --
```
where the Wolfenstein 3D game files have extension **.WL6**
> Note: the data value must match the file extension of the game exactly and is case sensitive so `WL6` is not the same as `wl6`

> Note: don't leave any space between `GRP` or `PATH` and `=` and enclose filenames containing spaces with "quotes"

> Note: add `-- end --` to the end of the file

Example: `/roms/ecwolf/spear of destiny.ecwolf` contains
```
PATH=SOD
DATA=SOD
PK3_1=/roms/ecwolf/SOD/ecwolf.pk3
-- end --
```
where the Spear of Destiny game files have extension **.SOD**
> Note: add `-- end --` to the end of the file