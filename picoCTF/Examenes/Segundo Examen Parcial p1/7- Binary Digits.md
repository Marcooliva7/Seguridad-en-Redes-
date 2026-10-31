## Descripción
This file doesn't look like much... just a bunch of 1s and 0s. But maybe it's not just random noise. Can you recover anything meaningful from this? Download the file [here](https://challenge-files.cylabacademy.net/library/6ba8983da0e17a2e2015a530788849e9c9c0bc3393d62fa3f9a06ce8068567c8/digits.bin).
## Solución
```
mkdir -p ~/picoctf-forensics/07-binary-digits
cd ~/picoctf-forensics/07-binary-digits
wget -O digits.bin 'https://challenge-files.cylabacademy.net/library/6ba8983da0e17a2e2015a530788849e9c9c0bc3393d62fa3f9a06ce8068567c8/digits.bin'
nano exp.py

python3 exp.py
file recuperado.jpg
xdg-open recuperado.jpg

academy{h1dd3n_1n_th3_b1n4ry_5a7375c5}
```
```

```

## Notas Adicionales
- Contiene **71 744 dígitos**, que representan **71 744 ÷ 8 = 8 968 bytes**. Los bytes recuperados forman un JPEG.
## Referencias
