## Descripción
Every file gets a flag. The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://challenge-files.cylabacademy.net/library/afab2dc0b8164303df06666c7b574103668443cba057e14f9d6683ce67665bda/flag.png).
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf/hideme
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ cd ~/picoctf/hideme
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/hideme]
└─$ curl -L --fail --show-error -o flag.png 'https://challenge-files.cylabacademy.net/library/afab2dc0b8164303df06666c7b574103668443cba057e14f9d6683ce67665bda/flag.png'
  % Total    % Received % Xferd  Average Speed  Time    Time    Time   Current
                                 Dload  Upload  Total   Spent   Left   Speed
100  21600 100  21600   0      0  40221      0                              0
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/hideme]
└─$ unzip -l flag.png
Archive:  flag.png
warning [flag.png]:  15929 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  Length      Date    Time    Name
---------  ---------- -----   ----
        0  2026-09-23 00:33   secret/
     5349  2026-09-23 00:33   secret/flag.png
---------                     -------
     5349                     2 files
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/hideme]
└─$ unzip -o flag.png -d extracted
Archive:  flag.png
warning [flag.png]:  15929 extra bytes at beginning or within zipfile
  (attempting to process anyway)
   creating: extracted/secret/
 extracting: extracted/secret/flag.png  
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/hideme]
└─$ xdg-open extracted/secret/flag.png


academy{Hiddinng_An_imag3_within_@n_ima9e_c29e4ed9}
```
```

```

## Notas Adicionales

## Referencias
