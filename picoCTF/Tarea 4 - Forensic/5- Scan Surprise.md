## Descripción
1.- QR codes are a way of encoding data. While they're most known for storing URLs, they can store other things too.

2.- Mobile phones have included native QR code scanners in their cameras since version 8 (Oreo) and iOS 11

3.- If you don't have access to a phone, you can also use zbar-tools to convert an image to text
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf/scan-surprise
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ cd ~/picoctf/scan-surprise
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/scan-surprise]
└─$ curl -L --fail --show-error -o challenge.zip 'https://challenge-files.cylabacademy.net/library/28f7fa0ca184e19eeea049b6013ccedc68033a4b7e2e396207048882fd30895e/challenge.zip'
  % Total    % Received % Xferd  Average Speed  Time    Time    Time   Current
                                 Dload  Upload  Total   Spent   Left   Speed
100    741 100    741   0      0   1624      0                              0
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/scan-surprise]
└─$ sudo apt update
[sudo] password for kali: 
Hit:1 http://http.kali.org/kali kali-rolling InRelease
950 packages can be upgraded. Run 'apt list --upgradable' to see them.
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/scan-surprise]
└─$ sudo apt install -y unzip zbar-tools
Upgrading:                      
  libzbar0t64  unzip

Installing:
  zbar-tools

Suggested packages:
  zbarcam-gtk  zbarcam-qt

Summary:
  Upgrading: 2, Installing: 1, Removing: 0, Not Upgrading: 948
  Download size: 352 kB
  Space needed: 113 kB / 59.4 GB available

Get:1 http://kali.download/kali kali-rolling/main amd64 libzbar0t64 amd64 0.23.93-10 [139 kB]
Get:3 http://kali.darklab.sh/kali kali-rolling/main amd64 zbar-tools amd64 0.23.93-10 [37.0 kB]
Get:2 http://us.mirror.ionos.com/linux/distributions/kali/kali kali-rolling/main amd64 unzip amd64 6.0-31 [176 kB]
Fetched 352 kB in 2s (223 kB/s)
(Reading database… 482281 files and directories currently installed.)
Preparing to unpack …/libzbar0t64_0.23.93-10_amd64.deb…
Unpacking libzbar0t64:amd64 (0.23.93-10) over (0.23.93-9+b4)…
Preparing to unpack …/unzip_6.0-31_amd64.deb…
Unpacking unzip (6.0-31) over (6.0-30)…
Selecting previously unselected package zbar-tools.
Preparing to unpack …/zbar-tools_0.23.93-10_amd64.deb…
Unpacking zbar-tools (0.23.93-10)…
Setting up unzip (6.0-31)…
Setting up libzbar0t64:amd64 (0.23.93-10)…
Setting up zbar-tools (0.23.93-10)…
Processing triggers for man-db (2.13.1-1)…
Processing triggers for dbus (1.16.2-5+b1)…
Processing triggers for mailcap (3.77)…
Processing triggers for kali-menu (2026.3.2)…
Processing triggers for libc-bin (2.42-17)…
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/scan-surprise]
└─$ unzip challenge.zip -d extracted
Archive:  challenge.zip
   creating: extracted/home/ctf-player/drop-in/
 extracting: extracted/home/ctf-player/drop-in/flag.png  
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/scan-surprise]
└─$ zbarimg --quiet --raw extracted/home/ctf-player/drop-in/flag.png
academy{p33k_@_b00_36769c4b}


academy{p33k_@_b00_977159d8}
```
```

```

## Notas Adicionales

## Referencias
