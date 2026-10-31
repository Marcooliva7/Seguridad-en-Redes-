## Descripción
Can you find the flag in this disk image? Wrap what you find in the academy{} flag format. Download the disk image [here](https://challenge-files.cylabacademy.net/library/bf9a20c350075c5863371e078daee1d570d4062902edc8a4a042e02a7cebf161/partition4.img.gz).

## Solución
```
mkdir -p ~/picoctf-forensics/08-timeline-0
cd ~/picoctf-forensics/08-timeline-0
wget -O partition4.img.gz 'https://challenge-files.cylabacademy.net/library/bf9a20c350075c5863371e078daee1d570d4062902edc8a4a042e02a7cebf161/partition4.img.gz'

gzip -dc partition4.img.gz > partition4.img
fls -r -m / partition4.img > body.txt
mactime -b body.txt -d -z UTC > timeline.csv
head -n 8 timeline.csv
grep -F '/bin/bcab' timeline.csv

contenido=$(icat partition4.img 4945 | base64 --decode)
printf 'academy{%s}\n' "$contenido"

academy{71m311n3_0u7113r_h3r_43a2e7af}
```
```

```

## Notas Adicionales
- Una fecha muy antigua respecto al resto del sistema ayuda a localizar anomalías.
- `fls -m` genera el archivo de metadatos que utiliza `mactime` para construir la línea de tiempo.

## Referencias
