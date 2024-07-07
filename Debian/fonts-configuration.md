<h1>Tweaks to get better font rendering on Debian</h1>

1. Install the Microsoft Fonts using this command:

        sudo apt install ttf-mscorefonts-installer -y

2. Open or create the <b>fonts.conf</b> file under ~/.config/fontconfig/fonts.conf and paste this setting:

        <?xml version='1.0'?>
        <!DOCTYPE fontconfig SYSTEM 'fonts.dtd'>
        <fontconfig>
            <match target="font">
                <edit mode="assign" name="antialias">
                    <bool>true</bool>
                </edit>
                <edit mode="assign" name="embeddedbitmap">
                    <bool>false</bool>
                </edit>
                <edit mode="assign" name="hinting">
                    <bool>true</bool>
                </edit>
                <edit mode="assign" name="hintstyle">
                    <const>hintslight</const>
                </edit>
                <edit mode="assign" name="lcdfilter">
                    <const>lcddefault</const>
                </edit>
                <edit mode="assign" name="rgba">
                    <const>rgb</const>
                </edit>
            </match>
        </fontconfig>

3. Run these commmands:

        # Reconfigure fontconfig
        sudo dpkg-reconfigure fontconfig-config

        # Regenerate fonts cache
        sudo dpkg-reconfigure fontconfig

4. Reboot your pc.
