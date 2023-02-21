# Fix Arch Linux Keyrings

Sometimes packages fail to update due to archlinux keyrings reporting bad signatures like this :
`error: archlinux-keyring: signature from "Erich Eckner (just to sign arch packages) <arch@eckner.net>" is unknown trust`
The cause of this is due to the fact that your key management has been messed up. You have gotten behind on updates or have something causing this issue.

## Fixing your Keyrings
### First try this:
```
sudo pacman -Sy archlinux-keyring
sudo pacman -Syu
```

### If it did not work do this:
```
sudo rename /etc/pacman.d/gnupg /etc/pacman.d/gnupg.bak
sudo pacman-key --init
sudo pacman-key --populate archlinux manjaro 
sudo pacman-key --refresh-keys 
sudo pacman -Syu
```
