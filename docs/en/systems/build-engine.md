# Build Engine

## .build files
These files must be created for each build engine game that will be launched with raze. The file contains a `PATH` variable and an optional `GRP` variable. The `PATH` variable points to the subfolder containing the game's **GRP** file. The optional `GRP` variable is used to identify the specific **GRP** file to load for games with multiple **GRP** files.

Example: `/roms/build/shadow warrior.build` contains
```
PATH=sw
GRP=SW.GRP
-- end --
```
where the Shadow Warrior games files are stored in subfolder `sw`, i.e. `/roms/build/sw/`
> Note: don't leave any space between `GRP` or `PATH` and `=` and enclose filenames containing spaces with "quotes"

> Note: add `-- end --` to the end of the file if it contains multiple lines