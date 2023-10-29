# :material-check-network-outline: VPN Services

JELOS has built in support for multiple VPN services.

## Tailscale

Tailscale is a VPN service that makes the devices and applications you own accessible anywhere in the world, securely and effortlessly. It enables encrypted point-to-point connections using the open source [WireGuard](https://www.wireguard.com/) protocol, which means only devices on your private network can communicate with each other.

### Step 1: Sign up for Tailscale account
[Sign up for a Tailscale account](https://login.tailscale.com/start).

Tailscale requires a Single Sign-On (SSO) provider, so you’ll need a Google, Microsoft, GitHub, Okta, OneLogin, or other  [supported SSO identity provider](https://tailscale.com/kb/1013/sso-providers)  account to begin.

### Step 2: Add a PC to your Tailscale network

Tailscale helps you connect your devices together. For that to be possible, Tailscale needs to run on your PC.

Tailscale works seamlessly with Linux, Windows, macOS, Raspberry Pi, Android, Synology, and more. Download Tailscale and log in on the PC.

[Download Tailscale](https://tailscale.com/download/)

### Step 3: Add your device to your network

JELOS Emulation Station has customized UI with Tailscale support.

- Press "start" button to go into Emulation Station Main Menu.
- Select Network Settings submenu.
- Select "Tailscale VPN" and turn it on.
- Select "Back" button to exit setting dialog.

The initial connection to Tailscale will require authentication.

- Select Network Settings submenu again.
- You should see Tailscale authentication url. You need to type this url on your PC browser and authenticate.
- After login on PC is successful, Select "Tailscale VPN" and turn it on again.
- Select "Back" button to exit setting dialog.
- Tailscale VPN should be connected.

### Links
* Tailscale homepage [link](https://tailscale.com/)

---

## Wireguard

As game streaming becomes more popular, it enables AAA games, streamed over the internet from your home computer, to be played on your console while traveling.

### Configuring WireGuard VPN in JELOS
Typically the configuration involves copying your WireGuard VPN config file over to your JELOS device and then enabling WireGuard VPN in Emulation Station Network Settings menu.

#### WireGuard Config
JELOS uses standard WireGuard config file format. The file is typically provided by your VPN provider. If you want to host your own VPN Server on your local network, there are plenty of tutorials available online.

Currently only the single connection is supported. The WireGuard config file must be placed in the following location - `/storage/.config/wireguard/wg0.conf`. Please use SSH or Samba to create the file there.

Don't forget to restart Emulation Station to pick up the changes.

Sample `wg0.conf` file
```
[Interface]
PrivateKey = <your private key>
Address = 10.111.10.2/24

[Peer]
PublicKey = <server public key>
AllowedIPs = 0.0.0.0/0
Endpoint = <server>:<port>
```
> Note: "DNS" option is not yet supported in the config. Please remove line starting with "DNS" from your config file.

#### Enabling WireGuard connection
Emulation Station now has a new menu item toggle to enable or disable WireGuard VPN connection. Use it turn the connection on or off.

> Note: make sure that WireGuard config file is present on the device, see the Configuring WireGuard VPN in JELOS section above. The menu option is only available when the config file is present.

Connect to configured VPN server
* Press "start" button to go into Emulation Station Main Menu
* Select Network Settings submenu
* Select "Wireguard VPN" and turn it on
* Select "Back" button to exit setting dialog
* WireGuard VPN should be connected

Disconnect from configured VPN server
* Press "start" button to go into Emulation Station Main Menu
* Select Network Settings submenu
* Select "Wireguard VPN" and turn it off
* Select "Back" button to exit setting dialog
* WireGuard VPN should be disconnected

#### Server Configuration (for advanced users)
The local PC can be setup to be a WireGuard server. This allows accessing that PC (and a local network if SNAT is enabled) from the remote location using the device.

The configuration is the following:
* Generate pair of configuration files
* Install WireGuard on your local PC and import server config
* Setup Port Forwarding for WireGuard port from your local router to your local PC
* Enable WireGuard on your device 

##### Config Pair generation
The device have a helper script which can generate a pair of configuration files for the device and for the local PC with WireGuard server.

The script should be executed from SSH terminal.
```
# Generate config file
wg-genconfig
```
The script will generate `wg0.conf` and `wg0.conf.server` files.

###### `wg0.conf.server` server config
```
[Interface]
PrivateKey = <server private key>
# PublicKey = <server public key>
Address = 10.111.10.1/24
ListenPort = 51820

# If you want to access other devices on the same network,
# you need to enable SNAT, the lines below.
# Make sure that eth0 matches your main network interface.
#PostUp = echo 1 > /proc/sys/net/ipv4/ip_forward
#PostUp = iptables -A FORWARD -i %i -j ACCEPT
#PostUp = iptables -A FORWARD -o %i -j ACCEPT
#PostUp = iptables -t nat -A POSTROUTING -s 10.111.10.0/24 -o eth0 -j MASQUERADE
#PostDown = iptables -D FORWARD -i %i -j ACCEPT
#PostDown = iptables -D FORWARD -o %i -j ACCEPT
#PostDown = iptables -t nat -D POSTROUTING -s 10.111.10.0/24 -o eth0 -j MASQUERADE

[Peer]
PublicKey = <device public key>
AllowedIPs = 10.111.10.2/32
```
If you want you device to access your local network, you need to enable SNAT, allow your local PC forward network packets to other devices on your local network. That is done by uncommenting PostUp/PostDown commands in the config. 

##### Install WireGuard on your local PC
* Download the client for your OS from [here](https://www.wireguard.com/install/).
* Import  wg0.conf.server and enable the tunnel.

### Troubleshooting

#### Diagnostics
Sometimes the tunnel doesn't establish successfully. The following commands can useful to diagnose issues.

The commands below should be executed on the device using SSH shell access.

```
# Check the status of active tunnels.
# You should see the connection statistics.
wg show
```
```
# Check my public ip address
curl ifconfig.co -4
```
```
# Bring tunnel up
wg-quick up /storage/.config/wireguard/wg0.conf
```
```
# Bring tunnel down
wg-quick down /storage/.config/wireguard/wg0.conf
```

### Links
* WireGuard homepage [link](https://www.wireguard.com/)
* WireGuard is also supported in ConnMan VPN plugin using ssh command line [link](https://wiki.libreelec.tv/configuration/wireguard)

---

## ZeroTier
ZeroTier allows you to build robust peer-to-peer networks, connetcting all of your devices together. It's very similar to Tailscale.

### Step 1: Sign up for ZeroTier account
[Sign up for a ZeroTier account](https://my.zerotier.com).

### Step 2: Add other devices to your ZeroTier network

You can add devices that you want connected to the ZeroTier network. One device can be connected to multiple networks, so you can even have different networks for different purposes.

It's most likely going to run everywhere you want it, since the software exists for OpenWRT, Desktop Linux, Windows, Android, etc.

[Download ZeroTier](https://www.zerotier.com/download)

### Step 3: Add your device to your network

JELOS Emulation Station has customized UI with ZeroTier support.

- Create a file called "zerotier-networks" in ```/storage/.config/zerotier-networks```, containing one network ID per line
- Press "start" button to go into Emulation Station Main Menu.
- Select Network Settings submenu.
- Select "ZeroTier VPN" and turn it on.
- Select "Back" button to exit setting dialog.

Don't forget to authenticate your device in the ZerTier [control panel](my.zerotier.com) after starting the service. It should show up on the webpage.

You can also use the traditional way of adding a network ID by using ```zerotier-cli join``` through SSH shell, but in this cae the zerotier-networks file shouldn't be present.

### Links
* ZeroTier homepage [link](https://zerotier.com/)
* Script used to add networks on start [link](https://github.com/JustEnoughLinuxOS/distribution/blob/dev/packages/network/zerotier-one/scripts/zerotier-join.sh)