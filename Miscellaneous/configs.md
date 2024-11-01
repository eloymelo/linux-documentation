# Setting up GEDIT custom theme on GNOME 47.

1. Install the dependencies.

```bash
sudo pacman -S hspell hunspell nuspell libvoikko
```
2. Create the following directory.

```bash
mkdir -p .local/share/libgedit-gtksourceview-300/styles
```

3. Copy and paste the theme file inside the folder we previously created.

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