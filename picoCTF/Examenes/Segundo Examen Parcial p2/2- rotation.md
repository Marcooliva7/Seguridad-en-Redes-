## Descripción
You will find the flag after decrypting this file Download the encrypted flag [here](https://challenge-files.cylabacademy.net/library/7b27068b4f8daca5e159c2ee99494b77c9f8418a8576d6a0cabc7947d41577aa/encrypted.txt).

1.- Sometimes rotation is right
## Solución
```
┌──(entorno)─(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf-crypto/02-rotation
cd ~/picoctf-crypto/02-rotation
wget -O encrypted.txt 'https://challenge-files.cylabacademy.net/library/7b27068b4f8daca5e159c2ee99494b77c9f8418a8576d6a0cabc7947d41577aa/encrypted.txt'
cat encrypted.txt
--2026-10-26 23:41:41--  https://challenge-files.cylabacademy.net/library/7b27068b4f8daca5e159c2ee99494b77c9f8418a8576d6a0cabc7947d41577aa/encrypted.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.37, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 37 [application/octet-stream]
Saving to: ‘encrypted.txt’

encrypted.txt                100%[=============================================>]      37  --.-KB/s    in 0s      

2026-10-26 23:41:42 (101 MB/s) - ‘encrypted.txt’ saved [37/37]

ikilmug{z0bib1wv_l3kzgxb3l_42440k4j}

academy{r0tat1on_d3crypt3d_a4008e11}
```
```

```

## Notas Adicionales
- Sumar `18` posiciones equivale a retroceder `8`, porque `26 − 8 = 18`. El prefijo `ikilmug` se convierte en `academy`.
## Referencias
