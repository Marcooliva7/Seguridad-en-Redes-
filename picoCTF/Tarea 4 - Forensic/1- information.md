## Descripción
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://challenge-files.cylabacademy.net/library/c585b4adbdaa06f409db7bf5012c2e58e9aab24669764a5f1cf0f9ce0d60dcfd/cat.jpg)

1.- Look at the details of the file

2.- Make sure to submit the flag as academy{XXXXX}
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf/information
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ cd ~/picoctf/information
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/information]
└─$ curl -L --fail --show-error -o cat.jpg 'https://challenge-files.cylabacademy.net/library/c585b4adbdaa06f409db7bf5012c2e58e9aab24669764a5f1cf0f9ce0d60dcfd/cat.jpg'
  % Total    % Received % Xferd  Average Speed  Time    Time    Time   Current
                                 Dload  Upload  Total   Spent   Left   Speed
100 857.5k 100 857.5k   0      0 837.5k      0   00:01   00:01              0
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/information]
└─$ strings cat.jpg | grep 'cc:license'
  <cc:license rdf:resource='YWNhZGVteXt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9'/>
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/information]
└─$ strings cat.jpg | grep -oP "cc:license rdf:resource='\K[^']+" | base64 -d
academy{the_m3tadata_1s_modified}                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/information]
└─$ echo    


academy{the_m3tadata_1s_modified}
```
```

```

## Notas Adicionales

## Referencias
