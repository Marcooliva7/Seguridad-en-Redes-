## Descripción
A message was encrypted using a shared secret... but it looks like one side of the exchange leaked something. Can you piece together the secret and get the flag? Download the [message](https://challenge-files.cylabacademy.net/library/696a330c92491df25f02f3f20e552a2b8b1b8fd8c5ffc3b3902b972c24638f19/message.txt). And source [code](https://challenge-files.cylabacademy.net/library/696a330c92491df25f02f3f20e552a2b8b1b8fd8c5ffc3b3902b972c24638f19/encryption.py)

1.- What do you get if you combine a public key with a known private one?
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf-crypto/04-shared-secrets                                                           
cd ~/picoctf-crypto/04-shared-secrets
wget -O message.txt 'https://challenge-files.cylabacademy.net/library/696a330c92491df25f02f3f20e552a2b8b1b8fd8c5ffc3b3902b972c24638f19/message.txt'
wget -O encryption.py 'https://challenge-files.cylabacademy.net/library/696a330c92491df25f02f3f20e552a2b8b1b8fd8c5ffc3b3902b972c24638f19/encryption.py'
cat message.txt
cat encryption.py
--2026-10-26 23:50:54--  https://challenge-files.cylabacademy.net/library/696a330c92491df25f02f3f20e552a2b8b1b8fd8c5ffc3b3902b972c24638f19/message.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.22, 13.226.187.37, 13.226.187.40, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1028 (1.0K) [application/octet-stream]
Saving to: ‘message.txt’

message.txt                  100%[=============================================>]   1.00K  --.-KB/s    in 0s      

2026-10-26 23:50:55 (18.3 MB/s) - ‘message.txt’ saved [1028/1028]

--2026-10-26 23:50:55--  https://challenge-files.cylabacademy.net/library/696a330c92491df25f02f3f20e552a2b8b1b8fd8c5ffc3b3902b972c24638f19/encryption.py
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.66, 13.226.187.22, 13.226.187.37, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.66|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1090 (1.1K) [application/octet-stream]
Saving to: ‘encryption.py’

encryption.py                100%[=============================================>]   1.06K  --.-KB/s    in 0s      

2026-10-26 23:50:55 (30.0 MB/s) - ‘encryption.py’ saved [1090/1090]

g = 2
p = 2927273144810939766701580090813587829846998218139050366191650895496341639672151115600622801622875986429173669666450605563086095565809406776099318149676703864803530494465478726922189453273460829331935414785533102652757649572940785971419755291375295328412738229475603220295990344218551730029944293124696567146516090193
A = 573064858108775587796401031506157877018348288426226470285524205679136075971072753567297355763163615870402991691187850746336169042262692610483425859830970803563824285074033597222769345556533666344979747486571381174509140455398567155637545070339870299749606406694126580709457390475875189904723414950764573551900114879
b = 310480984845844782350469929488957103404065672967681721794433968598078606678457574115948893342658016388850300951548689390362586285081923158250912861928954606683971373959652287246659410807804603053375492104235114782698335962292773627028417650732575398422905666599383548621368163602765974099546321049636858616564366046
enc = 43414346474f5b59464a7d5111415011567d16161347401b47475f
import os
import sys

from Crypto.Util.number import getPrime
from random import randint

# Public parameters
g = 2
p = getPrime(1048)

# Server's secret
a = randint(2, p-2)
A = pow(g, a, p)

# Client secret
b = randint(2, p-2)

B = pow(g, b, p)

# Shared key
shared = pow(A, b, p)

# Encrypt flag
flag = b"academy{...}"
enc = bytes([x ^ (shared % 256) for x in flag])

# Write challenge info
#
# You were handed message.txt alongside this script, and this writes that same
# name. Running it here would overwrite the file you have to solve with a fresh
# transcript over the redacted flag above -- a different p and b, and nothing to
# recover. So refuse rather than clobber.
if os.path.exists("message.txt"):
    sys.exit("message.txt already exists here -- that is the file you were given, "
             "and running this would overwrite it. Move it aside first, or run "
             "this somewhere else.")

with open("message.txt", "w") as f:
    f.write(f"g = {g}\n")
    f.write(f"p = {p}\n")
    f.write(f"A = {A}\n")
    f.write(f"b = {b}\n")
    f.write(f"enc = {enc.hex()}\n")
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/04-shared-secrets]
└─$ nano exp.py
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/04-shared-secrets]
└─$ python3 exp.py
academy{dh_s3cr3t_913ddd75}
```
```

```

## Notas Adicionales
- El valor privado `b` filtrado permite reconstruir el secreto compartido.
- En esta instancia, `secreto % 256` produce `34`; ese es el valor utilizado para deshacer XOR.
## Referencias
