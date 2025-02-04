# Things to do after installing Arch

1. Update the system:

```bash
sudo pacman -Syu
```

2. Install vim (or other text editor)

```bash
sudo pacman -S vim git 
```

3. Open **/etc/pacman.conf** and make the following changes in order to improve the overall experience.

```bash
sudo vim /etc/pacman.conf
```

4. Remove the **#** from **Color** and **ParallelDownloads**. 

```plaintext
# Misc options
#UseSyslog
Color
#NoProgressBar
CheckSpace
#VerbosePkgLists
ParallelDownloads = 5
```

5. Update the system:
```bash
sudo pacman -Sy
```

6. Install **reflector** so you can get the most up-to-date mirrors. You can also choose the mirrors by country if you want.

```bash
sudo pacman -S reflector
```

Create a backup of the **mirrorlist** file.

```bash
sudo cp /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.bak
```

Run this command to get top 10 fastest servers and to also add them to the **mirrorlist**.

```bash
sudo reflector --verbose --download-timeout 20 --latest 10 --protocol https --sort rate --save /etc/pacman.d/mirrorlist
```

You can also set by the country adding the **--country "name-of-the-country"** argument.

e.g.: --country "Brazil"

```bash
sudo reflector --verbose --country "Brazil" --download-timeout 20 --latest 10 --protocol https --sort rate --save /etc/pacman.d/mirrorlist
```

Updated pacman by running this command:

```bash
sudo pacman -Sy
```

7. Install a desktop environment (if you have installed Arch with the minimal option)

```bash
sudo pacman -S gnome
```
Enable and start GDM (GNOME display manager)

```bash
sudo systemctl enable gdm && sudo systemctl start gdm
```

8. Create user directory folders.

```bash
sudo pacman -S xdg-user-dirs
```

```bash
xdg-user-dirs-update
```

9. Install some important tools.

```bash
sudo pacman -S p7zip unrar tar rsync git fastfetch htop exfat-utils fuse-exfat ntfs-3g flac jasper aria2 qemu-full virt-manager dnsmasq 
```

Bluetooth:

```bash
sudo pacman -S bluez bluez-utils
```
```bash
sudo modprobe btusb
```
```bash
sudo systemctl enable bluetooth && sudo systemctl start bluetooth
```

Java:

```bash
sudo pacman -S jdk-openjdk
```

Microcode (choose amd-ucode or intel-ucode):

```bash
sudo pacman -S amd-ucode
```

Update grub:

```bash
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

10. Install Flatpak

Flatpak:

```bash
sudo pacman -S flatpak
```

11. Install **paccache** to automatically clean package cache.

You can check the size of your package cache by running this command:

```bash
du -sh /var/cache/pacman/pkg/
```

To install **paccache**, run: 

```bash
sudo pacman -S pacman-contrib
```

Enable the service:

```bash
sudo systemctl enable paccache.timer
```

12. Install NVIDIA driver.

For standard linux kernel:
```bash
sudo pacman -S nvidia
```
For linux-lts kernel:
```bash
sudo pacman -S nvidia-lts
```
Or

For the nvidia-open driver
```bash
sudo pacman -S nvidia-open
```

13. Install yay

Yay:

```bash
sudo pacman -S --needed base-devel git
```

```bash
git clone https://aur.archlinux.org/yay.git
```

```plaintext
cd yay
makepkg -si
```

14. Install **Preload**.

```bash
yay -S preload
```

```bash
sudo systemctl enable preload && sudo systemctl start preload
```

15. Install essential packages.

```bash
sudo pacman -S enchant mythes-en ttf-liberation noto-fonts hunspell-en_US ttf-bitstream-vera pkgstats adobe-source-sans-pro-fonts gst-plugins-good ttf-droid ttf-dejavu aspell-en icedtea-web gst-libav ttf-ubuntu-font-family ttf-anonymous-pro jre8-openjdk languagetool libmythes hspell hunspell nuspell libvoikko vulkan-radeon papirus-icon-theme gnome-tweaks gnome-themes-extra
```

16. Set up the firewall.

Click [here](https://github.com/eloymelo/linux-documentation/blob/main/Firewall/firewall-settings.md) and follow the steps.

17. Make the fonts look better.

Click [here](https://github.com/eloymelo/linux-documentation/blob/main/Fonts/fonts.md) and follow the steps.
