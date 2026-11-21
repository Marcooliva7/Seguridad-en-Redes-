## Descripción
We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://challenge-files.cylabacademy.net/library/f3895827512c6fab64095a69942e62ba9e367bb32d70ff69dc0e8fd9a826936a/message.txt).

Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.

Wrap your decrypted message in the academy flag format (i.e. `academy{decrypted_message}`)

1.- Do you know what `mod 37` means?

2.- `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir basicmod1
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ cd basicmod1 
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/basicmod1]
└─$ wget https://challenge-files.cylabacademy.net/library/f3895827512c6fab64095a69942e62ba9e367bb32d70ff69dc0e8fd9a826936a/message.txt
--2026-10-21 12:47:37--  https://challenge-files.cylabacademy.net/library/f3895827512c6fab64095a69942e62ba9e367bb32d70ff69dc0e8fd9a826936a/message.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.22, 13.226.187.37, 13.226.187.40, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 84 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                                                100%[=======================================================================================================================================>]      84  --.-KB/s    in 0s      

2026-10-21 12:47:38 (9.27 MB/s) - ‘message.txt’ saved [84/84]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/basicmod1]
└─$ ls
message.txt
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/basicmod1]
└─$ cat message.txt 
313 396 353 161 336 73 198 406 202 285 57 346 151 332 328 216 214 70 286 360 72 216                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/basicmod1]
└─$ sudo apt install ascii        
[sudo] password for kali: 
Installing:                     
  ascii

Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 948
  Download size: 17.7 kB
  Space needed: 79.9 kB / 59.2 GB available

Get:1 http://kali.download/kali kali-rolling/main amd64 ascii amd64 3.32-2 [17.7 kB]
Fetched 17.7 kB in 1s (11.8 kB/s)
Selecting previously unselected package ascii.
(Reading database… 483340 files and directories currently installed.)
Preparing to unpack …/ascii_3.32-2_amd64.deb…
Unpacking ascii (3.32-2)…
Setting up ascii (3.32-2)…
Processing triggers for man-db (2.13.1-1)…
Processing triggers for kali-menu (2026.3.2)…
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/basicmod1]
└─$ nano exp.py 
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/basicmod1]
└─$ python3 exp.py 
academy{R0UND_N_R0UND_65371195}
```
```

```

## Notas Adicionales

## Referencias
