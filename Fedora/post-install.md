# A couple of tweaks for a fresh Fedora install

1. **Make DNF faster by adding these lines in `/etc/dnf/dnf.conf`**

```plaintext
# DNF config
fastestmirror=True
max_parallel_downloads=10
defaultyes=True
keepcache=True
```

2. **Update your system**
```bash
sudo dnf update
```
3. **Enable RPM Fusion**

```bash
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```

[Source](https://rpmfusion.org/Configuration)

4. **Switch to full ffmpeg**

```bash
sudo dnf swap ffmpeg-free ffmpeg --allowerasing
```
[Source](https://rpmfusion.org/Howto/Multimedia)

5. **Enable Flatpaks**

```bash
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

[Source](https://flatpak.org/setup/Fedora)

6. **Install media plugins**

```bash
sudo dnf group install Multimedia
```
[Source](https://docs.fedoraproject.org/en-US/quick-docs/installing-plugins-for-playing-movies-and-music/)

7. **Enable video thumbnails**

```bash
sudo dnf install ffmpegthumbnailer
```

8. **Enable HEIC image support**

```bash
sudo dnf install heif-pixbuf-loader
``` 
```bash
sudo dnf install libheif-freeworld
```

9. **Change Hostname of the machine**
```bash
sudo hostnamectl set-hostname "New_Custom_Name"
```

10. **Make fonts look better**

Follow this [guide](https://github.com/eloymelo/linux-documentation/blob/main/Fonts/fonts.md) under fonts documentation and this [guide](https://github.com/eloymelo/linux-documentation/blob/main/Fedora/fonts.md) as well.