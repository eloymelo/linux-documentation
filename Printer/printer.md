# Setting up EPSON printer

1. Execute the following command in order to install the required driver: 

Debian:
```bash
sudo apt install printer-driver-escpr
```
Fedora:
```bash
sudo dnf install epson-inkjet-printer-escpr driver
```
Arch:
```bash
yay -S epson-inkjet-printer-escpr
```
2. Now go to the the following address: 
```plaintext
http://localhost:631
```
then **“Administration”**, **“Add Printer”**, select the printer that you have on your network (mine is the L355) and then it will pop up a list of printers. You can select the printer the best suits you. In my case is the Epson L405 or L455 (preferentially the L405).

3. Done