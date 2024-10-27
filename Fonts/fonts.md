# Steps to get better font rendering on Linux

1. Install the Microsoft Fonts.

Arch based (choose one of the following):
```bash
yay -S ttf-ms-fonts 
yay -S ttf-ms-win11-auto
yay -S ttf-ms-win10-auto
```

Debian based:
```bash    
sudo apt install ttf-mscorefonts-installer -y
```
Fedora:
```bash    
sudo dnf install curl cabextract xorg-x11-font-utils fontconfig -y
```
```bash
sudo rpm -i https://downloads.sourceforge.net/project/mscorefonts2/rpms/msttcore-fonts-installer-2.6-1.noarch.rpm
```

# Using Ubuntu fonts

1. Install Font-Manager and install Ubuntu font.

Debian:
```bash
sudo apt install font-manager
```
Fedora:
```bash
sudo dnf install font-manager
```
Arch:
```bash
sudo pacman -S font-manager
```
2. Open Gnome Tweaks and set the following:
```plaintext 
Interface Text: Ubuntu
Document Text: Ubuntu
Monospace Text: MesloLGS NF
    
Rendering (Hinting):
        
Slight

Antialiasing:

Subpixel (for LCD screens)
```

# Optional
Using the FREETYPE_PROPERTIES option for bolder fonts (less pixelated):

1. Enter the following command in the terminal:
```bash
sudo nano /etc/environment
```
2. Now that you are in edit mode, type the following parameters:
```plaintext
FREETYPE_PROPERTIES="cff:no-stem-darkening=0 autofitter:no-stem-darkening=0"
```
3. Ctrl + O to save it and then Ctrl + X to close the nano editor.

4. Done
