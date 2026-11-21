## Descripción
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?

Download the suspicious file [here](https://challenge-files.cylabacademy.net/library/70f90e64dbbf4b6c6da7c0cd024663e66eb3fecf36dde7c7947c96debe14885a/flag2of2-final.pdf).

1.- This problem can be solved by just opening the file in different ways
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf/polyglot
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ cd ~/picoctf/polyglot
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/polyglot]
└─$ curl -L --fail --show-error -o flag2of2-final.pdf 'https://challenge-files.cylabacademy.net/library/70f90e64dbbf4b6c6da7c0cd024663e66eb3fecf36dde7c7947c96debe14885a/flag2of2-final.pdf'
file flag2of2-final.pdf
  % Total    % Received % Xferd  Average Speed  Time    Time    Time   Current
                                 Dload  Upload  Total   Spent   Left   Speed
100   2901 100   2901   0      0   3491      0                              0
flag2of2-final.pdf: PNG image data, 200 x 40, 4-bit colormap, non-interlaced
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/polyglot]
└─$ file flag2of2-final.pdf
flag2of2-final.pdf: PNG image data, 200 x 40, 4-bit colormap, non-interlaced
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/polyglot]
└─$ cp flag2of2-final.pdf flag1of2.png
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/polyglot]
└─$ xdg-open flag1of2.png
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/polyglot]
└─$ sudo apt install -y poppler-utils
[sudo] password for kali: 
poppler-utils is already the newest version (26.07.0-2).
Summary:                    
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 948
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/polyglot]
└─$ pdftotext -layout flag2of2-final.pdf -
1n_pn9_&_pdf_2f8da0be}



academy{f1u3n7_1n_pn9_&_pdf_07226ac4} ```
```

```

## Notas Adicionales

## Referencias
