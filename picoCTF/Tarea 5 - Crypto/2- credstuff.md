## Descripción
We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it? Download the leak [here](https://challenge-files.cylabacademy.net/library/7f760cee144ac7237469fd6bfab7c748d6f1d101ca47c101187ca7d8f5c721f0/leak.tar).

The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.

1.- Maybe other passwords will have hints about the leak?
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/credstuff
cd ~/credstuff
wget -O leak.tar 'https://challenge-files.cylabacademy.net/library/7f760cee144ac7237469fd6bfab7c748d6f1d101ca47c101187ca7d8f5c721f0/leak.tar'
tar -xf leak.tar
rg -n 'cultiris' leak/usernames.txt
sed -n '378p' leak/passwords.txt
sed -n '378p' leak/passwords.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
--2026-10-22 01:30:36--  https://challenge-files.cylabacademy.net/library/7f760cee144ac7237469fd6bfab7c748d6f1d101ca47c101187ca7d8f5c721f0/leak.tar
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.22, 13.226.187.37, 13.226.187.66, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30720 (30K) [application/octet-stream]
Saving to: ‘leak.tar’

leak.tar                                                   100%[=======================================================================================================================================>]  30.00K  --.-KB/s    in 0s      

2026-10-22 01:30:37 (72.0 MB/s) - ‘leak.tar’ saved [30720/30720]

Command 'rg' not found, but can be installed with:
sudo apt install ripgrep
Do you want to install it? (N/y)y
sudo apt install ripgrep
[sudo] password for kali: 
Installing:                     
  ripgrep

Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 948
  Download size: 1,434 kB
  Space needed: 5,411 kB / 59.2 GB available

Get:1 http://kali.download/kali kali-rolling/main amd64 ripgrep amd64 15.2.0-1 [1,434 kB]
Fetched 1,434 kB in 1s (1,103 kB/s)
Selecting previously unselected package ripgrep.
(Reading database… 483379 files and directories currently installed.)
Preparing to unpack …/ripgrep_15.2.0-1_amd64.deb…
Unpacking ripgrep (15.2.0-1)…
Setting up ripgrep (15.2.0-1)…
Processing triggers for man-db (2.13.1-1)…
Processing triggers for kali-menu (2026.3.2)…
npnqrzl{P7e1S_54I35_71Z3}
academy{C7r1F_54V35_71M3}



academy{C7r1F_54V35_71M3}
```
```

```

## Notas Adicionales

## Referencias