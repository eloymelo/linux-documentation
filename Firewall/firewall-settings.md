<h1>Setting up Uncomplicated Firewall (UWF)</h1>

1. You can install it using your package manager

    Arch: 
        
        sudo pacman -S ufw

    Debian:

        sudo apt install ufw

    Fedora:

        sudo dnf install ufw

2. Now use these recommended rules:

        sudo ufw limit 22/tcp
        sudo ufw allow 80/tcp
        sudo ufw allow 443/tcp
        sudo ufw default deny incoming
        sudo ufw default allow outgoing
        sudo ufw enable

3. If you are using the application LocalSend, also run this:

        sudo ufw allow 53317

    This will allow localsend to work properly with the ufw rules above.

4. Done.