Better fonts for Fedora

Enable COPR repository:
sudo dnf copr enable chriscowleyunix/better_fonts -y

Install packages:
sudo dnf install fontconfig-font-replacements -y

(Optional) Enable subpixel (rgb) antialiasing:
sudo dnf install fontconfig-enhanced-defaults -y

Log out and log in again or restart computer to see the effect

Source: https://copr.fedorainfracloud.org/coprs/chriscowleyunix/better_fonts/