# Better fonts for Fedora

1. Enable COPR repository:
```bash
sudo dnf copr enable chriscowleyunix/better_fonts -y
```
2. Install packages:
```bash
sudo dnf install fontconfig-font-replacements -y
```
3. (Optional) Enable subpixel (rgb) antialiasing:
```bash
sudo dnf install fontconfig-enhanced-defaults -y
```
4. Log out and log in again or restart computer so the changes can take effect.

Source: https://copr.fedorainfracloud.org/coprs/chriscowleyunix/better_fonts/