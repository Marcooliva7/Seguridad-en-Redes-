## Descripción
Oops! I have a typo in my first message so i sent it again! I used RSA twice so this is secure right? [chall.py](https://challenge-files.cylabacademy.net/library/d33371f1a01fd9671ac08d9ce0a486325fd0e8ed66ce83fc97ee9a5a07a64cb9/chall.py) [output.txt](https://challenge-files.cylabacademy.net/library/d33371f1a01fd9671ac08d9ce0a486325fd0e8ed66ce83fc97ee9a5a07a64cb9/output.txt)

1.- How are the two messages related?

2.- Franklin Reiter _______ _______ attack.
## Solución
```
┌──(entorno)─(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf-crypto/09-related-messages
cd ~/picoctf-crypto/09-related-messages
wget -O chall.py 'https://challenge-files.cylabacademy.net/library/d33371f1a01fd9671ac08d9ce0a486325fd0e8ed66ce83fc97ee9a5a07a64cb9/chall.py'
wget -O output.txt 'https://challenge-files.cylabacademy.net/library/d33371f1a01fd9671ac08d9ce0a486325fd0e8ed66ce83fc97ee9a5a07a64cb9/output.txt'
cat chall.py
cat output.txt
--2026-10-26 23:58:54--  https://challenge-files.cylabacademy.net/library/d33371f1a01fd9671ac08d9ce0a486325fd0e8ed66ce83fc97ee9a5a07a64cb9/chall.py
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.22, 13.226.187.40, 13.226.187.37, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 408 [application/octet-stream]
Saving to: ‘chall.py’

chall.py                     100%[=============================================>]     408  --.-KB/s    in 0s      

2026-10-26 23:58:54 (903 MB/s) - ‘chall.py’ saved [408/408]

--2026-10-26 23:58:54--  https://challenge-files.cylabacademy.net/library/d33371f1a01fd9671ac08d9ce0a486325fd0e8ed66ce83fc97ee9a5a07a64cb9/output.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.22, 13.226.187.40, 13.226.187.66, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1856 (1.8K) [application/octet-stream]
Saving to: ‘output.txt’

output.txt                   100%[=============================================>]   1.81K  --.-KB/s    in 0s      

2026-10-26 23:58:55 (49.9 MB/s) - ‘output.txt’ saved [1856/1856]

from Crypto.Util.number import getPrime, inverse, bytes_to_long, long_to_bytes, GCD

Message = bytes_to_long(b"[redacted]")
Message_fixed = bytes_to_long(b"[redacted]")
e = 0x11
p = getPrime(1024)
q = getPrime(1024)
phi = (p-1) * (q-1)
d = inverse(e, phi)
N = p*q

ciphertext = pow(Message, e, N)
ciphertext2 = pow(Message_fixed, e, N)

print(ciphertext, ciphertext2)
print(Message - Message_fixed)
print(N)
7860045912761396733787151827626577980078289621512234984005839529445593961368363165615482913261313445577614266105220430077936882987309653936618914037675890821869848427651951462864111455091224624017013752923198424235413627033411988371628127559251662511729862890956888355789090360746289972510667449324212113366687952630884079645915870264911389483507931832117188007620470095632420020779606744409188579682888493947359008801656068578817939871469189675626231339108371592861998828230204300202858372124933376359346879893291365980088919013448983078324893849549552032430373288584589130382381436739856712282038348904428689060468
12242541346870441563279267964970728743591932233000595657654560994149472372270512741418951736992335451666500111189959083296476015901548809361700751396332625940085892354023816171318073111224110805072757421795353313124805581222324469403495695192763571684450036123861695845187972213628668282649007172041926793717896049917743779282603119058607412350110498143536518457593592420905209362039604206212704407217478833088416937871504722966727408419148391169520573934094848094018120478728020762106737466117647949093306744454630437866843120406376951084619958051543731724896601868764063192046833255869212513885985482189279940089463
-3
17334845546772507565250479697360218105827285681719530148909779921509619103084219698006014339278818598859177686131922807448182102049966121282308256054696565796008642900453901629937223685292142986689576464581496406676552201407729209985216274086331582917892470955265888718120511814944341755263650688063926284195007148056359887333784052944201212155189546062807573959105963160320187551755272391293705288576724811668369745107148481856135696249862795476376097454818009481550162364943945249601744881676746859305855091288055082626399929893610275614840617858985993338556889612804266896309310999363054134373435198031731045253881
                                                                                                                   
┌──(entorno)─(kali㉿kali)-[~/picoctf-crypto/09-related-messages]
└─$ nano exp.py
                                                                                                                   
┌──(entorno)─(kali㉿kali)-[~/picoctf-crypto/09-related-messages]
└─$ source ~/picoctf-crypto/entorno/bin/activate
python3 exp.py
academy{m3ssage_w1th_typ0}
```
```

```

## Notas Adicionales
- El primer mensaje recuperado termina en `z`; el segundo corrige ese carácter y termina en `}`.
- El script comprueba que ambos mensajes producen sus respectivos cifrados antes de mostrar la bandera.
## Referencias
