## Descripción

Can you find the flag in [file](https://challenge-files.picoctf.net/c_fickle_tempest/563d66bbed3925c75ed71efa974bfafab26460ae99938d699a8881cd173fca60/strings) without running it?
## Solución
```
Primero hice wget

```
```

- Luego hice file strings
- Cat strings
- Strings strings
- Finalmente: Strings strings | grep pico

```
academy{5tRIng5_1T_8552bB3B}

```
```

## Notas Adicionales
- Strings muestra las caenas (caracteres imprimibles) en un archivo binario (no texto)
## Referencias
-- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)