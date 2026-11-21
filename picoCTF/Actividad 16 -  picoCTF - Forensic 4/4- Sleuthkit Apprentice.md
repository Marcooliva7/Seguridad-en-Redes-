## Descripción
Download this disk image and find the flag.

Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://challenge-files.cylabacademy.net/library/162bc8bf6dd1abbc5269c16570e170277369a39cf46bdd8d99443e136fabcc5f/disk.flag.img.gz)
## Solución
```
Descargar la imagen comprimida: 
wget https://challenge-files.cylabacademy.net/library/162bc8bf6dd1abbc5269c16570e170277369a39cf46bdd8d99443e136fabcc5f/disk.flag.img.gz

Descomprimir la imagen: 
gzip -d disk.flag.img.gz 

Mostrar la tabla de particiones y ubicar la partición Linux que comienza en el sector 360448: 
mmls disk.flag.img 

Listar recursivamente los archivos de esa partición y buscar los nombres relacionados con la bandera: 
fls -r -o 360448 disk.flag.img | grep -i flag 

Extraer el archivo activo flag.uni.txt, cuyo inode es 2371: 
icat -o 360448 disk.flag.img 2371

academy{by73_5urf3r_217f681f}
```

```

```

## Notas Adicionales

## Referencias
