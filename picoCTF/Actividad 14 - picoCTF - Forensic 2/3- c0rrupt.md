## Descripción
We found this [file](https://challenge-files.cylabacademy.net/library/8388ecc430588d15064755583476bec46e23d42a6d8de6e8995c19e40f2e4c58/c0rrupt-mystery). Recover the flag.

1.- Try fixing the file header
## Solución
```
──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/8388ecc430588d15064755583476bec46e23d42a6d8de6e8995c19e40f2e4c58/c0rrupt-mystery
--2026-09-30 22:01:32--  https://challenge-files.cylabacademy.net/library/8388ecc430588d15064755583476bec46e23d42a6d8de6e8995c19e40f2e4c58/c0rrupt-mystery
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.66, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 201205 (196K) [application/octet-stream]
Saving to: ‘c0rrupt-mystery’

c0rrupt-mystery                                            100%[=======================================================================================================================================>] 196.49K  --.-KB/s    in 0.08s   

2026-09-30 22:01:32 (2.32 MB/s) - ‘c0rrupt-mystery’ saved [201205/201205]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ ls
c0rrupt-mystery  Desktop  Documents  Downloads  LaboratorioSeguridad  Music  Pictures  Public  sstv  Templates  Videos
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ cat c0rrupt-mystery 


┌──(kali㉿kali)-[~]
└─$ ls                 
c0rrupt-mystery  Desktop  Documents  Downloads  LaboratorioSeguridad  Music  Pictures  Public  sstv  Templates  Videos
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ file c0rrupt-mystery 
c0rrupt-mystery: data
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ xxd -l 64 c0rrupt-mystery
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ cp c0rrupt-mystery fixed.png
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ python3 - <<'PY'
p = "fixed.png"

with open(p, "rb") as f:
    data = bytearray(f.read())

data[0:8] = bytes.fromhex("89 50 4E 47 0D 0A 1A 0A")
data[12:16] = b'IHDR'

data[70:74] = bytes.fromhex("00 00 16 25")
data[78:82] = bytes.fromhex("38 D8 2C 82")

data[83:87] = bytes.fromhex("00 00 FF A5")
data[87:91] = b'IDAT'

with open(p, "wb") as f:
    f.write(data)

print("Archivo reparado:", p)
PY
Archivo reparado: fixed.png
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ ls
c0rrupt-mystery  Desktop  Documents  Downloads  fixed.png  LaboratorioSeguridad  Music  Pictures  Public  sstv  Templates  Videos
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ file fixed.png      
fixed.png: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ xdg-open fixed.png



academy{c0rrupt10n_1847995}
```
```

```

## Notas Adicionales

## Referencias
