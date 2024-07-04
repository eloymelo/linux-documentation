<h1>A couple of tweaks to apply after installing Debian stable</h1>

1. Enable contrib and non-free sources.

    Using terminal, edit the following file: <b>/etc/apt/sources.list</b> and add the "contrib" and "non-free" or replace with theses lines:

        deb http://deb.debian.org/debian bookworm main contrib non-free non-free-firmware 
        deb-src http://deb.debian.org/debian bookworm main contrib non-free non-free-firmware

        deb http://deb.debian.org/debian-security/ bookworm-security main contrib non-free non-free-firmware
        deb-src http://deb.debian.org/debian-security/ bookworm-security main contrib non-free non-free-firmware

        deb http://deb.debian.org/debian bookworm-updates main contrib non-free non-free-firmware
        deb-src http://deb.debian.org/debian bookworm-updates main contrib non-free non-free-firmware

2. Enable bookworm backports.

    Again, using the terminal, edit the file in: <b>/etc/apt/sources.list</b> and add the following:

        # bookworm-backports
        deb http://deb.debian.org/debian bookworm-backports main contrib non-free
        deb-src http://deb.debian.org/debian bookworm-backports main contrib non-free 

3. Update the package manager.

        sudo apt update

4. Enable 32bit packages.

        sudo dpkg --add-architecture i386 && sudo apt update

5. Enable flatpak support.

        sudo apt install flatpak
        sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo

6. Install and configure Virtual Manager

        sudo apt install qemu-system libvirt-daemon-system virt-manager

Using nano go to <b>/etc/libvirt/libvirtd.conf</b>. Inside of libvirtd.conf will have to enable these two lines:

        unix_sock_group = "libvirt"
        unix_sock_rw_perms = "0770"

Start and enable the libvirtd service.

        sudo systemctl start libvirtd
        sudo systemctl enable libvirtd

Add your user to the libvirt group by typing this command:

        sudo usermod -a -G libvirt $(whoami)

And at last, start default network and enable autostart

        sudo virsh net-start default
        sudo virsh net-autostart --network default

7. Fix slow shutdown

First you'll have to edit the system.conf and change the default value from 90s to 15s (or 10s):

        sudo nano /etc/systemd/system.conf
        DefaultTimeoutStopSec=15s

9. Remove all pre-installed GNOME games. Run:

        sudo apt purge iagno lightsoff four-in-a-row gnome-robots pegsolitaire gnome-2048 hitori gnome-klotski gnome-mines gnome-mahjongg gnome-sudoku quadrapassel swell-foop gnome-tetravex gnome-taquin aisleriot gnome-chess five-or-more gnome-nibbles tali ; sudo apt autoremove

8. Fix broken QT application theme

Just follow the steps that I have already cover here.

