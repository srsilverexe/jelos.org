# :material-cube-unfolded: Modifying JELOS

Before modifying JELOS, be sure you can successfully [build](build.md) the unmodified `main` or `dev` branch.  Establish a baseline of success before introducing changes to the JELOS source.

## Building a Single Package

When modifying individual packages, it's useful to regularly verify the build-ability of your changes.  Rather than rebuild an entire device image, it is much faster to simply rebuild a single package using the following commands:

``` bash linenums="1"
make docker-shell
export PROJECT=PC DEVICE=AMD64 ARCH=x86_64
./scripts/clean busybox
./scripts/build busybox
exit
```

PROJECT is one of `Amlogic`, `PC`, or `Rockchip` (i.e. the subdirectories of the project directory).

!!! note "The first and last lines should be omitted if building outside of Docker."

!!! info "If you are interested in an EmulationStation package build it requires additional steps because its source code is located in a separate repository.  Please see instructions [here](https://github.com/JustEnoughLinuxOS/distribution/blob/main/packages/ui/emulationstation/package.mk#L39)."

## Creating a Patch for a Package

It is common to have imported package source code modifed to fit the use case. It's recommended to use a special shell script to build it in case you need to iterate over it. See below.

``` bash linenums="1"
cd sources/wireguard-linux-compat
tar -xvJf wireguard-linux-compat-v1.0.20211208.tar.xz
mv wireguard-linux-compat-v1.0.20211208 wireguard-linux-compat
cp -rf wireguard-linux-compat wireguard-linux-compat.orig

# Make your changes to wireguard-linux-compat
mkdir -p ../../packages/network/wireguard-linux-compat/patches/AMD64
# run from the sources dir
diff -rupN wireguard-linux-compat wireguard-linux-compat.orig >../../packages/network/wireguard-linux-compat/patches/AMD64/mychanges.patch
```

## Creating a Patch for a Package Using git

If you are working with a git repository, building a patch for the distribution is simple.  Rather than using `diff`, use `git diff`.

``` bash linenums="1"
cd sources/emulationstation/emulationstation-098226b/
# Make your changes to EmulationStation
vim/emacs/vscode/notepad.exe
# Make the patch directory
mkdir -p ../../packages/ui/emulationstation/patches
# Run from the sources dir
git diff >../../packages/ui/emulationstation/patches/005-mypatch.patch
```

After the patch is generated, rebuild an individual package by following the section above. The build system will automatically pick up patch files from the `patches` directory. For testing, one can either copy the built binary to the console or burn the whole image on SD card.

## Building a Modified Image

If you already have a build for your device made using the above process, it's simple to shortcut the build process and create an image to test your changes quickly using the process below.

``` bash linenums="1"
make docker-shell

# Update the package version for a new package, or apply your patch as above.
vim/emacs/vscode/notepad.exe

export OS_VERSION=$(date +%Y%m%d) BUILD_DATE=$(date)
export PROJECT=PC DEVICE=AMD64 ARCH=x86_64
./scripts/clean emulationstation
./scripts/build emulationstation
./scripts/install emulationstation
./scripts/image mkimage

exit
```

!!! note "The first and last lines should be omitted if building outside of Docker."

## Pushing Modified Images to a Device

You can of course reflash the SD card with the modified image.

Alternatively, you may install the image through the JELOS update mechanism, which retains your ES and emulator settings.  If the device is networked and reachable from the build machine, this can be done as follows.

``` bash linenums="1"
# Replace with your device values
HOST=192.168.0.123
DEVICE=RK3566
ARCH=aarch64

# Assume today is the same UTC day that the image was built
TIMESTAMP=$(date -u +%Y%m%d)

SSH_OPTS="-o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null"
scp ${SSH_OPTS} ~/distribution/release/JELOS-${DEVICE}.${ARCH}-${TIMESTAMP}.tar root@${HOST}:~/.update && \
    ssh ${SSH_OPTS} root@{HOST} reboot
```

## Common File Locations

Below is a reference for the locations of files you may frequently interact with while modifying JELOS

| File &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Location | Description |
| -- | -- | -- |
| bootloader mkimage | projects/Rockchip/bootloader/mkimage |  |
| busybox package | packages/sysutils/busybox |  |
| init | packages/sysutils/busybox/scripts/init |  |
| kernel config | projects/Rockchip/devices/RK3566-ML/linux/linux.aarch64.conf |  |
| running kernel config | build.JELOS-RK3566-ML.aarch64/linux-6.5-rc7/.config |  |
| boot.scr | projects/Rockchip/devices/RK3566/boot/boot.scr |  |
| uboot package.mk | projects/Rockchip/packages/u-boot/package.mk |  |
| uboot | sources/u-boot/u-boot-976fb2f |  |
| uboot config | sources/u-boot/u-boot-976fb2f/configs/anbernic-rgxx3-rk3566_defconfig |  |
| dts sources | sources/u-boot/u-boot-976fb2f/arch/arm/dts/rk3566-anbernic-rgxx3.dts |  |
| kernel sources/build | build.JELOS-RK3566-ML.aarch64/linux-6.6-rc3 |  |
| final.img | releases |  |
| $EXTRA_CMDLINE | projects/Rockchip/devices/RK3566-ML/options |  |
| $INSTALL | /config $BUILD/image/system, /scripts ${BUILD}/initramfs |  |
| $LE_TEMP | scripts/mkimage mktemp -d -p $TARGET_IMG |  |