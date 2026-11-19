## Descripción
Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...

- This program will only work in the webshell or another Linux computer.
## Solución
```
```
wget https://challenge-files.picoctf.net/c_wily_courier/fc72a950cbaa130f81486c2df35deced17604b2c08c6a5aa99d18168036d3107/warm

XlayersCeboso-academy@webshell:~$ file warm
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=9e46ec8729d2f2aa8ffc4b1cdc058081bddcfe67, for GNU/Linux 3.2.0, with debug_info, not stripped
XlayersCeboso-academy@webshell:~$ chmod +x warm
XlayersCeboso-academy@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
XlayersCeboso-academy@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here:
 
academy{b1scu1ts_4nd_gr4vy_57d8c79}
```
```

## Notas Adicionales

- chmod +x agrega permisos de ejecución a un binario el linux
- ./warm - ejecutar el binario warm una vez que ya tiene los permisos de ejecución
- ELF - es el formato de archivo ejecutable en Linux (equivalente al .EXE de Windows)
- file - permite saber de que tipo es un archivo
## Referencias
-