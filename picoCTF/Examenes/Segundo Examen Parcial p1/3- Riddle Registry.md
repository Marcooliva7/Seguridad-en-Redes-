
## Descripción
Hi, intrepid investigator! 📄🔍 You've stumbled upon a peculiar PDF filled with what seems like nothing more than garbled nonsense. But beware! Not everything is as it appears. Amidst the chaos lies a hidden treasure—an elusive flag waiting to be uncovered. Find the PDF file here [Hidden Confidential Document](https://challenge-files.cylabacademy.net/library/1d073b2830cd8e8e6fb24a8bab184a91b61a25bea90c1d93530e92fe8a368e61/confidential.pdf) and uncover the flag within the metadata.
## Solución
```
mkdir -p ~/picoctf-forensics/03-riddle-registry
cd ~/picoctf-forensics/03-riddle-registry
wget -O confidential.pdf 'https://challenge-files.cylabacademy.net/library/cd10271d1755c79f00fce1beff6a218832ac3678783ccfce59c111813fcb7276/confidential.pdf'
exiftool -Author confidential.pdf
exiftool -s3 -Author confidential.pdf | base64 --decode
printf '\n'
academy{puzzl3d_m3tadata_f0und!_606a0ba9}

```


```
##Notas Adicionales
- Los metadatos pueden contener información que no aparece en las páginas visibles del documento.


## Referencias