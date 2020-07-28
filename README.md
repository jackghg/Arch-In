# Arch-In
Arch-In is a **Arch Linux** installer scripts, easy to customize, I hope.\
There are 2 editions:
- ASK: It's a interactive script, it will ask you the installation details. 
- VARS: Fill the variables in the script and run it.

Art-in is still a beta.

## Installation common steps:
- Backup your data !
- Download the last arch iso, flash it to a usb drive, boot it and login as root
- Put the 3 script files in /ai for example by mounting a drive
```
mkdir /ai
mount /dev/sdc1 /ai
cd /ai
```
## Arch-In Ask installation:
- Make the partitions now or in the installer with cfdisk
- Note the partitions path in /dev for boot, system, swap. Data on these partitions will be deleted!
- Start the first part of the installer and follow the instrucions
```
./aisc1
```
- When finished remove the Arch iso and restart
- Login as root, connect to wifi if needed, and start the second part
```
./aisc2
```
- Restart. Review and delete the installer files in /root

## Arch-In Vars installation:
- Make the partitions
- Note the partitions path in /dev for boot, system, swap. Data on these partitions will be deleted!
- Open aiva1 in a text editor and insert the script variables values, on top of the file.
- Copy and paste the variables from aiva1 to aiva2
- Comment the 'exit' command on top of the 3 script files.
- Start the first part of the installer
```
./aiva1
```
- When finished remove the Arch iso and restart
- Login as root, connect to wifi if needed, and start the second part
```
./aiva2
```
- Restart. Review and delete the installer files in /root

## Autoupdate
A very basic auto update will execute `pacman -Syyu && paccache -rk1` every 7 days if you install it. If the update fails, see  the arch linux news, a manual fix may be needed.

## Warnings and limitations
- **Backup** your data before installing Linux !
- Xfce or Lxde (only) can be installed at the moment
- the installer won't connect to **wifi**. Do it manually. Internet is needed at part 2
- home partition and extra partitions won't be mounted. Edit the fstab later
- no encryption
- homed services are disabled by default. I you want to use it, comment the 'systemctl mask' commands in the second script.
