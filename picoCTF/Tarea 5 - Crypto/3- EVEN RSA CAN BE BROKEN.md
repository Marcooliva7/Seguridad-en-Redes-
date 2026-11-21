## Descripción
This service provides you an encrypted flag. Can you decrypt it with just N & e? Connect to the program with netcat:

`$ nc chatelaine.cylabacademy.net 39887`

The program's source code can be downloaded [here](https://challenge-files.cylabacademy.net/library/742b4d10be646510247831837d9876dafee7f7eb0eea7ee82eaf8f04981ef2d3/encrypt.py).

1.- How much do we trust randomness?

2.- Notice anything interesting about N?

3.- Try comparing N across multiple requests
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/even-rsa
cd ~/even-rsa
nc -w 5 chatelaine.cylabacademy.net 39887 | tee datos.txt
nano exp.py
N: 17296060070990749741891922726449751919157739545114226442366934759825168250496713636237971551084713006079479951982512119572507204508112778910583205345445378
e: 65537
cyphertext: 9655376439288864676190826314994402550041995329143380725267506474989295523741694806632181116593155945032506056197110609543484458036321831840774247627931365
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/even-rsa]
└─$ python3 exp.py 
academy{tw0_1$_pr!m39cf1fb4f}



academy{tw0_1$_pr!m3cfb893a9}
```

```

## Notas Adicionales

## Referencias