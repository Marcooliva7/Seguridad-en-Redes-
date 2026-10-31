 ## Descripción
 1.- Try checking the file’s header.

2.- JPEG

3.- Tools like xxd or hexdump can help you inspect and edit file bytes.

## Solución
```
mkdir -p ~/picoctf-forensics/06-corrupted-file
cd ~/picoctf-forensics/06-corrupted-file
wget -O file 'https://challenge-files.cylabacademy.net/library/cefad24659aa422bb4e57016eda1c098a0e8f3e83fbf006b58c235ca0440cb9e/file'

xxd -l 16 file
cp file reparado.jpg
printf '\xff\xd8' | dd of=reparado.jpg bs=1 seek=0 conv=notrunc status=none
file reparado.jpg
xdg-open reparado.jpg

academy{r3st0r1ng_th3_by73s_a6f66bd7}
```
```


```
## Notas Adicionales
-- Cambiar la extensión no corrige una cabecera dañada.
- La reparación se realiza sobre una copia y conserva el original.
## Referencias


