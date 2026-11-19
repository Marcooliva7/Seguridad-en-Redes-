## Descripción
There's something in the [building](https://challenge-files.cylabacademy.net/library/5235bfccd8f3cc2d059ee828f774846542f28f7ec66cb4f0c6ceb536c38026d4/buildings.png). Can you retrieve the flag?

1.- There is data encoded somewhere... there might be an online decoder.
## Solución
```
└─$ wget https://challenge-files.cylabacademy.net/library/5235bfccd8f3cc2d059ee828f774846542f28f7ec66cb4f0c6ceb536c38026d4/buildings.png
--2026-09-28 13:29:22--  https://challenge-files.cylabacademy.net/library/5235bfccd8f3cc2d059ee828f774846542f28f7ec66cb4f0c6ceb536c38026d4/buildings.png
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.66, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 615860 (601K) [application/octet-stream]
Saving to: ‘buildings.png’

buildings.png                                              100%[=======================================================================================================================================>] 601.43K   185KB/s    in 3.3s    

2026-09-28 13:29:26 (185 KB/s) - ‘buildings.png’ saved [615860/615860]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ file buildings.png 
buildings.png: PNG image data, 657 x 438, 8-bit/color RGBA, non-interlaced
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ open buildings.png 
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ xxd -l 100 buildings.png 
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 0291 0000 01b6 0806 0000 0027 6add  .............'j.
00000020: d800 0020 0049 4441 5478 dabc bddf 8b64  ... .IDATx.....d
00000030: 5b9a 1df6 d5ee 3d67 8e62 6282 7038 1c0e  [.....=g.bb.p8..
00000040: d249 92a4 cb45 f972 691a d30c 7a30 c6f8  .I...E.ri...z0..
00000050: 49f8 0ff0 b3ff 0c3d f8c1 e841 08e3 0761  I......=...A...a
00000060: fca0 0723                                ...#
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ pwd buildings.png                   
pwd: too many arguments
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ find / -name "building.png" 2>/dev/null
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ ztegs -a buildings.png | grep academy
ztegs: command not found
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ zsteg -a buildings.png | grep academy
zsteg: command not found
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ zsteg -a buildings.png | grep academy
zsteg: command not found
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ steghide extract -sf buildings.png   
Command 'steghide' not found, but can be installed with:
sudo apt install steghide
Do you want to install it? (N/y)N     
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ zsteg -a buildings.png | grep picoCTF
zsteg: command not found
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ sudo apt insall zsteg             
[sudo] password for kali: 
Error: Invalid operation insall
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ sudo apt insall zsteg
Error: Invalid operation insall
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ 123456789
123456789: command not found
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ sudo apt insall zsteg
Error: Invalid operation insall
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ sudo apt install ruby ruby-dev build-essential libpcap-dev -y

ruby is already the newest version (1:3.3+b1).
ruby set to manually installed.
ruby-dev is already the newest version (1:3.3+b1).
ruby-dev set to manually installed.
build-essential is already the newest version (12.12).
build-essential set to manually installed.
Installing:                 
  libpcap-dev
                                                                                                                                                                                                                                           
Installing dependencies:
  libdbus-1-dev  libpcap0.8-dev  libpkgconf7  libsystemd-dev  pkgconf  pkgconf-bin
                                                                                                                                                                                                                                           
Summary:
  Upgrading: 0, Installing: 7, Removing: 0, Not Upgrading: 0
  Download size: 2,044 kB
  Space needed: 8,582 kB / 61.0 GB available

Get:1 http://kali.download/kali kali-rolling/main amd64 libsystemd-dev amd64 261.2-1 [1,385 kB]
Get:2 http://kali.download/kali kali-rolling/main amd64 libpkgconf7 amd64 2.5.1-4 [47.8 kB]
Get:3 http://kali.download/kali kali-rolling/main amd64 pkgconf-bin amd64 2.5.1-4 [35.9 kB]
Get:4 http://kali.download/kali kali-rolling/main amd64 pkgconf amd64 2.5.1-4 [33.6 kB]
Get:5 http://http.kali.org/kali kali-rolling/main amd64 libdbus-1-dev amd64 1.16.2-5+b1 [213 kB]
Get:6 http://kali.download/kali kali-rolling/main amd64 libpcap0.8-dev amd64 1.10.6-2 [292 kB]
Get:7 http://kali.download/kali kali-rolling/main amd64 libpcap-dev amd64 1.10.6-2 [36.4 kB]
Fetched 2,044 kB in 5s (398 kB/s)        
Selecting previously unselected package libsystemd-dev:amd64.
(Reading database… 433206 files and directories currently installed.)
Preparing to unpack …/0-libsystemd-dev_261.2-1_amd64.deb…
Unpacking libsystemd-dev:amd64 (261.2-1)…
Selecting previously unselected package libpkgconf7:amd64.
Preparing to unpack …/1-libpkgconf7_2.5.1-4_amd64.deb…
Unpacking libpkgconf7:amd64 (2.5.1-4)…
Selecting previously unselected package pkgconf-bin.
Preparing to unpack …/2-pkgconf-bin_2.5.1-4_amd64.deb…
Unpacking pkgconf-bin (2.5.1-4)…
Selecting previously unselected package pkgconf:amd64.
Preparing to unpack …/3-pkgconf_2.5.1-4_amd64.deb…
Unpacking pkgconf:amd64 (2.5.1-4)…
Selecting previously unselected package libdbus-1-dev:amd64.
Preparing to unpack …/4-libdbus-1-dev_1.16.2-5+b1_amd64.deb…
Unpacking libdbus-1-dev:amd64 (1.16.2-5+b1)…
Selecting previously unselected package libpcap0.8-dev:amd64.
Preparing to unpack …/5-libpcap0.8-dev_1.10.6-2_amd64.deb…
Unpacking libpcap0.8-dev:amd64 (1.10.6-2)…
Selecting previously unselected package libpcap-dev:amd64.
Preparing to unpack …/6-libpcap-dev_1.10.6-2_amd64.deb…
Unpacking libpcap-dev:amd64 (1.10.6-2)…
Setting up libpkgconf7:amd64 (2.5.1-4)…
Setting up pkgconf-bin (2.5.1-4)…
Setting up libsystemd-dev:amd64 (261.2-1)…
Setting up pkgconf:amd64 (2.5.1-4)…
Setting up libdbus-1-dev:amd64 (1.16.2-5+b1)…
Processing triggers for libc-bin (2.42-17)…
Processing triggers for man-db (2.13.1-1)…
Processing triggers for sgml-base (1.31+nmu1)…
Processing triggers for kali-menu (2026.3.2)…
Setting up libpcap0.8-dev:amd64 (1.10.6-2)…
Setting up libpcap-dev:amd64 (1.10.6-2)…
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ sudo gem install zsteg

Fetching rainbow-3.1.1.gem
Fetching iostruct-0.7.0.gem
Fetching zsteg-0.2.14.gem
Fetching zpng-0.4.6.gem
Successfully installed rainbow-3.1.1
Successfully installed iostruct-0.7.0
Successfully installed zpng-0.4.6
Successfully installed zsteg-0.2.14
Parsing documentation for rainbow-3.1.1
Installing ri documentation for rainbow-3.1.1
Parsing documentation for iostruct-0.7.0
Installing ri documentation for iostruct-0.7.0
Parsing documentation for zpng-0.4.6
Installing ri documentation for zpng-0.4.6
Parsing documentation for zsteg-0.2.14
Installing ri documentation for zsteg-0.2.14
Done installing documentation for rainbow, iostruct, zpng, zsteg after 0 seconds
4 gems installed
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ zsteg -a buildings.png | grep academy
b1,rgb,lsb,xy       .. text: "academy{h1d1ng_1n_th3_b1t5}"


academy{h1d1ng_1n_th3_b1t5}
```
```

```

## Notas Adicionales
La esteganografía es la técnica que permite ocultar información dentro de otros archivos o portadores de apariencia normal para que su existencia pase totalmente desapercibida.
## Referencias
