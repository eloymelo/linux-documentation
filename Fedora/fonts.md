<h1>Better fonts for Fedora</h1>

1. Enable COPR repository:

        sudo dnf copr enable chriscowleyunix/better_fonts -y

2. Install packages:

        sudo dnf install fontconfig-font-replacements -y

3. (Optional) Enable subpixel (rgb) antialiasing:

        sudo dnf install fontconfig-enhanced-defaults -y

4. Log out and log in again or restart computer to see the effect

Source: https://copr.fedorainfracloud.org/coprs/chriscowleyunix/better_fonts/