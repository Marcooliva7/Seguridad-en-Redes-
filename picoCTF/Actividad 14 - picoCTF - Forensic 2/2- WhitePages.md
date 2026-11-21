## Descripción
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://challenge-files.cylabacademy.net/library/53f38374e47a48424dc7e9100aba4e4b42a590f3921cfc31188171ae7d6d61e3/whitepages.txt) is all blank!

1.- There is data encoded somewhere... there might be an online decoder.
## Solución
```
┌──(kali㉿kali)-[~/Downloads]
└─$ wget https://challenge-files.cylabacademy.net/library/53f38374e47a48424dc7e9100aba4e4b42a590f3921cfc31188171ae7d6d61e3/whitepages.txt        
--2026-09-30 21:57:29--  https://challenge-files.cylabacademy.net/library/53f38374e47a48424dc7e9100aba4e4b42a590f3921cfc31188171ae7d6d61e3/whitepages.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.40, 13.226.187.66, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.37|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2766 (2.7K) [application/octet-stream]
Saving to: ‘whitepages.txt.1’

whitepages.txt.1                                100%[====================================================================================================>]   2.70K  --.-KB/s    in 0s      

2026-09-30 21:57:29 (107 MB/s) - ‘whitepages.txt.1’ saved [2766/2766]

                                                                                                                                                                                             
┌──(kali㉿kali)-[~/Downloads]
└─$ ls                  
whitepages.txt  whitepages.txt.1
                                                                                                                                                                                             
┌──(kali㉿kali)-[~/Downloads]
└─$ xxd whitepages.txt.1 | head
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000010: 20e2 8083 e280 8320 20e2 8083 e280 83e2   ......  .......
00000020: 8083 e280 8320 e280 8320 20e2 8083 e280  ..... ...  .....
00000030: 83e2 8083 2020 e280 8320 20e2 8083 e280  ....  ...  .....
00000040: 83e2 8083 e280 8320 e280 8320 20e2 8083  ....... ...  ...
00000050: e280 8320 e280 83e2 8083 e280 8320 20e2  ... .........  .
00000060: 8083 e280 8320 e280 8320 e280 8320 20e2  ..... ... ...  .
00000070: 8083 2020 e280 8320 e280 8320 2020 20e2  ..  ... ...    .
00000080: 8083 e280 8320 e280 83e2 8083 e280 83e2  ..... ..........
00000090: 8083 20e2 8083 20e2 8083 e280 83e2 8083  .. ... .........
                                                                                                                                                                                             
┌──(kali㉿kali)-[~/Downloads]
└─$ python3 - <<'PY'
data = open("whitepages.txt", "r", encoding="utf-8").read()

bits = data.replace("\u2003", "0").replace(" ", "1")

texto = ""
for i in range(0, len(bits), 8):
    byte = bits[i:i+8]
    if len(byte) == 8:
        texto += chr(int(byte, 2))

print(texto)
PY

academy

SEE PUBLIC RECORDS & BACKGROUND REPORT
5000 Forbes Ave, Pittsburgh, PA 15213


academy{not_all_spaces_are_created_equal_5fe1602ea91f835386aa3eae672cf4e3}
```
```

```

## Notas Adicionales

## Referencias
