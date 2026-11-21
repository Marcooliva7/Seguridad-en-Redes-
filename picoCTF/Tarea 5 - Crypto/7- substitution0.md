## Descripción
A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher? Download the message [here](https://challenge-files.cylabacademy.net/library/0a2e91276318c0f6d400f5096fdaf87fcf57f37ebabf90004552502979a581c8/message.txt).

1.- Try a frequency attack. An online tool might help.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/substitution0
cd ~/substitution0
wget -O message.txt 'https://challenge-files.cylabacademy.net/library/0a2e91276318c0f6d400f5096fdaf87fcf57f37ebabf90004552502979a581c8/message.txt'
nano exp.py
--2026-10-22 01:46:17--  https://challenge-files.cylabacademy.net/library/0a2e91276318c0f6d400f5096fdaf87fcf57f37ebabf90004552502979a581c8/message.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.37, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 670 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                                                100%[=======================================================================================================================================>]     670  --.-KB/s    in 0s      

2026-10-22 01:46:17 (2.95 MB/s) - ‘message.txt’ saved [670/670]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/substitution0]
└─$ python3 exp.py 

Hereupon Legrand arose, with a grave and stately air, and brought me the beetle
from a glass case in which it was enclosed. It was a beautiful scarabaeus, and, at
that time, unknown to naturalists—of course a great prize in a scientific point
of view. There were two round black spots near one extremity of the back, and a
long one near the other. The scales were exceedingly hard and glossy, with all the
appearance of burnished gold. The weight of the insect was very remarkable, and,
taking all things into consideration, I could hardly blame Jupiter for his opinion
respecting it.

The flag is: academy{5UB5717U710N_3V0LU710N_4FBD1EB7}

academy{5UB5717U710N_3V0LU710N_4FBD1EB7}
```
```

```

## Notas Adicionales

## Referencias