## Descripción
Can you get the flag? Go to this website and see what you can discover.

[http://xebec.cylabacademy.net:33567/](http://xebec.cylabacademy.net:33567/)

1.- Is there more code than what the inspector initially shows?
## Solución
```
Revisé el HTML principal y encontré que la página carga dos archivos externos:

<link rel="stylesheet" href="style.css">
<script src="script.js"></script>

La primera parte de la bandera estaba en style.css:

curl -s http://xebec.cylabacademy.net:33567/style.css

/*  academy{1nclu51v17y_1of2_  */

La segunda parte estaba en script.js:

curl -s http://xebec.cylabacademy.net:33567/script.js

//  f7w_2of2_ce526b3b}

Concatené ambas partes:
academy{1nclu51v17y_1of2_f7w_2of2_64d6df37}
```
```

```

## Notas Adicionales

## Referencias
-- [http://xebec.cylabacademy.net:33567/](http://xebec.cylabacademy.net:33567/)
- [http://xebec.cylabacademy.net:33567/style.css](http://xebec.cylabacademy.net:33567/style.css)
- [http://xebec.cylabacademy.net:33567/script.js](http://xebec.cylabacademy.net:33567/script.js)
