# Setting up GEDIT custom theme on GNOME 47.

1. Install the dependencies.

```bash
sudo pacman -S hspell hunspell nuspell libvoikko
```
2. Create the following directory.

```bash
mkdir -p .local/share/libgedit-gtksourceview-300/styles
```

3. Copy and paste the theme file inside the folder previously created.

4. Custom theme "Tomorrow Night":

[Click here](https://github.com/eloymelo/linux-documentation/blob/main/Miscellaneous/Tomorrow-Night.xml) to download the file.

# Creating an autostart for 1Password

1. Create the following directory.

```bash
mkdir -p ~/.config/autostart
```

2. Create and edit the `1password.desktop` file.

```plaintext
[Desktop Entry]
Type=Application
Exec=1password --silent
Hidden=false
NoDisplay=false
X-GNOME-Autostart-enabled=true
Name[en_US]=1Password
Name=1Password
Comment[en_US]=Start 1Password silently at login
Comment=Start 1Password silently at login
```

3. Save the file.

# Set Nautilus as the default file manager

1. Just run the following

```bash
xdg-mime default org.gnome.Nautilus.desktop inode/directory
```
# Tabstrip on Chromium based browsers.
 
```plaintext
chrome://flags/#scrollable-tabstrip
``` 

# ProtonGE

1. Go to [ProtonGE github page](https://github.com/GloriousEggroll/proton-ge-custom) and download the latest version.

2. Create the **compatibilitytools.d** directory if it does not exist.

```bash
mkdir -p ~/.steam/root/compatibilitytools.d
```

3. After downloading the latest version of ProtonGE, extract it to compatibilitytools.d directory.

```bash
sudo tar -xf GE-ProtonVERSION.tar.gz -C ~/.steam/root/compatibilitytools.d/
```

# Make grub boot linux instead of linux-lts as the default kernel

1. 

```bash
sudo vim /etc/default/grub
```

2. Add the following line:

```plaintext
GRUB_TOP_LEVEL="/boot/vmlinuz-linux"
```

3. Update grub

```bash
sudo grub-mkconfig -o /boot/grub/grub.cfg
```
