## Descripción
Do you know how to use the web inspector? Start searching here to find the flag.

[http://chatelaine.cylabacademy.net:34918/](http://chatelaine.cylabacademy.net:34918/)

1.- Use the web inspector on other files included by the web page.

2.- The flag may or may not be encoded.
## Solución
```
curl -s http://chatelaine.cylabacademy.net:34918/

<a href="about.html">About</a>
<a href="contact.html">Contact</a>

Después revisé about.html:

curl -s http://chatelaine.cylabacademy.net:34918/about.html

Dentro del HTML encontré un atributo sospechoso llamado notify_true:

<section class="about" notify_true="YWNhZGVteXt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfM2NkMTQ0ZTV9">

Decodifiqué el valor en Base64:

YWNhZGVteXt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfM2NkMTQ0ZTV9

academy{web_succ3ssfully_d3c0ded_07989b25}
```
```

```

## Notas Adicionales

## Referencias
- [http://chatelaine.cylabacademy.net:34918/](http://chatelaine.cylabacademy.net:34918/)
- [http://chatelaine.cylabacademy.net:34918/about.html](http://chatelaine.cylabacademy.net:34918/about.html)
