# TheOneScript
This is a pile of tweaks to speed up Linux installer, please use at your own risk, some code is from other scripts

some parts taken from
https://github.com/Chrysostomus/manjaro-zsh-config

https://github.com/zsh-users/zsh-autosuggestions

https://github.com/benburk/dotfiles/blob/master/arch_install/arch_install.sh

These have there own respective licences, my portition of the script is under the GPL V2, if this is in conflict with any of the other licences please contact me.


--------------------------------------------Use-------------------------------------------------------
For general use just install git and as a regular user (non root) "cd ~/ && wget https://github.com/Vthyarilops/bashscriptsandshit/releases/download/0.1/onescript.tar.gz && tar xvf onescript.tar.gz && cd onescript && ./TheOneScript" for the Arch linux install script, download to any directory after root partition has been mounted, cd to directory, and run as normal. It will automatically copy the OneScriptChroot to /mnt and execute it inside a chroot, once completed if you want ZSH config use general use steps (ie. clone to home folder, skip Arch installer step ofc)


--------------------------------------------IMPORTANT-------------------------------------------------
 If you don't run the script as a user with sudo permissions, it may not find your home folder at ~/ 

 You must place the folder "onescript" in you home directory and run the file "TheOneScript"

 you may be prompted for your root password

-------------------------------------------------------------------------------------------------------


zsh and zsh-syntax-highlightings are required, on ubuntu and related distro's they can be installed with
"sudo apt-get install zsh zsh-syntax-highlightings", the script requires root password as it calls sudo 
move files into /usr/share/zsh/scripts/ and /root/, if any of the commands fail, take note of which ones
and try running them by logging in as root "su -" and running the commands (in order is probably best)
and only the sudo commands (removing the sudo part as you are logged into a root terminal)

-------------------------------------------------------------------------------------------------------

Arch linux notice, the 1st thing this installer has is....well an Arch installer, type N, n , or no and 
hit Return to skip it, this is the only step that doesn't assume its in ~/onescript, so use the installer
then when it finishes (before ZSH config) restart your new install and copy the folder to the correct 
location (home directory /home/$USER/onescript ~/onescript) and rerun the script skipping that part. 
Make sure you run it as a regular user (it uses sudo permissions) or the other tweaks later may not work,

    SO here are the basic steps in Arch installer

    1 - Determine your Hard drive location and partitions ("lsblk -f"), take note of them

    2 - Format/Partition and mount your root partition ("mount /dev/sdX /mnt") replacing /dev/sdX with your root partition
          ie. mount /dev/sda5 /mnt

    3 - If its a UEFI system, mount efi partition to /boot, ie. mkdir /mnt/boot && mount /dev/sda2 /mnt/boot

    3 - establish an internet connection (use "ping www.google.ca" to test it) ("ip link" to list devices and "dhcpcd" followed 
        by device number to use wired connection) ie. dhcpcd enp8s7

    4 - Get install script to your pc untar and execute it, ie. cd /mnt && wget https://github.com/Vthyarilops/bashscriptsandshit/releases/download/0.1/onescript.tar.gz && tar xvf onescript.tar.gz && cd onescript && ./TheOneScript

    Thats it, if you don't understand any of this, Arch probably wouldn't be a good OS for you anyways.
