## Bonus: Troubleshooting what went wrong


### Package nightmare
- When trying to run pacstrap, the installation would keep failiing at the openssl package. When this failed, the package manager would stop all downloads as well.
I noticed there was an error stating that the PGP signature was not up to date. After searching around for a bit, it looks like the ISO for Arch linux does not come with updates keys for the package. Prior to running the pacstrap, I ran `pacman -Sy archlinux-keyring` to get an updated version of the keys, and this let pacstrap work as expected

### GPT vs DOS
- Another thing that went wrong was my selection of using GPT over DOS. Orginally I thought this wasn't going to be a big deal, though after going through the installation, I realized that GRUB was not going to be able to use the disk without further configuration. 