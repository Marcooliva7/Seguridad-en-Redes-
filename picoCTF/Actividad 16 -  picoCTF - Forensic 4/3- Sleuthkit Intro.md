## Descripción
Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.

Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

[Download disk image](https://challenge-files.cylabacademy.net/library/d8718cbbc14dcd9f9aad532a51d7a01b00e1715ca3b1d654dfef687d0b15cbf5/disk.img.gz) Access checker program: `nc chatelaine.cylabacademy.net 26086`
## Solución
```
Descargar la imagen comprimida: 
wget https://challenge-files.cylabacademy.net/library/d8718cbbc14dcd9f9aad532a51d7a01b00e1715ca3b1d654dfef687d0b15cbf5/disk.img.gz 

Comprobar el tipo de archivo: 
file disk.img.gz 

Descomprimir la imagen para obtener disk.img: 
gzip -d disk.img.gz 

Mostrar la tabla de particiones y localizar el valor Length de la fila Linux: 
mmls disk.img 

Conectarse al verificador y enviar el tamaño 202752 cuando lo solicite:
nc chatelaine.cylabacademy.net 26086

academy{mm15_f7w!}
```
```

```

## Notas Adicionales

## Referencias
