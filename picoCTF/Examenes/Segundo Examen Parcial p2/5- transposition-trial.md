## Descripción
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message. Download the corrupted message [here](https://challenge-files.cylabacademy.net/library/304dc08e455ad3c33cf532bb41f44a7e939e8e2ad161d9c9012b8375dee48829/message.txt).

1.- Split the message up into blocks of 3 and see how the first block is scrambled
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf-crypto/05-transposition-trial
cd ~/picoctf-crypto/05-transposition-trial
wget -O message.txt 'https://challenge-files.cylabacademy.net/library/304dc08e455ad3c33cf532bb41f44a7e939e8e2ad161d9c9012b8375dee48829/message.txt'
cat message.txt
--2026-10-26 23:52:28--  https://challenge-files.cylabacademy.net/library/304dc08e455ad3c33cf532bb41f44a7e939e8e2ad161d9c9012b8375dee48829/message.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.22, 13.226.187.40, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.37|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 54 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                  100%[=============================================>]      54  --.-KB/s    in 0s      

2026-10-26 23:52:29 (161 MB/s) - ‘message.txt’ saved [54/54]

heTfl g as icaaemd{7y4NRP051N5_16_35P3X51N3_V1CCA2B2}A                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/05-transposition-trial]
└─$ nano exp.py
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/05-transposition-trial]
└─$ python3 exp.py

academy{7R4N5P051N6_15_3XP3N51V3_27F6D45C}
```
```

```

## Notas Adicionales
- Conserva los espacios del archivo, porque también forman parte de los bloques de tres caracteres.
## Referencias
