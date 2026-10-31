## Descripción
The SOC team discovered a suspiciously large log file after a recent breach. When they opened it, they found an enormous block of encoded text instead of typical logs. Could there be something hidden within? Your mission is to inspect the resulting file and reveal the real purpose of it. The team is relying on your skills to uncover any concealed information within this unusual log. Download the encoded data here: [Logs Data](https://challenge-files.cylabacademy.net/library/e6fc51b98dd61381c5cd54dc836c8344fb475f17728f2095969e3a0f401ea195/logs.txt). Be prepared—the file is large, and examining it thoroughly is crucial .

1.- Use `base64` to decode the data and generate the image file.

## Solución
```
mkdir -p ~/picoctf-forensics/05-flag-in-flame
cd ~/picoctf-forensics/05-flag-in-flame
wget -O logs.txt 'https://challenge-files.cylabacademy.net/library/e6fc51b98dd61381c5cd54dc836c8344fb475f17728f2095969e3a0f401ea195/logs.txt'
base64 --decode logs.txt > flame.png
file flame.png
xdg-open flame.png

printf '%s' '61636164656D797B666F72656E736963735F616E616C797369735F69735F616D617A696E675F32303433646264317D' | xxd -r -p
printf '\n'
academy{forensics_analysis_is_amazing_1c6b929d}
```
```

```
## Notas Adicionales

-- Hay dos capas: Base64 recupera el PNG y el hexadecimal de la imagen recupera la bandera.
## Referencias

