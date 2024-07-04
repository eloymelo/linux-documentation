<h1>Simple fix for the broken QT apps theming on GNOME</h1>

First run this command in order to install qt5-style-plugins.

Debian:

        sudo apt install qt5-style-plugins

Arch:

        sudo pacman -S qt5-styleplugins

Now follow theses steps:

1. Open terminal and type the following

        sudo nano /etc/environment

2. Then add these lines

        # fix for GTK broken themes
        QT_QPA_PLATFORM=xcb

3. Log out of the session or restart the machine.
