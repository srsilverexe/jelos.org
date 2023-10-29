# SCUMMVM

## .scummvm or .svm files
These files are created by `_Scan ScummVM Games.sh` script in `/storage/.config/scummvm` folder (which is also displayed in EmuStation). The script scans for game folders and generates the relevant `.scummvm` files to launch those games. The files are stored in `/storage/.config/scummvm/games`.  

`.scummvm` files are named using the common name of the game and the <a href="https://www.scummvm.org/compatibility/"> <strong>Game Short Name</strong></a> in brackets (e.g. `Beneath a Steel Sky (sky).scummvm`). 

`.scummvm` files contain a single line in the form:

* `--path=` variable and the path to the folder containing the game, *followed by*
* <a href="https://www.scummvm.org/compatibility/"> <strong>Game Short Name</strong></a>

Example: `/storage/.config/scummvm/games/Beneath a Steel Sky (sky).scummvm` contains
```
--path="/roms/scummvm/Beneath a Steel Sky (CD VGA)" sky
```
> Note: enclose filenames containing spaces with "quotes"

> Note: `.scummvm` and `.svm` files are identical and interchangeable

> Note: the `.scummvm` files are **NOT** stored in `/roms/scummvm` and any `.scummvm` files stored there will not be displayed by EmuStation. EmuStation only displays `.scummvm` files that are in `/storage/.config/scummvm/games`.

> Note: to display metadata and media within EmuStation, put `gamelist.xml` in `/storage/.config/scummvm/games` and media into relevant subfolders (e.g. `/storage/.config/scummvm/games/media` folder with `boxart`, `images` and `videos` subfolders)