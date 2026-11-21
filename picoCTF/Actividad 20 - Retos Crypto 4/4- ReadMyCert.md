## Descripción
How about we take you on an adventure on exploring certificate signing requests Take a look at this CSR file [here](https://challenge-files.cylabacademy.net/library/5106e781bbd36dcc1335e6ad005b28467f171c07351768e71d06bf9cafb3c1f6/readmycert.csr).

1.- Download the certificate signing request and try to read it.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir readmecat  
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ cd readmecat     
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/readmecat]
└─$ wget https://challenge-files.cylabacademy.net/library/5106e781bbd36dcc1335e6ad005b28467f171c07351768e71d06bf9cafb3c1f6/readmycert.csr
--2026-10-21 13:31:48--  https://challenge-files.cylabacademy.net/library/5106e781bbd36dcc1335e6ad005b28467f171c07351768e71d06bf9cafb3c1f6/readmycert.csr
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.40, 13.226.187.66, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.37|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 997 [application/octet-stream]
Saving to: ‘readmycert.csr’

readmycert.csr                                             100%[=======================================================================================================================================>]     997  --.-KB/s    in 0s      

2026-10-21 13:31:50 (3.83 MB/s) - ‘readmycert.csr’ saved [997/997]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/readmecat]
└─$ openssl req -in readmycert.csr -noout -subject
subject=CN=academy{read_mycert_52274715}, name=ctfPlayer


academy{read_mycert_a209fd00}
```
```

```

## Notas Adicionales

## Referencias
