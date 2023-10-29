# Moonlight

JELOS now supports Moonlight Game Streaming, which allows to connect to your local computer running [Moonlight](https://moonlight-stream.org/) and stream AAA games.

## Step 1: Setup Moonlight on your PC
Please follow standard guide to setup Moonlight on your home PC, [link](https://github.com/moonlight-stream/moonlight-docs/wiki/Setup-Guide).

## Step 2: Configure Moonlight in JELOS
The setup requires pairing with your local PC running Moonlight and then populating Moonlight Streaming tab with all your games. After those are completed, you can select an individual game to start streaming.

### Pair with your local PC
* While in EmulationStation press ++"START"++ to open the Main Menu
* Select "MOONLIGHT GAME STREAMING" submenu
* Please note the "PAIRING PIN" at the bottom of the window
* You can also specify "SERVER IP" address, but it should be detected automatically
* Select "PAIR WITH SERVER" option
* Now, go to the local PC and enter PIN to continue the pairing process
* You should see a confirmation message on your device
* The paring process should complete

After pairing was successful, select "UPDATE MOONLIGHT GAMES" option. This should query the server for the list of all games and populate Moonlight Streaming system in Emulation Station.

## Step 3: Play
Browse to the Moonlight system in Emulation Station. Select the game you want to play. The game should start and you should be able to interact with it.

### Remote Playing over internet
* The easiest option is to add your device to your [Tailscale](../../configure/vpn/#tailscale) network with your local PC.
* Moonlight allows to open several ports to connect to the local PC to stream over the internet. Setup might be somewhat complicated.
* Another option is to use [WireGuard](../../configure/vpn/#wireguard) to setup the connection with the device. This approach requires only a single open port, but it requires WireGuard server to be running on your local network.