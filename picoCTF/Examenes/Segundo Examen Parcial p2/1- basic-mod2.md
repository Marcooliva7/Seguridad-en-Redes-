## Descripción
A new modular challenge! Download the message [here](https://challenge-files.cylabacademy.net/library/4f25bc41d739375d13732691063a72f372cc433988ff76ad620c458a792b5c9e/message.txt).

Take each number mod 41 and find the modular inverse for the result. Then map to the following character set: 1-26 are the alphabet, 27-36 are the decimal digits, and 37 is an underscore.

Wrap your decrypted message in the academy flag format (i.e. `academy{decrypted_message}`)

1.- Do you know what the modular inverse is?

2.- The inverse modulo _z_ of _x_ is the number, _y_ that when multiplied by _x_ is 1 modulo _z_

3.- It's recommended to use a tool to find the modular inverses

## Solución
```
┌──(kali㉿kali)-[~]
└─$ sudo apt update
sudo apt install -y wget python3 python3-pip python3-venv libimage-exiftool-perl xxd openssl
[sudo] password for kali: 
Hit:1 http://http.kali.org/kali kali-rolling InRelease 
1085 packages can be upgraded. Run 'apt list --upgradable' to see them.
wget is already the newest version (1.25.0-3).
python3 is already the newest version (3.14.7-3).
python3 set to manually installed.
python3-pip is already the newest version (26.1.2+dfsg-1).
python3-pip set to manually installed.
python3-venv is already the newest version (3.14.7-3).
python3-venv set to manually installed.
libimage-exiftool-perl is already the newest version (13.55+dfsg-1).
xxd is already the newest version (2:9.2.0858-1).
The following package was automatically installed and is no longer required:
  python3.13-tk
Use 'sudo apt autoremove' to remove it.

Upgrading:
  openssl  openssl-provider-legacy
                                                                                                                   
Summary:
  Upgrading: 2, Installing: 0, Removing: 0, Not Upgrading: 1083
  Download size: 1,883 kB
  Space needed: 46.1 kB / 61.2 GB available

Get:1 http://kali.download/kali kali-rolling/main amd64 openssl-provider-legacy amd64 3.6.5-1 [329 kB]
Get:2 http://us.mirror.ionos.com/linux/distributions/kali/kali kali-rolling/main amd64 openssl amd64 3.6.5-1 [1,554 kB]
Fetched 1,883 kB in 2s (806 kB/s)                                                                   
(Reading database… 433241 files and directories currently installed.)
Preparing to unpack …/openssl-provider-legacy_3.6.5-1_amd64.deb…
Unpacking openssl-provider-legacy (3.6.5-1) over (3.6.3-1)…
Setting up openssl-provider-legacy (3.6.5-1)…
(Reading database… 433241 files and directories currently installed.)
Preparing to unpack …/openssl_3.6.5-1_amd64.deb…
Unpacking openssl (3.6.5-1) over (3.6.3-1)…
Setting up openssl (3.6.5-1)…
Processing triggers for man-db (2.13.1-1)…
Processing triggers for kali-menu (2026.3.2)…
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf-crypto
python3 -m venv ~/picoctf-crypto/entorno
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ source ~/picoctf-crypto/entorno/bin/activate
python3 -m pip install pycryptodome owiener sympy
Collecting pycryptodome
  Downloading pycryptodome-4.2.0-cp39-abi3-manylinux2014_x86_64.manylinux_2_17_x86_64.whl.metadata (6.1 kB)
Collecting owiener
  Downloading owiener-1.0.10.tar.gz (4.7 kB)
  Installing build dependencies ... done
  Getting requirements to build wheel ... done
  Preparing metadata (pyproject.toml) ... done
Collecting sympy
  Downloading sympy-1.14.0-py3-none-any.whl.metadata (12 kB)
Collecting mpmath<1.4,>=1.1.0 (from sympy)
  Downloading mpmath-1.3.0-py3-none-any.whl.metadata (8.6 kB)
Downloading pycryptodome-4.2.0-cp39-abi3-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (3.0 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 3.0/3.0 MB 1.4 MB/s  0:00:02
Downloading sympy-1.14.0-py3-none-any.whl (6.3 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6.3/6.3 MB 2.5 MB/s  0:00:02
Downloading mpmath-1.3.0-py3-none-any.whl (536 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 536.2/536.2 kB 3.8 MB/s  0:00:00
Building wheels for collected packages: owiener
  Building wheel for owiener (pyproject.toml) ... done
  Created wheel for owiener: filename=owiener-1.0.10-py3-none-any.whl size=6103 sha256=f599bef0f5c355ebab66800a0de50d93273cb059a088390e14be4b98d9854a61
  Stored in directory: /home/kali/.cache/pip/wheels/cb/fc/35/c4b6c1ba7dea5a05b5bdc167a0e93a78ff1c9e8f5817af952b
Successfully built owiener
Installing collected packages: mpmath, sympy, pycryptodome, owiener
Successfully installed mpmath-1.3.0 owiener-1.0.10 pycryptodome-4.2.0 sympy-1.14.0
                                                                                                                   
┌──(entorno)─(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf-crypto/01-basic-mod2
cd ~/picoctf-crypto/01-basic-mod2
wget -O message.txt 'https://challenge-files.cylabacademy.net/library/4f25bc41d739375d13732691063a72f372cc433988ff76ad620c458a792b5c9e/message.txt'
cat message.txt
--2026-10-26 23:39:07--  https://challenge-files.cylabacademy.net/library/4f25bc41d739375d13732691063a72f372cc433988ff76ad620c458a792b5c9e/message.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.66, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.37|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 90 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                  100%[=============================================>]      90  --.-KB/s    in 0s      

2026-10-26 23:39:08 (159 MB/s) - ‘message.txt’ saved [90/90]

104 126 274 231 262 378 108 352 64 338 77 209 139 441 297 168 158 309 329 415 186 145 186                                                                                                                    
┌──(entorno)─(kali㉿kali)-[~/picoctf-crypto/01-basic-mod2]
└─$ nano exp.py
                                                                                                                   
┌──(entorno)─(kali㉿kali)-[~/picoctf-crypto/01-basic-mod2]
└─$ python3 exp.py    
```
academy{1NV3R53LY_H4RD_471A6111}
``` 
```
```

```

## Notas Adicionales
- Primero se calcula el residuo módulo `41` y después su inverso; ese orden importa.
## Referencias
