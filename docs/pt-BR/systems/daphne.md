# Daphne

## Overview

| Game Path | Supported Extensions |
| --- | --- |
| `roms/daphne` | .daphne |

## Emulator/Core

| Name | Documentation |
| --- | --- |
| Hypseus Singe &nbsp; `default` | [github.com/DirtBagXon/hypseus-singe](https://github.com/DirtBagXon/hypseus-singe) |

## Instructions

### Background

Hypseus-Singe supports two different game formats (Daphne and Singe). One thing to keep in mind (which will help when working with files) is that Daphne is emulation so it requires a rom dump of the arcade machine to function and Singe is simulation so it combines video files with LUA code to simulate the machines.

The Daphne format requires a rom file that goes in the `daphne/roms` directory and a folder per game that contains resources (video files, sounds, etc...) for each game.  The Singe format is self-contained and its folders contain all the resources that a game requires to run.