## Descripción
This is a really weird text file. Can you find the flag? Get the flag from [TXT](https://challenge-files.cylabacademy.net/library/a5d365fedad883763fb28c78e25a1765220bef6501848c84f2a7a7adf74d83cd/flag.txt).

1.- How do operating systems know what kind of file it is? (It's not just the ending!)

2.- Make sure to submit the flag as academy{XXXXX}
## Solución
```
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/a5d365fedad883763fb28c78e25a1765220bef6501848c84f2a7a7adf74d83cd/flag.txt    
--2026-09-28 13:15:24--  https://challenge-files.cylabacademy.net/library/a5d365fedad883763fb28c78e25a1765220bef6501848c84f2a7a7adf74d83cd/flag.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.37, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15696 (15K) [application/octet-stream]
Saving to: ‘flag.txt’

flag.txt                                                   100%[=======================================================================================================================================>]  15.33K  --.-KB/s    in 0.001s  

2026-09-28 13:15:24 (16.5 MB/s) - ‘flag.txt’ saved [15696/15696]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ file flag.txt    
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ open flag.txt        
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ xxd -l 100 flag.txt     
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 06a1 0000 0260 0802 0000 0085 ad5e  .......`.......^
00000020: 9a00 0000 0173 5247 4200 aece 1ce9 0000  .....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 0000 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f000 003c e549 4441 5478 daed dd77  R$...<.IDATx...w
00000060: 8015 d5a1                                ....
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ open flag.txt 
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ mv flag.txt flag.png                            
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ open flag.png 


academy{now_you_know_about_extensions}
```
```

```

## Notas Adicionales
MV sirve para renombrar archivos, en este caso sirvió para cambiar la extensión txt por png.

## Referencias
## Referencias
