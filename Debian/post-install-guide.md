# A Couple of tweaks to apply after installing debian stable

1. **Enable contrib and non-free sources**

    Using the terminal, edit the following file, add the "contrib" and "non-free" sources, or replace with these lines:

    ```plaintext
    sudo vim /etc/apt/sources.list
    ```

    ```plaintext
    deb http://deb.debian.org/debian bookworm main contrib non-free non-free-firmware
    deb-src http://deb.debian.org/debian bookworm main contrib non-free non-free-firmware

    deb http://deb.debian.org/debian-security/ bookworm-security main contrib non-free non-free-firmware
    deb-src http://deb.debian.org/debian-security/ bookworm-security main contrib non-free non-free-firmware

    deb http://deb.debian.org/debian bookworm-updates main contrib non-free non-free-firmware
    deb-src http://deb.debian.org/debian bookworm-updates main contrib non-free non-free-firmware
    ```

2. **Enable bookworm backports**

    Again, using the terminal, edit the file **/etc/apt/sources.list** and add the following lines:

    ```plaintext
    # bookworm-backports
    deb http://deb.debian.org/debian bookworm-backports main contrib non-free
    deb-src http://deb.debian.org/debian bookworm-backports main contrib non-free
    ```

3. **Update the package manager**

    ```bash
    sudo apt update
    ```

4. **Enable 32bit packages**

    ```bash
    sudo dpkg --add-architecture i386 && sudo apt update
    ```

5. **Enable Flatpak support**

    ```bash
    sudo apt install flatpak
    ```
    ```bash
    sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
    ```
    ```bash
    sudo apt install gnome-software-plugin-flatpak
    ```

6. **Install and configure Virtual Manager**

    ```bash
    sudo apt install qemu-system libvirt-daemon-system virt-manager
    ```

    Using `vim` (or any other text editor), open `libvirtd.conf` and enable these two lines:

    ```bash
    sudo vim /etc/libvirt/libvirtd.conf
    ```

    ```plaintext
    unix_sock_group = "libvirt"
    unix_sock_rw_perms = "0770"
    ```

    Start and enable the libvirtd service:

    ```bash
    sudo systemctl enable libvirtd && sudo systemctl start libvirtd
    ```

    Add your user to the libvirt group by typing this command:

    ```bash
    sudo usermod -a -G libvirt $(whoami)
    ```

    Start the default network and enable autostart:

    ```bash
    sudo virsh net-start default
    sudo virsh net-autostart --network default
    ```

7. **Fix slow shutdown**

    Edit `system.conf` and change the default value from 90s to 15s (or 10s):

    ```bash
    sudo vim /etc/systemd/system.conf
    ```
    ```plaintext
    DefaultTimeoutStopSec=15s
     ```

8. **Remove all pre-installed GNOME games**

    Run:

    ```bash
    sudo apt purge iagno lightsoff four-in-a-row gnome-robots pegsolitaire gnome-2048 hitori gnome-klotski gnome-mines gnome-mahjongg gnome-sudoku quadrapassel swell-foop gnome-tetravex gnome-taquin aisleriot gnome-chess five-or-more gnome-nibbles tali
    sudo apt autoremove
    ```

    Or just run:

    ```bash
    sudo apt purge gnome-games
    ```

9. **Fix broken QT application theme**

    Follow the steps covered under the [GNOME documentation](https://github.com/eloymelo/linux-documentation/tree/main/GNOME).

10. **Fonts configuration guide**

    Follow the fonts configuration guide to make your fonts look better and to install Microsoft fonts (needed for some applications and websites to work properly):

    [Click here to go direct to the guide](https://github.com/eloymelo/linux-documentation/blob/main/Debian/fonts-configuration.md)

11. **Set up firewall**

    Follow the steps [here](https://github.com/eloymelo/linux-documentation/blob/main/Firewall/firewall-settings.md)
