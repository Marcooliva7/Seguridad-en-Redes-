## Descripción
Can you get the flag? Go to this website and see what you can discover.

[http://chatelaine.cylabacademy.net:44084/](http://chatelaine.cylabacademy.net:44084/)

1.- How is the password checked on this website?
## Solución
```
El archivo secure.js contenía las credenciales:

curl -s http://chatelaine.cylabacademy.net:44084/secure.js

function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}

Usé las credenciales encontradas:

username: admin
password: strongPassword098765

El login generó el hash de administrador:

2196812e91c29df34f5e217cfd639881

Envié ese hash a admin.php y obtuve la bandera:

academy{j5_15_7r4n5p4r3n7_4fcce45f}
```
```

```

## Notas Adicionales

## Referencias
- [http://chatelaine.cylabacademy.net:44084/](http://chatelaine.cylabacademy.net:44084/)
- [http://chatelaine.cylabacademy.net:44084/secure.js](http://chatelaine.cylabacademy.net:44084/secure.js)
- [http://chatelaine.cylabacademy.net:44084/login.php](http://chatelaine.cylabacademy.net:44084/login.php)
- [http://chatelaine.cylabacademy.net:44084/admin.php](http://chatelaine.cylabacademy.net:44084/admin.php)
