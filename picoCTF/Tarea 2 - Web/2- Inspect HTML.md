## Descripción
Can you get the flag? Go to this website and see what you can discover.

[http://chatelaine.cylabacademy.net:16727/](http://chatelaine.cylabacademy.net:16727/)

1.- What is the web inspector in web browsers?
## Solución
```
Revisé el código fuente HTML de la página:

curl -s http://chatelaine.cylabacademy.net:16727/

Al final del body encontré la bandera dentro de un comentario HTML:

<!-- academy{1n5p3t0r_0f_h7ml_22eecea7}-->

academy{1n5p3t0r_0f_h7ml_22eecea7}
```
```

```

## Notas Adicionales

## Referencias
-
