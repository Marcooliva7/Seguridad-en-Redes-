## Descripción
The flag is somewhere on this web application not necessarily on the website. Find it.

[http://xebec.cylabacademy.net:13111/](http://xebec.cylabacademy.net:13111/)
## Solución
```
curl -s http://xebec.cylabacademy.net:13111/robots.txt

Aparecieron cadenas en Base64:

ZmxhZzEudHh0
anMvbXlmaWxlLnR4dA==

Las decodifiqué:

ZmxhZzEudHh0 -> flag1.txt
anMvbXlmaWxlLnR4dA== -> js/myfile.txt

La ruta flag1.txt no existía, pero /js/myfile.txt sí contenía la bandera:

curl -s http://xebec.cylabacademy.net:13111/js/myfile.txt

academy{Who_D03sN7_L1k5_90B0T5_662b27d3}

```
```

```

## Notas Adicionales

## Referencias
- [http://xebec.cylabacademy.net:13111/](http://xebec.cylabacademy.net:13111/)
- [http://xebec.cylabacademy.net:13111/robots.txt](http://xebec.cylabacademy.net:13111/robots.txt)
- [http://xebec.cylabacademy.net:13111/js/myfile.txt](http://xebec.cylabacademy.net:13111/js/myfile.txt)
