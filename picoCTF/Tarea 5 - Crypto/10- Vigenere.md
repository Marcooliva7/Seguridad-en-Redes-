## Descripción
Can you decrypt this message? Decrypt this [message](https://challenge-files.cylabacademy.net/library/1415ede8e9f58b36fddf7b520d73c151a53ac100c476ca97c7a19f9b901100d3/cipher.txt) using this key "CYLAB".

1.- [https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher](https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher)
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/vigenere
cd ~/vigenere
wget -O cipher.txt 'https://challenge-files.cylabacademy.net/library/1415ede8e9f58b36fddf7b520d73c151a53ac100c476ca97c7a19f9b901100d3/cipher.txt'
nano exp.py
--2026-10-22 01:54:32--  https://challenge-files.cylabacademy.net/library/1415ede8e9f58b36fddf7b520d73c151a53ac100c476ca97c7a19f9b901100d3/cipher.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.37, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43 [application/octet-stream]
Saving to: ‘cipher.txt’

cipher.txt                                                 100%[=======================================================================================================================================>]      43  --.-KB/s    in 0s      

2026-10-22 01:54:33 (81.9 MB/s) - ‘cipher.txt’ saved [43/43]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/vigenere]
└─$ python3 exp.py 
academy{D0NT_US3_V1G3N3R3_C1PH3R_y0393es7}

academy{D0NT_US3_V1G3N3R3_C1PH3R_y0393es7}
```
```

```

## Notas Adicionales

## Referencias