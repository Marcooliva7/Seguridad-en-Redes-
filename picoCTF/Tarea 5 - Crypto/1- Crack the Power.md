## Descripción
We received an encrypted message. The modulus is built from primes large enough that factoring them isn’t an option, at least not today. See if you can make sense of the numbers and reveal the flag. Download the [message](https://challenge-files.cylabacademy.net/library/045cb85019ff34b1046bdea29511114f0f635e533109dc1b88bb3bc42b39658d/message.txt).

1.- When certain values in the encryption setup are smaller than usual, it opens up unexpected shortcuts to recover the plaintext

2.- Consider whether you can invert the encryption without factoring `n`.

3.- Read more about Coppersmith's_attack [here](https://en.wikipedia.org/wiki/Coppersmith's_attack)
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/crack-the-power
cd ~/crack-the-power
wget -O message.txt 'https://challenge-files.cylabacademy.net/library/045cb85019ff34b1046bdea29511114f0f635e533109dc1b88bb3bc42b39658d/message.txt'

--2026-10-22 01:24:45--  https://challenge-files.cylabacademy.net/library/045cb85019ff34b1046bdea29511114f0f635e533109dc1b88bb3bc42b39658d/message.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.22, 13.226.187.40, 13.226.187.37, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2398 (2.3K) [application/octet-stream]
Saving to: ‘message.txt’

message.txt                                                100%[=======================================================================================================================================>]   2.34K  --.-KB/s    in 0s      

2026-10-22 01:24:46 (55.9 MB/s) - ‘message.txt’ saved [2398/2398]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/crack-the-power]
└─$ nano exp.py
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/crack-the-power]
└─$ python3 exp.py 
  File "/home/kali/crack-the-power/exp.py", line 5
    n = 0x...  # Valor del módulo N
         ^
SyntaxError: invalid hexadecimal literal
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/crack-the-power]
└─$ nano expa.py  
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/crack-the-power]
└─$ python3 expa.py 
academy{t1ny_e_d6b18b0b}
```
```

```

## Notas Adicionales
- El ataque de Coppersmith describe una clase de ataques criptográficos contra el criptosistema de clave pública RSA basados ​​en el método de Coppersmith . Algunas aplicaciones particulares del método de Coppersmith para atacar RSA incluyen casos en los que el exponente público e es pequeño o cuando se dispone de información parcial sobre un factor primo de la clave secreta.
## Referencias
- [https://en.wikipedia.org/wiki/Coppersmith's_attack](https://en.wikipedia.org/wiki/Coppersmith's_attack)