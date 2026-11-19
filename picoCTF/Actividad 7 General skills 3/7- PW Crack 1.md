## Descripción
Can you crack the password to get the flag?

Download the password checker [here](https://artifacts.picoctf.net/c/12/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) in the same directory too.

## Solución
```
Welcome to the CyLab Security Academy webshell!
XlayersCeboso-academy@webshell:~$ wget https://artifacts.picoctf.net/c/12/level1.py
--2026-08-26 16:49:20--  https://artifacts.picoctf.net/c/12/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.95, 3.160.5.40, 3.160.5.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                                                  100%[========================================================================================================================================>]     876  --.-KB/s    in 0s      

2026-08-26 16:49:20 (523 MB/s) - 'level1.py' saved [876/876]

XlayersCeboso-academy@webshell:~$ wget https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
--2026-08-26 16:49:28--  https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.64, 3.160.5.18, 3.160.5.40, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc                                        100%[========================================================================================================================================>]      30  --.-KB/s    in 0s      

2026-08-26 16:49:28 (15.9 MB/s) - 'level1.flag.txt.enc' saved [30/30]

XlayersCeboso-academy@webshell:~$ ls      
Addadshashanammu        HOLA        big-zip-files      codebook.txt    convertme.py.2  file    files.zip  flag   l                    ltdis.sh    salida.txt  static.ltdis.strings.txt  warm
Addadshashanammu.zip    HOLA.txt    big-zip-files.zip  convertme.py    enc_flag        file.1  fixme1.py  hola   level1.flag.txt.enc  ltdis.sh.1  static      static.ltdis.x86_64.txt
Addadshashanammu.zip.1  README.txt  code.py            convertme.py.1  enc_flag.1      files   fixme2.py  koala  level1.py            runme.py    static.1    strings
XlayersCeboso-academy@webshell:~$ nano level1.py
XlayersCeboso-academy@webshell:~$ python3 level1.py 
Please enter correct password for flag: 8713
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_1b2fd683}
```
```

```

## Notas Adicionales

## Referencias
-- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)