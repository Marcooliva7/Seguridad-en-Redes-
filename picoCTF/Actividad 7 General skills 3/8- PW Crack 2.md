## Descripción
Can you crack the password to get the flag?

Download the password checker [here](https://artifacts.picoctf.net/c/15/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/15/level2.flag.txt.enc) in the same directory too.

## Solución
## Solución
```
Welcome to the CyLab Security Academy webshell!
XlayersCeboso-academy@webshell:~$ wget https://artifacts.picoctf.net/c/15/level2.py
--2026-08-26 16:53:25--  https://artifacts.picoctf.net/c/15/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.95, 3.160.5.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py                                                  100%[========================================================================================================================================>]     914  --.-KB/s    in 0s      

2026-08-26 16:53:25 (417 MB/s) - 'level2.py' saved [914/914]

XlayersCeboso-academy@webshell:~$ wget 
wget: missing URL
Usage: wget [OPTION]... [URL]...

Try `wget --help' for more options.
XlayersCeboso-academy@webshell:~$ wget https://artifacts.picoctf.net/c/15/level2.flag.txt.enc
--2026-08-26 16:53:49--  https://artifacts.picoctf.net/c/15/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.40, 3.160.5.64, 3.160.5.95, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc                                        100%[========================================================================================================================================>]      31  --.-KB/s    in 0s      

2026-08-26 16:53:49 (463 KB/s) - 'level2.flag.txt.enc' saved [31/31]

XlayersCeboso-academy@webshell:~$ ls
Addadshashanammu        HOLA        big-zip-files      codebook.txt    convertme.py.2  file    files.zip  flag   l                    level2.flag.txt.enc  ltdis.sh.1  static                    static.ltdis.x86_64.txt
Addadshashanammu.zip    HOLA.txt    big-zip-files.zip  convertme.py    enc_flag        file.1  fixme1.py  hola   level1.flag.txt.enc  level2.py            runme.py    static.1                  strings
Addadshashanammu.zip.1  README.txt  code.py            convertme.py.1  enc_flag.1      files   fixme2.py  koala  level1.py            ltdis.sh             salida.txt  static.ltdis.strings.txt  warm
XlayersCeboso-academy@webshell:~$ nano level2.py
XlayersCeboso-academy@webshell:~$ python3 level2.py 
Please enter correct password for flag: 39ce
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_502ec42e}
```
```

```

## Notas Adicionales

## Referencias
-- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)