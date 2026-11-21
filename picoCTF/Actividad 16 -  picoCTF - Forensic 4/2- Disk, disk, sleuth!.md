## Descripción
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image. [dds1-alpine.flag.img.gz](https://challenge-files.cylabacademy.net/library/4d6e776c4f09366b282fa45c00b74c0e348309a34f636fd6a9e4e0ee50e7345b/dds1-alpine.flag.img.gz)

1.- Have you ever used `file` to determine what a file was?

2.- Relevant terminal-fu in Challenge Library: [https://learn.cylabacademy.org/library/85](https://learn.cylabacademy.org/library/85)

3.- Mastering this terminal-fu would enable you to find the flag in a single command: [https://learn.cylabacademy.org/library/48](https://learn.cylabacademy.org/library/48)

4.- Using your own computer, you could use qemu to boot from this disk!
## Solución
```
Descargar el archivo comprimido: 
wget https://challenge-files.cylabacademy.net/library/4d6e776c4f09366b282fa45c00b74c0e348309a34f636fd6a9e4e0ee50e7345b/dds1-alpine.flag.img.gz 

Comprobar el tipo de archivo descargado: 
file dds1-alpine.flag.img.gz 

Descomprimirlo; se generará dds1-alpine.flag.img: 
gzip -d dds1-alpine.flag.img.gz

Instalar Sleuth Kit si el comando srch_strings no está disponible: 
sudo apt update && sudo apt install sleuthkit -y 

Buscar cadenas legibles y filtrar la bandera: 
srch_strings dds1-alpine.flag.img | grep -Eo '(picoCTF|academy)\{[^}]+\}'


academy{f0r3ns1c4t0r_n30phyt3_6502313d}
```
```

```

## Notas Adicionales

## Referencias
