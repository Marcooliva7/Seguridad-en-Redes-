## Descripción
This file contains more than it seems. Get the flag from garden.jpg.

1.- What is a hex editor?
## Solución
```
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/3c60c5a7f7a8067606c51d4b4b3c7913fae709b11e2f2c7adbc0a0b4cda452ff/garden.jpg
--2026-09-28 12:30:31--  https://challenge-files.cylabacademy.net/library/3c60c5a7f7a8067606c51d4b4b3c7913fae709b11e2f2c7adbc0a0b4cda452ff/garden.jpg
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.66, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.37|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295191 (2.2M) [application/octet-stream]
Saving to: ‘garden.jpg’

garden.jpg                                                 100%[=======================================================================================================================================>]   2.19M   667KB/s    in 3.4s    

2026-09-28 12:30:36 (667 KB/s) - ‘garden.jpg’ saved [2295191/2295191]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ open garden.jpg 
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ file garden.jpg 
garden.jpg: JPEG image data, JFIF standard 1.01, resolution (DPI), density 72x72, segment length 16, baseline, precision 8, 2999x2249, components 3
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ strings -n 10 garden.jpg  
XICC_PROFILE
mntrRGB XYZ 
Copyright (c) 1998 Hewlett-Packard Company
sRGB IEC61966-2.1
sRGB IEC61966-2.1
IEC http://www.iec.ch
IEC http://www.iec.ch
.IEC 61966-2.1 Default RGB colour space - sRGB
.IEC 61966-2.1 Default RGB colour space - sRGB
,Reference Viewing Condition in IEC61966-2.1
,Reference Viewing Condition in IEC61966-2.1
        %       :       O       d       y


┌──(kali㉿kali)-[~]
└─$ strings -20 garden.jpg  
Copyright (c) 1998 Hewlett-Packard Company
IEC http://www.iec.ch
IEC http://www.iec.ch
.IEC 61966-2.1 Default RGB colour space - sRGB
.IEC 61966-2.1 Default RGB colour space - sRGB
,Reference Viewing Condition in IEC61966-2.1
,Reference Viewing Condition in IEC61966-2.1
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
Here is a flag: academy{more_than_m33ts_the_3y3ff3b9e86}

┌──(kali㉿kali)-[~]
└─$ strings garden.jpg -n 15 | grep academy
Here is a flag: academy{more_than_m33ts_the_3y3caff56ca}
                                                           


academy{more_than_m33ts_the_3y3caff56ca}
```
```

```

## Notas Adicionales
Un editor hexadecimal es un tipo de programa informático que permite a los usuarios modificar archivos binarios.
## Referencias
