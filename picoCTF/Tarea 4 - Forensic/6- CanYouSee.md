## Descripción
How about some hide and seek?

Download this file [here](https://challenge-files.cylabacademy.net/library/db9453955f3bd6e863102fd10b5c3b1e6ce0517e7c648b76d86172eed079e028/unknown.zip).

1.- How can you view the information about the picture?

2.- If something isn't in the expected form, maybe it deserves attention?
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf/canyousee
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ cd ~/picoctf/canyousee
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/canyousee]
└─$ curl -L --fail --show-error -o unknown.zip 'https://challenge-files.cylabacademy.net/library/db9453955f3bd6e863102fd10b5c3b1e6ce0517e7c648b76d86172eed079e028/unknown.zip'
  % Total    % Received % Xferd  Average Speed  Time    Time    Time   Current
                                 Dload  Upload  Total   Spent   Left   Speed
100  2.14M 100  2.14M   0      0  1.03M      0   00:02   00:02         685.0k
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/canyousee]
└─$ unzip unknown.zip
Archive:  unknown.zip
  inflating: ukn_reality.jpg         
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/canyousee]
└─$ strings -a ukn_reality.jpg | grep 'cc:attributionURL'
  <cc:attributionURL rdf:resource='YWNhZGVteXtNRTc0RDQ3QV9ISUREM05fYTgxZDk0MzF9Cg=='/>
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/canyousee]
└─$ strings -a ukn_reality.jpg | grep -oP "cc:attributionURL rdf:resource='\K[^']+" | base64 -d
academy{ME74D47A_HIDD3N_a81d9431}



academy{ME74D47A_HIDD3N_a81d9431}
```
```

```

## Notas Adicionales

## Referencias
