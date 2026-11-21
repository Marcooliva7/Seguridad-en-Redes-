## Descripción
It seems that another encrypted message has been intercepted. The encryptor seems to have learned their lesson though and now there isn't any punctuation! Can you still crack the cipher? Download the message [here](https://challenge-files.cylabacademy.net/library/696c6874056837b137b48e23a74d72e27d26def4454fdb690063e6baefa68124/message.txt).

1.- Try refining your frequency attack, maybe analyzing groups of letters would improve your results?
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/substitution2
cd ~/substitution2
wget -O message.txt 'https://challenge-files.cylabacademy.net/library/696c6874056837b137b48e23a74d72e27d26def4454fdb690063e6baefa68124/message.txt'
nano exp.py
--2026-10-22 01:52:00--  https://challenge-files.cylabacademy.net/library/696c6874056837b137b48e23a74d72e27d26def4454fdb690063e6baefa68124/message.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.37, 13.226.187.66, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1288 (1.3K) [application/octet-stream]
Saving to: ‘message.txt’

message.txt                                                100%[=======================================================================================================================================>]   1.26K  --.-KB/s    in 0s      

2026-10-22 01:52:00 (27.8 MB/s) - ‘message.txt’ saved [1288/1288]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/substitution2]
└─$ python3 exp.py 
academy{N6R4M_4N41Y515_15_73D10U5_9F106B2E}
```
```

```

## Notas Adicionales

## Referencias