# EndeavourOS-iso-next 

Maintaner: <joekamprad@endeavouros.com> with the help of our beloved community

testings on recreation of ISO from original latest Arch-ISO

* currently not ready, but almost working, a reimplemantation of EndeavourOS changes into latest archiso-framework


## Add and enable EndeavourOS Repository at your system (currently unused)

Add calamares package repo to your /etc/pacman.conf

`[endeavouros_calamares]`\
`SigLevel = PackageRequired`\
`Server = https://github.com/endeavouros-team/mirrors/releases/download/endeavouros_calamares/`

* Uses the same signature that normal repo and has no mirrors package to install.

`sudo pacman -Syy`

## Install necessary packages
`sudo pacman -S archiso mkinitcpio-archiso git squashfs-tools --needed`

Clone:\
`git clone https://github.com/endeavouros-team/iso-next.git`

`cd iso-next`

## Run fix permissions script
`sudo ./fix_permissions.sh`

## Build
`sudo ./mkarchiso /path/to/profile` 

path is where you clone the ISO structure... 

## The iso appears at `out` folder

to install locally builded packages on ISO:
you can do so like that putting the packages inside ISO-next/airootfs/root/ and use this lines:

`#pacman -U --noconfirm /root/calamares_current-3.2.41.1-5-any.pkg.tar.zst`

`#rm /root/calamares_current-3.2.41.1-5-any.pkg.tar.zst`

`#pacman -U --noconfirm /root/calamares_config_next-2.0-4-any.pkg.tar.zst`

`#rm /root/calamares_config_next-2.0-4-any.pkg.tar.zst`
