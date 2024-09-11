# Simple fix for the broken QT apps theming on GNOME

1. Open terminal and type the following

```bash
sudo apt install qgnomeplatform-qt5
```

```bash
sudo nano /etc/environment
```
2. Then add these lines
```plaintext
# fix for QT broken themes
QT_QPA_PLATFORMTHEME=gnome
```
3. Log out of the session or restart the machine.

4. Done

# Optional

Run this command in order to install "qt5-style-plugins" if you're still facing problems:

Debian:
```bash
sudo apt install qt5-style-plugins
```
Arch:
```bash
sudo pacman -S qt5-styleplugins
```

Or

Just add the following under `/etc/environment`

```plaintext
QT_QPA_PLATFORM=xcb
```