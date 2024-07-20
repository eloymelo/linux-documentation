# A couple of tweaks for a fresh Fedora install

1. Make DNF faster by add theses lines in /etc/dnf/dnf.conf

```plaintext
#DNF Config
fastestmirror=True
max_parallel_downloads=10
defaultyes=True
keepcache=True
```

2. Update your system
```bash
sudo dnf update
```
3. Enable RPM Fusion

[RPM Fusion Website](https://rpmfusion.org/Configuration)

4. Enable Flatpaks

[Flatpak Website](https://flatpak.org/setup/Fedora)

5. Change Hostname of the machine
```bash
sudo hostnamectl set-hostname "New_Custom_Name"
```

