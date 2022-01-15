# Arch linux

## pacman
 - Update all packages: `pacman -Syu`
 - List all packages: `pacman -Q`
 - List all AUR packages: `pacman -Qm`
 - Remove unneeded dependencies: `pacman -Qtdq | pacman -Rns -`
 - Install previous cached version: `pacman -U /var/cache/pacman/pkg/<file>`

## yay
 - Update all packages (including AUR packages): `yay -Syu` or `yay`
 - Update only AUR packages: `yay -Sua`
 - Get detailed package info: `yay -Si <package>`
 - Edit PKGBUILD before install: `yay -S --editmenu <package>`
 - Remove package and unneeded dependencies: `yay -Rns <package>`
 - Remove unneeded dependencies: `yay -Yc`
 - Get system statistics: `yay -Ps`
 - Clean cache: `yay -Sc`
