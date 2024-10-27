# Setting up Uncomplicated Firewall (UFW)

1. You can install it using your package manager

Arch: 
 ```bash       
sudo pacman -S ufw
```
Debian:
```bash
sudo apt install ufw
```
Fedora:
```bash
sudo dnf install ufw
```
2. Now use these recommended rules:
```bash
sudo ufw limit 22/tcp
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw enable
```
3. If you are using the application LocalSend, also run this:
```bash
sudo ufw allow 53317
```
This will allow localsend to work properly with the ufw rules above.

4. If you are using KDEConnect:

```bash
sudo ufw allow 1714:1764/tcp
sudo ufw allow 1714:1764/udp
```

5. Done.
