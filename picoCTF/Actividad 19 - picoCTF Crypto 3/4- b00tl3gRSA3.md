## Descripción
Why use p and q when I can use more? Connect with `nc xebec.cylabacademy.net 42855`.

1.- There's more prime factors than p and q, finding d is going to be different.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ ^[[200~cd ~/b00tl3gRSA3~
zsh: bad pattern: ^[[200~cd
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ cd ~/b00tl3gRSA3
cd: no such file or directory: /home/kali/b00tl3gRSA3
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ mkdir cd b00tl3gRSA3
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ cd ~/b00tl3gRSA3
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/b00tl3gRSA3]
└─$ sudo apt install -y pari-gp
[sudo] password for kali: 
Installing:                     
  pari-gp

Installing dependencies:
  pari-doc  pari-elldata  pari-galdata  pari-seadata

Suggested packages:
  pari-gp2c  pari-galpol  pari-nflistdata

Summary:
  Upgrading: 0, Installing: 5, Removing: 0, Not Upgrading: 948
  Download size: 89.2 MB
  Space needed: 103 MB / 59.4 GB available

Get:1 http://kali.download/kali kali-rolling/main amd64 pari-doc all 2.17.4-1 [8,089 kB]
Get:3 http://us.mirror.ionos.com/linux/distributions/kali/kali kali-rolling/main amd64 pari-galdata all 0.20080411-4 [36.3 kB]
Get:5 http://us.mirror.ionos.com/linux/distributions/kali/kali kali-rolling/main amd64 pari-seadata all 0.20090618-3 [19.3 MB]
Get:2 http://kali.download/kali kali-rolling/main amd64 pari-elldata all 0.20210301-1 [57.8 MB]
Get:4 http://kali.download/kali kali-rolling/main amd64 pari-gp amd64 2.17.4-1 [4,010 kB]                                                                                                                                                 
Fetched 89.2 MB in 20s (4,356 kB/s)                                                                                                                                                                                                       
^[[B^[[B^[[BSelecting previously unselected package pari-doc.
(Reading database… 482310 files and directories currently installed.)
Preparing to unpack …/pari-doc_2.17.4-1_all.deb…
Unpacking pari-doc (2.17.4-1)…
Selecting previously unselected package pari-elldata.
Preparing to unpack …/pari-elldata_0.20210301-1_all.deb…
Unpacking pari-elldata (0.20210301-1)…
^[[B^[[B^[[BSelecting previously unselected package pari-galdata.
Preparing to unpack …/pari-galdata_0.20080411-4_all.deb…
Unpacking pari-galdata (0.20080411-4)…
Selecting previously unselected package pari-gp.
Preparing to unpack …/pari-gp_2.17.4-1_amd64.deb…
Unpacking pari-gp (2.17.4-1)…
Selecting previously unselected package pari-seadata.
Preparing to unpack …/pari-seadata_0.20090618-3_all.deb…
Unpacking pari-seadata (0.20090618-3)…
Setting up pari-galdata (0.20080411-4)…
Setting up pari-elldata (0.20210301-1)…
Setting up pari-doc (2.17.4-1)…
Setting up pari-seadata (0.20090618-3)…
Setting up pari-gp (2.17.4-1)…
Processing triggers for doc-base (0.11.2)…
Processing 4 added doc-base files...
Processing triggers for man-db (2.13.1-1)…
Processing triggers for kali-menu (2026.3.2)…
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/b00tl3gRSA3]
└─$ nc -w 5 xebec.cylabacademy.net 42855 | tee datos.txt
c: 29958320004468465431713393031024270461641220101856234622176480334520117450366958130954852706049538158736603114091738967445879768416702528051072355468456131947191221898020806264191686710536995134554690836451249802474741099202408882836052155831372122394062913778126376017534913388965430071181260903435607681489624213645468083318003373010983109606
n: 43813277567606370609778516103912768173068379669760178834117955317829640500693429893797967500611691403517028031117143604139203412559078082278042717251616045737510730607093488093914190020216065745111640000087290517925705389964915286673770493437203711507529922522373465915186653507801056533413211444612325952685652433203459943281543108513663018159
e: 65537
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/b00tl3gRSA3]
└─$ python3 resolver_b00tl3gRSA3.py datos.txt
python3: can't open file '/home/kali/b00tl3gRSA3/resolver_b00tl3gRSA3.py': [Errno 2] No such file or directory



┌──(kali㉿kali)-[~/b00tl3gRSA3]
└─$ python exp.py                     
python: can't open file '/home/kali/b00tl3gRSA3/exp.py': [Errno 2] No such file or directory
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/b00tl3gRSA3]
└─$ nano resolver_b00tl3gRSA3.py
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/b00tl3gRSA3]
└─$ nano resolver_b00tl3gRSA3.py
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/b00tl3gRSA3]
└─$ python3 resolver_b00tl3gRSA3.py datos.txt
Factorizando n...
FACTORES:[8688904529, 1; 8894282611, 1; 8907255809, 1; 8966534719, 1; 9251696189, 1; 9372783577, 1; 9439454803, 1; 10173165599, 1; 10743150683, 1; 10744777357, 1; 11027849687, 1; 11762651503, 1; 12006453829, 1; 12260585641, 1; 12337586761, 1; 13015782529, 1; 13522255601, 1; 13548609937, 1; 14052796523, 1; 14235885067, 1; 14368533997, 1; 14869104233, 1; 15122393003, 1; 15129512737, 1; 15511193237, 1; 15538201201, 1; 15723626599, 1; 16037846921, 1; 16236960227, 1; 16367382221, 1; 16806796577, 1; 17015235719, 1; 17050776979, 1; 17068172119, 1]
COMPROBACION:1
Bandera: academy{too_many_fact0rs_9487747}


academy{too_many_fact0rs_9487747}
```
```

```

## Notas Adicionales

## Referencias