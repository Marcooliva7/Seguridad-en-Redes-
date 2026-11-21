## Descripción
A type of transposition cipher is the rail fence cipher, which is described [here](https://en.wikipedia.org/wiki/Rail_fence_cipher). Here is one such cipher encrypted using the rail fence with 4 rails. Can you decrypt it? Download the message [here](https://challenge-files.cylabacademy.net/library/54f070d7a4fbb401b7ae06e5f41a3071cc195039368a58d9c6bb6f5a95b7913c/message.txt).

The decoded message names a phrase. Put that phrase, and nothing else, in the academy flag format: `academy{phrase}`.

1.- Once you've understood how the cipher works, it's best to draw it out yourself on paper
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/rail-fence
cd ~/rail-fence
wget -O message.txt 'https://challenge-files.cylabacademy.net/library/54f070d7a4fbb401b7ae06e5f41a3071cc195039368a58d9c6bb6f5a95b7913c/message.txt'
nano exp.py
--2026-10-22 01:44:48--  https://challenge-files.cylabacademy.net/library/54f070d7a4fbb401b7ae06e5f41a3071cc195039368a58d9c6bb6f5a95b7913c/message.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.66, 13.226.187.22, 13.226.187.40, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.66|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 56 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                                                100%[=======================================================================================================================================>]      56  --.-KB/s    in 0s      

2026-10-22 01:44:48 (124 MB/s) - ‘message.txt’ saved [56/56]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/rail-fence]
└─$ python exp.py                     
The flag is: WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_8CEF1166
academy{WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_8CEF1166}


academy{WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_8CEF1166}
```
```

```

## Notas Adicionales

## Referencias