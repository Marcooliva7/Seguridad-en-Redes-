## Descripción
How about some hide and seek heh? Look at this image [here](https://challenge-files.cylabacademy.net/library/8033762450472ffeea8ef74c4098556d749abc1f4e836b849798e18e9554e5e5/atbash.jpg).

1.- Download the image and try to extract it.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mdkir hidetosee
Command 'mdkir' not found, did you mean:
  command 'mkdir' from deb coreutils
  command 'mdir' from deb mtools
Try: sudo apt install <deb name>
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ mkdir hidetosee
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ cd hidetosee   
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/hidetosee]
└─$ wget https://challenge-files.cylabacademy.net/library/8033762450472ffeea8ef74c4098556d749abc1f4e836b849798e18e9554e5e5/atbash.jpg 
--2026-10-21 13:13:12--  https://challenge-files.cylabacademy.net/library/8033762450472ffeea8ef74c4098556d749abc1f4e836b849798e18e9554e5e5/atbash.jpg
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.66, 13.226.187.37, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.66|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 51491 (50K) [application/octet-stream]
Saving to: ‘atbash.jpg’

atbash.jpg                                                 100%[=======================================================================================================================================>]  50.28K  --.-KB/s    in 0.08s   

2026-10-21 13:13:13 (634 KB/s) - ‘atbash.jpg’ saved [51491/51491]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/hidetosee]
└─$ ls
atbash.jpg
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/hidetosee]
└─$ open atbash.jpg 
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/hidetosee]
└─$ steghide extract -sf atbash.jpg 
Command 'steghide' not found, but can be installed with:
sudo apt install steghide
Do you want to install it? (N/y)y
sudo apt install steghide
[sudo] password for kali: 
Installing:                     
  steghide

Installing dependencies:
  libmcrypt4  libmhash2

Suggested packages:
  libmcrypt-dev  mcrypt

Summary:
  Upgrading: 0, Installing: 3, Removing: 0, Not Upgrading: 948
  Download size: 319 kB
  Space needed: 966 kB / 59.2 GB available

Continue? [Y/n] Y
Get:1 http://http.kali.org/kali kali-rolling/main amd64 libmcrypt4 amd64 2.5.8-8+b2 [71.8 kB]
Get:2 http://http.kali.org/kali kali-rolling/main amd64 libmhash2 amd64 0.9.9.9-11+b1 [93.3 kB]
Get:3 http://http.kali.org/kali kali-rolling/main amd64 steghide amd64 0.5.1+git20240220-2 [154 kB]
Fetched 319 kB in 3s (104 kB/s)                                      
Selecting previously unselected package libmcrypt4:amd64.
(Reading database… 483346 files and directories currently installed.)
Preparing to unpack …/libmcrypt4_2.5.8-8+b2_amd64.deb…
Unpacking libmcrypt4:amd64 (2.5.8-8+b2)…
Selecting previously unselected package libmhash2:amd64.
Preparing to unpack …/libmhash2_0.9.9.9-11+b1_amd64.deb…
Unpacking libmhash2:amd64 (0.9.9.9-11+b1)…
Selecting previously unselected package steghide.
Preparing to unpack …/steghide_0.5.1+git20240220-2_amd64.deb…
Unpacking steghide (0.5.1+git20240220-2)…
Setting up libmhash2:amd64 (0.9.9.9-11+b1)…
Setting up libmcrypt4:amd64 (2.5.8-8+b2)…
Setting up steghide (0.5.1+git20240220-2)…
Processing triggers for libc-bin (2.42-17)…
Processing triggers for man-db (2.13.1-1)…
Processing triggers for kali-menu (2026.3.2)…
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/hidetosee]
└─$ ls                      
atbash.jpg
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/hidetosee]
└─$ steghide extract -sf atbash.jpg
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/hidetosee]
└─$ cat encrypted.txt       
zxzwvnb{zgyzhs_xizxp_zz003u7z}


academy{atbash_crack_02f11bb3}
```
```

```

## Notas Adicionales

## Referencias
- [https://www.google.com/search?q=traduce+esto+a+atbash%3A+zxzwvnb%7Bzgyzhs_xizxp_zz003u7z%7D&rlz=1C1UEAD_enMX1136MX1136&oq=traduce+esto+a+atbash%3A+zxzwvnb%7Bzgyzhs_xizxp_zz003u7z%7D&gs_lcrp=EgZjaHJvbWUyBggAEEUYOdIBCDQ5NjdqMGo3qAIAsAIA&sourceid=chrome&source=chrome.ob&ie=UTF-8](https://www.google.com/search?q=traduce+esto+a+atbash%3A+zxzwvnb%7Bzgyzhs_xizxp_zz003u7z%7D&rlz=1C1UEAD_enMX1136MX1136&oq=traduce+esto+a+atbash%3A+zxzwvnb%7Bzgyzhs_xizxp_zz003u7z%7D&gs_lcrp=EgZjaHJvbWUyBggAEEUYOdIBCDQ5NjdqMGo3qAIAsAIA&sourceid=chrome&source=chrome.ob&ie=UTF-8)