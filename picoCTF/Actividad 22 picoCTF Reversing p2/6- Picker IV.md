## Descripción
## Picker IV

Binary ExploitationMedium

by LT 'syreal' Jones

Can you figure out how this program works to get the flag? Connect to the program with netcat:

`$ nc chatelaine.cylabacademy.net 20449`

The program's source code can be downloaded [here](https://challenge-files.cylabacademy.net/library/0000d8a0aee8130be2d84be318a53e00580bfd2529533c5d1d502187f6411476/picker-IV.c). The binary can be downloaded [here](https://challenge-files.cylabacademy.net/library/0000d8a0aee8130be2d84be318a53e00580bfd2529533c5d1d502187f6411476/picker-IV).

Instance

Expires in 14:52

Hints

1- With Python, there are no binaries. With compiled languages like C, there is source code, and there are binaries. Binaries are created from source code, they are a conversion from the human-readable source code, to the highly efficient machine language, in this case: x86_64.

2- How can you find the address that `win` is at?
## Solución
```
academy{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_cd521e4c}
```

## Notas Adicionales

## Referencias