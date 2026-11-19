## Descripción
How about trying to match a regular expression

[http://saturn.picoctf.net:61214/](http://saturn.picoctf.net:61214/)

1.- Access the webpage and try to match the regular expression associated with the text field
## Solución
```
^p.....F!?

La cadena picoCTF coincide con la expresión:

p      -> inicia con p
.....  -> cinco caracteres: icoCT
F      -> termina con F
!?     -> el signo ! es opcional

Probé el input en el endpoint de la página:

curl -s "http://saturn.picoctf.net:61214/flag?input=picoCTF"

{"flag":"academy{succ3ssfully_matchtheregex_4d5352dc}"}

academy{succ3ssfully_matchtheregex_4d5352dc}
```
```

```

## Notas Adicionales
- La validación estaba expuesta en el JavaScript de la página.
## Referencias
-- [http://saturn.picoctf.net:61214/](http://saturn.picoctf.net:61214/)
