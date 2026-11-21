## Descripción
RED, RED, RED, RED Download the image: [red.png](https://challenge-files.cylabacademy.net/library/fefcf06050d98347e1585e5cb9f2940967f82e0b89c591966473c752de9f3aba/red.png)

1.- The picture seems pure, but is it though?

2.- Red?Ged?Bed?Aed?

3.- Check whatever Facebook is called now.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf/red      
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ cd ~/picoctf/red      
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/red]
└─$ curl -L --fail --show-error -o red.png 'https://challenge-files.cylabacademy.net/library/fefcf06050d98347e1585e5cb9f2940967f82e0b89c591966473c752de9f3aba/red.png'
  % Total    % Received % Xferd  Average Speed  Time    Time    Time   Current
                                 Dload  Upload  Total   Spent   Left   Speed
100    792 100    792   0      0   1773      0                              0
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/red]
└─$ strings -a red.png | head -15
IHDR
tEXtPoem
Crimson heart, vibrant and bold,
Hearts flutter at your sight.
Evenings glow softly red,
Cherries burst with sweet life.
Kisses linger with your warmth.
Love deep as merlot.
Scarlet leaves falling softly,
Bold in every stroke.x
IDATx
IEND
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/red]
└─$ sudo apt install -y python3-pil        
[sudo] password for kali: 
python3-pil is already the newest version (12.3.0-1+b1).
python3-pil set to manually installed.
Summary:                    
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 948
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/red]
└─$ python3 - <<'PY'
from PIL import Image
from base64 import b64decode

im = Image.open('red.png').convert('RGBA')
bits = (channel & 1
        for y in range(im.height)
        for x in range(im.width)
        for channel in im.getpixel((x, y)))
encoded = bytes(sum(next(bits) << (7 - i) for i in range(8)) for _ in range(64))
print(b64decode(encoded).decode())
PY
academy{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}



academy{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
```
```

```

## Notas Adicionales

## Referencias
