# lmdescrypt
### version 0.98

This script installs Linux Mint Debian Edition (201403) or LMDE2 (201503 and
201701), or regular Linux Mint 17.1, 17.2, 17.3 or 18 and 18.1, either
i686 or amd64, whether with MSDOS or GPT partitions, UEFI or not. The result is:

**A fully LUKS encrypted system, with LVM2 volumes of root and swap (and
optionally: data) with optional boot partition (with optional boot-from-iso-file too).**

* Download shortlink for the script: http://j.mp/lmdescrypt
* Tutorial on Linux Mint community: https://community.linuxmint.com/tutorial/view/2265
* Github page: https://github.com/pepa65/lmdescrypt
* Questions?  solusos@passchier.net or post an Issue on the github page

## INSTRUCTIONS

**1. Boot the Live environment**

**2. Open a Terminal (Menu/Terminal of Ctrl-Alt-T) and enter:**

```
sudo -i
wget j.mp/lmdescrypt
```

**3. If needed, adapt the SETTINGS section:**

```
nano lmdescrypt
```

**4. Make sure all the partitions mentioned in SETTINGS exist.**
For example, (re)partition the drive like this
(erasing all, taking up all space):

```
fdisk /dev/sda
```

Within fdisk, enter the following:
```
 o [Enter]
 n [Enter]
 [Enter]
 [Enter]
 [Enter]
 [Enter]
 w [Enter]
```
This is giving all space to the encrypted lvm2

**5. Start the script:**

```
source lmdescrypt
```

**6. Answer the questions as they come up:**
* set password for encryption

Then after all the preparations have happened:
* set password for user
* set timezone
* configure keyboard

## And that's it!

### Installing into a pre-existing environment

* Using a pre-existing boot-partition, LUKS partition and LVM Logical Volumes is entirely supported.
* Not having a separate boot partition is also supported: total encryption!
* Multiple booting with other OSes also works out of the box.
* MBR, GPT partition tables and UEFI work according to configuration.
