## Descripción
Everything seems secure; strong numbers, familiar parameters but something small might ruin it all. Can you recover the message? Download the [message](https://challenge-files.cylabacademy.net/library/6838f6423a4aaa55592ff8b72be8e3453da45539db3e12dc43bc3ba783654be9/message.txt). And source [code](https://challenge-files.cylabacademy.net/library/6838f6423a4aaa55592ff8b72be8e3453da45539db3e12dc43bc3ba783654be9/encryption.py)

1.- This might be a job for Boneh-Durfee.
## Solución
```
┌──(entorno)─(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf-crypto/08-small-trouble
cd ~/picoctf-crypto/08-small-trouble
wget -O message.txt 'https://challenge-files.cylabacademy.net/library/6838f6423a4aaa55592ff8b72be8e3453da45539db3e12dc43bc3ba783654be9/message.txt'
wget -O encryption.py 'https://challenge-files.cylabacademy.net/library/6838f6423a4aaa55592ff8b72be8e3453da45539db3e12dc43bc3ba783654be9/encryption.py'
cat message.txt
cat encryption.py
--2026-10-26 23:57:30--  https://challenge-files.cylabacademy.net/library/6838f6423a4aaa55592ff8b72be8e3453da45539db3e12dc43bc3ba783654be9/message.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.22, 13.226.187.40, 13.226.187.66, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1908 (1.9K) [application/octet-stream]
Saving to: ‘message.txt’

message.txt                  100%[=============================================>]   1.86K  --.-KB/s    in 0s      

2026-10-26 23:57:31 (47.1 MB/s) - ‘message.txt’ saved [1908/1908]

--2026-10-26 23:57:31--  https://challenge-files.cylabacademy.net/library/6838f6423a4aaa55592ff8b72be8e3453da45539db3e12dc43bc3ba783654be9/encryption.py
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.66, 13.226.187.37, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 502 [application/octet-stream]
Saving to: ‘encryption.py’

encryption.py                100%[=============================================>]     502  --.-KB/s    in 0s      

2026-10-26 23:57:31 (13.5 MB/s) - ‘encryption.py’ saved [502/502]

n = 5547674139605244587760717182911518673311419047725141350558004946311344418453877769259457248006935141424285027695909573319661163917492834298454634742454567925396510269772956256967616852359188646442718375943814998047714147262019386007294326660716821849389784781589832589622542734728942755267751863215961111436970623846500065965952752526543369456714602155547940857731060969311872698528408292867566777961383299583379560005955080375231309440361416080143866530425164158997532867839160961107961002284536447653813770804342354505160793611198036455395061121786210168882045796389191492217006238417984078491158217487819937498240326875623502481
e = 4159357498262470485125540817575394525189686670614998704652432501757845634882492314213100316868752285987296720741939791343819202528735764849900902125043514812459371422204416138905505490579853777731866178326119339331107047333980580137267486216710355836080071320980811188419925373425664681452036299949770625344005330997513730864059615747910744374216700320270720922810147645547391619331482259065185492695833049782945822829879764488412200121225384594460600312475036340936700848611054827956802253924732159542345144123939145863606179002488385804394085920326091896432453022253468487188874912253591462907501882851215386316409508359433046165
c = 5509346217981582813410513506305898392379850810526929043252714254508405417252279797404306487242982829750898370253546521596793613824524739985746322107251638420905759599643848539203344710063954517441541943104144906842248148504024708107916989593462693387202901245508530412913345591605278102097073070453968292960378073298094124539617886780903397164865631209147468509900767050067375983110625007138233842462106606109097426177754022776682453013286641375989701392072783876305749625957933468040587293466045614606841350444297546727766643950001058710764900042474986762891948097914213156288506206455487861459269794731040759530920381176362582936
from Crypto.Util.number import getPrime, inverse, bytes_to_long
import random

# Generate two large primes (1048 bits each)
p = getPrime(1048)
q = getPrime(1048)
n = p * q
phi = (p - 1) * (q - 1)

# compute d
d = getPrime(256)

# Compute the public exponent
e = inverse(d, phi)

# Encrypt a flag
flag = b'academy{...}'
m = bytes_to_long(flag)
c = pow(m, e, n)

# Output for the challenge
with open("message.txt", "w") as f:
    f.write(f"n = {n}\n")
    f.write(f"e = {e}\n")
    f.write(f"c = {c}\n")
                                                                                                                   
┌──(entorno)─(kali㉿kali)-[~/picoctf-crypto/08-small-trouble]
└─$ nano exp.py
                                                                                                                   
┌──(entorno)─(kali㉿kali)-[~/picoctf-crypto/08-small-trouble]
└─$ source ~/picoctf-crypto/entorno/bin/activate
python3 exp.py
academy{sm4ll_d_c0409804}
```
```

```

## Notas Adicionales

- Aunque la pista menciona Boneh-Durfee, Wiener funciona con estos datos. El script también comprueba el resultado volviendo a cifrar el mensaje recuperado.
## Referencias
