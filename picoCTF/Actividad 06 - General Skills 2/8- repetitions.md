## Descripción
Can you make sense of this file?

Multiple decoding is always good.

## Solución
```
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.95, 3.160.5.40, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 349 [application/octet-stream]
Saving to: 'enc_flag.1'

enc_flag.1                                                 100%[========================================================================================================================================>]     349  --.-KB/s    in 0s      

2026-08-25 02:23:47 (112 MB/s) - 'enc_flag.1' saved [349/349]

XlayersCeboso-academy@webshell:~$ ls
Addadshashanammu      Addadshashanammu.zip.1  HOLA.txt    enc_flag    file    flag  koala     ltdis.sh.1  static    static.ltdis.strings.txt  strings
Addadshashanammu.zip  HOLA                    README.txt  enc_flag.1  file.1  hola  ltdis.sh  salida.txt  static.1  static.ltdis.x86_64.txt   warm
XlayersCeboso-academy@webshell:~$ file enc_flag
enc_flag: ASCII text
XlayersCeboso-academy@webshell:~$ cat enc_flag
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZrTTBKVVZXcE9VazFXV2toT1dHUllDbUY2UWpSWk1GWlhWa2RHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
XlayersCeboso-academy@webshell:~$ cat enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_492767d2}
```
```

```

## Notas Adicionales

## Referencias
-- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)