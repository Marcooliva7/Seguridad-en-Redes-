## Descripción
We have several pages hidden. Can you find the one with the flag?

[http://xebec.cylabacademy.net:41584/](http://xebec.cylabacademy.net:41584/)

1.- folders folders folders
## Solución
```

curl -s http://xebec.cylabacademy.net:41584/

Encontré una referencia a la carpeta secret:

<link href="secret/assets/index.css" rel="stylesheet" />

Entré a /secret/ y apareció otra carpeta:

curl -s http://xebec.cylabacademy.net:41584/secret/

<link rel="stylesheet" href="hidden/file.css" />

Entré a /secret/hidden/ y encontré la carpeta superhidden:

curl -s http://xebec.cylabacademy.net:41584/secret/hidden/

<link href="superhidden/login.css" rel="stylesheet" />

Finalmente revisé /secret/hidden/superhidden/:

curl -s http://xebec.cylabacademy.net:41584/secret/hidden/superhidden/

Ahí estaba la bandera dentro del HTML:

<h3 class="flag">academy{succ3ss_@h3n1c@10n_7d8bae24}</h3>

academy{succ3ss_@h3n1c@10n_7d8bae24}
```
```

```

## Notas Adicionales

## Referencias
- [http://xebec.cylabacademy.net:41584/](http://xebec.cylabacademy.net:41584/)
- [http://xebec.cylabacademy.net:41584/secret/](http://xebec.cylabacademy.net:41584/secret/)
- [http://xebec.cylabacademy.net:41584/secret/hidden/](http://xebec.cylabacademy.net:41584/secret/hidden/)
- [http://xebec.cylabacademy.net:41584/secret/hidden/superhidden/](http://xebec.cylabacademy.net:41584/secret/hidden/superhidden/)