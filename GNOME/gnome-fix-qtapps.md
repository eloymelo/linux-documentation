# Simple fix for the broken QT apps theming on GNOME

Debian:

1. Open terminal and type the following

```bash
sudo apt install qgnomeplatform-solarized-qt5
```

2. Arch:

```bash
sudo yay -S qgnomeplatform-solarized-qt5 qgnomeplatform-solarized-qt6
```
3. Open **`/etc/environment`** and paste the following:

```bash
sudo vim /etc/environment
```

```plaintext
# fix for broken QT themes
QT_QPA_PLATFORM=xcb
```
4. Log out of the session or restart the machine.

5. Done

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
