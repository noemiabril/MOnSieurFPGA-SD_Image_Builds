# MOnSieurFPGA Pre-Built SD Images

- Pre-built SD images of [**MOnSieurFPGA**](https://github.com/MOnSieurFPGA) for the DE10-Nano using [**MiSTerFPGA**](https://github.com/MiSTer-devel) userspace binaries and [**ArchLinux**](https://archlinux.org) on the armv7h cpu.

- If you choose to compile from source, see [**MOnSieurFPGA-Src_Image_Build**](https://github.com/MOnSieurFPGA/MOnSieurFPGA-Image_Build). For package source information see [**MOnSieurFPGA-Packages**](https://github.com/MOnSieurFPGA/MOnSieurFPGA-Packages). Source files for builds are taken from the [**MiSTerArch**](https://github.com/amstan/MiSTerArch) repo by amstan.

## Why Should I Use MOnSieurFPGA?

- **MOnSieurFPGA** images give the end-user freedom to choose what **THEY** decide to do with the Linux ARM side of **THEIR** DE10-Nano. 

- Will **MOnSieurFPGA** images affect the MiSTerFPGA binaries or make the MiSTerFPGA framework unstable? **NO**. 

- Is **MOnSieurFPGA** intended to replace the MiSTerFPGA distribution setup? **NO**. It is an alternative.

- Will **MOnSieurFPGA** enhance your end-user experience? **YES**.
 
- Here's a few examples why **YOU** might want to checkout **MOnSieurFPGA**!

- The ability to **update** and **add** Linux drivers! Wi-Fi sucks? Not anymore! Free yourself from wired restrictions after initial setup.
   
- Don't want to wait **30 seconds** for your SNES 8GB compressed zip file to open? Rejoice! It's instantaneous! Were you wasting SD/Storage space and uncompressing your files? **NOT ANYMORE**!

- Extend your vintage computer cores by using your favorite open-source tools on **MOnSieurFPGA** and the **SHARED FOLDERS**!
   
- Develop for the MiSTerFPGA platform? Then **MOnSieurFPGA** images are for you. Anything that isn't taxing on the arm7h cpu is now at **YOUR** discretion. Having the ability to add userspace development tools and/or utilities for MiSTerFPGA without using additional devices is great. Maybe you want to make an MegaDrive game? Well, now you can use [**SGDK by Stephane**](https://github.com/Stephane-D/SGDK) and compile the rom on the device you're going to test it on! There's a romantic side about using the device every one's going to be playing on for your vintage software development!

## MOnSieurFPGA Installation

### SD Card Setup

1. Write the [**MOnSieurFPGA**](https://github.com/MOnSieurFPGA/MOnSieurFPGA-SD_Image_Builds/releases/download/MOnSieur-SD_Image/MOnSieur-20220228.img.bz2) image from releases with [**balena-io/etcher**](https://github.com/balena-io/etcher) on your local machine.
 
2. Boot the DE10-Nano with your newly created sd card with a wired internet connection. 
    
3. Follow these steps on your local machine for SSH'ing into the DE10-Nano:

      _**Username/Password**:_

      **LOCAL:**  alarm/alarm  **ROOT:**  root/root
      
     - **`ssh alarm@your.device.ip`** (use alarm password)
     - **`su`** (use root password)
     - **`./setup.sh`**
     
4. Follow the prompts from  **`setup.sh`** and answer **yes** to all. When **`setup.sh`** is completed your device will reboot. You'll see the MiSTerFPGA menu displayed over HDMI or 15KHz depending on your display setup.

   **Notes:**
   - **The  `MiSTer`  binary location is  now **`/user/bin`**  and  **`menu.rbf`**  is located in `/boot/`. The `menu.rbf` is also copied to `/media/fat/`.**
   
   - **Do not edit files in the `/MiSTer/` directory when the SD card is in your DE10-Nano. Instead, use `/media/fat/` only.**
   
   - **Fast USB polling (1000Hz) is enabled by default in `/boot/uboot.txt`.**

### Package Installation

- By default **`setup.sh`** installs the following packages below. Once you've rebooted, there are additional packages to install.

- <b>Pre-Installed Packages:</b>
```rsync lockfile-progs exfat-utils  git go-ipfs networkmanager bluez bluez-utils sudo wget unzip bash cifs-utils ntfs-3g imlib2 freetype2 MiSTer-Devel-Bin MiSTer-Devel-Support MiSTer-Devel-Menu MiSTer-Linux-Addons```

  
- When installing **MOnSieurFPGA** packages for the **first time**, use **`pacman -Sy PackageName —overwrite “*”`**. This will set up the correct paths in **`/media/fat`** for initial packages.

   - Example: **`pacman -Sy MiSTer-Devel-Console —overwrite “*”`**

### How To Enable Wi-Fi

In terminal type the following command `sudo nmtui` and select the preferred network.

## Licensing

Follow the GPLv3 license attached.
