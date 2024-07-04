<h2>Steps to get better font rendering on Linux</h2>

<h3>Install the Microsoft Fonts.</h3>

1. Debian based:
    
        sudo apt install ttf-mscorefonts-installer -y

2. Fedora:
    
        sudo dnf install curl cabextract xorg-x11-font-utils fontconfig -y

        sudo rpm -i https://downloads.sourceforge.net/project/mscorefonts2/rpms/msttcore-fonts-installer-2.6-1.noarch.rpm

3. Arch based (Choose one of the following):

        yay -S ttf-ms-fonts 
        yay -S ttf-ms-win11-auto
        yay -S ttf-ms-win10-auto


<h3>Using Ubuntu fonts</h3>

1. Install Font-Manager and install Ubuntu font.

    Debian:

        sudo apt install font-manager

    Fedora:

        sudo dnf install font-manager

    Arch:

        sudo pacman -S font-manager

2. Open Gnome Tweaks and set the following:

    Fonts
        
        Interface Text: Ubuntu
        Document Text: Ubuntu
        Monospace Text: Monospace
    
    Rendering (Hinting)
        
        None
    
    Antialiasing

        Standard (grayscale)



<h3>Using the FREETYPE_PROPERTIES option for bolder fonts (less pixelated):</h3>

1. Enter the following command in the terminal:

        sudo nano /etc/environment

2. Now that you are in edit mode, type the following parameters:

        FREETYPE_PROPERTIES="cff:no-stem-darkening=0 autofitter:no-stem-darkening=0"

3. Ctrl + O to save it and then Ctrl + X to close the nano editor.

4. Be happy ((: