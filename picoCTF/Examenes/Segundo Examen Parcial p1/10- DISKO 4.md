
## Descripción
Can you find the flag in this disk image? This time I deleted the file! Let see you get it now! Download the disk image [here](https://challenge-files.cylabacademy.net/library/73410159cc8aafa59ec856dcc13ab8b30a50f6827eef6627d3e346bbd3c0085a/disko-4.dd.gz).

1.- How would you look for deleted files?
## Solución
```
mkdir -p ~/picoctf-forensics/10-disko-4
cd ~/picoctf-forensics/10-disko-4
wget -O disko-4.dd.gz 'https://challenge-files.cylabacademy.net/library/73410159cc8aafa59ec856dcc13ab8b30a50f6827eef6627d3e346bbd3c0085a/disko-4.dd.gz'

gzip -dc disko-4.dd.gz > disko-4.dd
file disko-4.dd
fls -r -d -p disko-4.dd > eliminados.txt
cat eliminados.txt

icat -r disko-4.dd 532021 > recuperado.gz
gzip -dc recuperado.gz

academy{d3l_d0n7_h1d3_w3ll_0a4d31fa}
```
```

```

## Notas Adicionales
- Eliminar un archivo puede dejar datos recuperables mientras no se sobrescriban.
- `fls -d` muestra entradas eliminadas e `icat -r` aplica técnicas de recuperación.
## Referencias
