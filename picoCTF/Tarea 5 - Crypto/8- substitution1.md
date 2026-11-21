## Descripción
A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again. Download the message [here](https://challenge-files.cylabacademy.net/library/ceba1af4dd4ee542c226922acd536495ebe14c328fb6766ae3244de7d7deaa2e/message.txt).

1.- Try a frequency attack

2.- Do the punctuation and the individual words help you make any substitutions?
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/substitution1
cd ~/substitution1
wget -O message.txt 'https://challenge-files.cylabacademy.net/library/ceba1af4dd4ee542c226922acd536495ebe14c328fb6766ae3244de7d7deaa2e/message.txt'
nano exp.py
--2026-10-22 01:48:50--  https://challenge-files.cylabacademy.net/library/ceba1af4dd4ee542c226922acd536495ebe14c328fb6766ae3244de7d7deaa2e/message.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.22, 13.226.187.66, 13.226.187.40, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 638 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                                                100%[=======================================================================================================================================>]     638  --.-KB/s    in 0s      

2026-10-22 01:48:50 (8.63 MB/s) - ‘message.txt’ saved [638/638]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/substitution1]
└─$ python3 exp.py 
CTFs (short for capture the flag) are a type of computer security competition. Contestants are presented with a set of challenges which test their creativity, technical (and googling) skills, and problem-solving ability. Challenges usually cover a number of categories, and when solved, each yields a string (called a flag) which is submitted to an online scoring service. CTFs are a great way to learn a wide array of computer security skills in a safe, legal environment, and are hosted and played by many security groups around the world for fun and practice. For this problem, the flag is: academy{FR3QU3NCY_4774CK5_4R3_C001_26A742EB}

Bandera: academy{FR3QU3NCY_4774CK5_4R3_C001_0532A335}
```
```

```

## Notas Adicionales

## Referencias