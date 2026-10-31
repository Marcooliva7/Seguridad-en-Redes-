## Descripción
Can you find the flag in this disk image? Wrap what you find in the academy{} flag format. Download the disk image [here](https://challenge-files.cylabacademy.net/library/0b369ed5974a5e777ca3bc323bd39d75a6f27762a449d16cd2a0ffc08b2a6aa8/timeline-1-partition4.img.gz).

1.- Create a Sleuthkit MAC timeline!

2.- Look at recent timestamps

3.- Pay close attention to timestamps near an anti-forensic action

4.- Filter only new files by grepping for `macb`

## Solución
```
mkdir -p ~/picoctf-forensics/09-timeline-1
cd ~/picoctf-forensics/09-timeline-1
wget -O timeline-1-partition4.img.gz 'https://challenge-files.cylabacademy.net/library/0b369ed5974a5e777ca3bc323bd39d75a6f27762a449d16cd2a0ffc08b2a6aa8/timeline-1-partition4.img.gz'

gzip -dc timeline-1-partition4.img.gz > timeline-1-partition4.img
fls -r -m / timeline-1-partition4.img > body.txt
mactime -b body.txt -d -z UTC > timeline.csv
grep ',macb,' timeline.csv | tail -n 20

icat timeline-1-partition4.img 4943
contenido=$(icat timeline-1-partition4.img 32716 | base64 --decode)
printf 'academy{%s}\n' "$contenido"

academy{573417h13r_7h4n_7h3_1457_58527bb222}
```
```

```

## Notas Adicionales
- `macb` agrupa marcas temporales coincidentes; por sí solo no demuestra que un archivo sea nuevo o malicioso.
- El historial ayuda a contextualizar los archivos que aparecen cerca del apagado.
## Referencias
