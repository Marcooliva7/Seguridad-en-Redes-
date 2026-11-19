## Descripción
Can you crack the password to get the flag?

Download the password checker [here](https://artifacts.picoctf.net/c/18/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/18/level3.hash.bin) in the same directory too.

There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.
## Solución
```
==========================================================================

Welcome to the CyLab Security Academy webshell!
XlayersCeboso-academy@webshell:~$ wget https://artifacts.picoctf.net/c/18/level3.py
--2026-08-26 17:02:18--  https://artifacts.picoctf.net/c/18/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.95, 3.160.5.40, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py                                                  100%[========================================================================================================================================>]   1.31K  --.-KB/s    in 0s      

2026-08-26 17:02:18 (809 MB/s) - 'level3.py' saved [1337/1337]

XlayersCeboso-academy@webshell:~$ wget https://artifacts.picoctf.net/c/18/level3.flag.txt.enc
--2026-08-26 17:02:26--  https://artifacts.picoctf.net/c/18/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.40, 3.160.5.18, 3.160.5.95, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc                                        100%[========================================================================================================================================>]      31  --.-KB/s    in 0s      

2026-08-26 17:02:26 (18.6 MB/s) - 'level3.flag.txt.enc' saved [31/31]

XlayersCeboso-academy@webshell:~$ wget https://artifacts.picoctf.net/c/18/level3.hash.bin
--2026-08-26 17:02:37--  https://artifacts.picoctf.net/c/18/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.40, 3.160.5.64, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin                                            100%[========================================================================================================================================>]      16  --.-KB/s    in 0s      

2026-08-26 17:02:37 (585 KB/s) - 'level3.hash.bin' saved [16/16]

XlayersCeboso-academy@webshell:~$ tail level3.py



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"]

XlayersCeboso-academy@webshell:~$ python3 level3.py 
Please enter correct password for flag: 8799
That password is incorrect
XlayersCeboso-academy@webshell:~$ python3 level3.py 
Please enter correct password for flag: d3ab 
That password is incorrect
XlayersCeboso-academy@webshell:~$ python3 level.py
python3: can't open file '/home/XlayersCeboso-academy/level.py': [Errno 2] No such file or directory
XlayersCeboso-academy@webshell:~$ python3 levele3.py
python3: can't open file '/home/XlayersCeboso-academy/levele3.py': [Errno 2] No such file or directory
XlayersCeboso-academy@webshell:~$ python3 level3.py
Please enter correct password for flag: 6f3d
That password is incorrect
XlayersCeboso-academy@webshell:~$ python3 level3.py
Please enter correct password for flag: a9de
That password is incorrect
XlayersCeboso-academy@webshell:~$ python3 level3.py
Please enter correct password for flag: acaf
That password is incorrect
XlayersCeboso-academy@webshell:~$ python3 level3.py
Please enter correct password for flag: 1ea2
That password is incorrect
XlayersCeboso-academy@webshell:~$ python3 level3.py
Please enter correct password for flag: 2295
Welcome back... your flag, user:
academy{m45h_fl1ng1ng_f684152a}
```
```

```

## Notas Adicionales

## Referencias
-- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)