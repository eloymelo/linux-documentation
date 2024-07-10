<h1>A couple of tweaks for a fresh Fedora install</h1>

1. Make DNF faster by add theses lines in /etc/dnf/dnf.conf

        DNF Config
        fastestmirror=True
        max_parallel_downloads=10
        defaultyes=True
        keepcache=True

2. Update your system

        sudo dnf update

3.Enable RPM Fusion

        https://rpmfusion.org/Configuration

4. Enable Flatpaks

        https://flatpak.org/setup/Fedora

5. Change Hostname of the machine

        sudo hostnamectl set-hostname "New_Custom_Name"


