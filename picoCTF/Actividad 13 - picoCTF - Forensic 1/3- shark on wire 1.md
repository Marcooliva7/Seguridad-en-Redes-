## Descripción
We found this [packet capture](https://challenge-files.cylabacademy.net/library/e64f2c2aaf9bf531af7be1787c1407c47a4cc7b57f251d5108a1151e9721a2d6/shark-on-wire-1-capture.pcap). Recover the flag.

1.- Try using a tool like Wireshark, What are streams?
## Solución
```
wget https://challenge-files.cylabacademy.net/library/e64f2c2aaf9bf531af7be1787c1407c47a4cc7b57f251d5108a1151e9721a2d6/shark-on-wire-1-capture.pcap 

(kali㉿kali)-[~] └─$ sudo apt install wireshark y se abre wireshark 

abrí el archivo y busqué que el archivo sea UDP para así buscar la FLAG. Luego al botón de Follow. 

academy{StaT31355_636f6e6e}
```
```

```

## Notas Adicionales
PCAP es un formato de datos utilizado para almacenar el tráfico de red grabado en tiempo real. Funciona como una especie de "grabación digital" de todos los datos (paquetes) que viajan a través de una red informática, ya sea Wi-Fi o cableada.
## Referencias
