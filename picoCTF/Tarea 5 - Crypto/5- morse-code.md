## Descripción
Morse code is well known. Can you decrypt this? Download the file [here](https://challenge-files.cylabacademy.net/library/3728bfa4e8314fddd6b7e9f3fae9cb453b459a0bd4b3a29a9224701152f0cd89/morse_chal.wav).

Wrap your answer with academy{}, put underscores in place of pauses, and use all uppercase.

1.- Audacity is a really good program to analyze morse code audio.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/morse-code
cd ~/morse-code
wget -O morse_chal.wav 'https://challenge-files.cylabacademy.net/library/3728bfa4e8314fddd6b7e9f3fae9cb453b459a0bd4b3a29a9224701152f0cd89/morse_chal.wav'
nano exp.py
--2026-10-22 01:43:09--  https://challenge-files.cylabacademy.net/library/3728bfa4e8314fddd6b7e9f3fae9cb453b459a0bd4b3a29a9224701152f0cd89/morse_chal.wav
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.66, 13.226.187.22, 13.226.187.37, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.66|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2549024 (2.4M) [application/octet-stream]
Saving to: ‘morse_chal.wav’

morse_chal.wav                                             100%[=======================================================================================================================================>]   2.43M  2.28MB/s    in 1.1s    

2026-10-22 01:43:11 (2.28 MB/s) - ‘morse_chal.wav’ saved [2549024/2549024]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/morse-code]
└─$ python3 exp.py 
academy{WH47_H47H_90D_W20U9H7}


academy{WH47_H47H_90D_W20U9H7}
```
```

```

## Notas Adicionales

## Referencias