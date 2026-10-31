## Descripción
A message has been encrypted using RSA. The public key is gone… but someone might have been careless with the private key. Can you recover it and decrypt the message? Download the [flag](https://challenge-files.cylabacademy.net/library/4c19613e66e3f22baabf929555a826f8ebd997a002b008eb4e51dc2849aca14e/flag.enc) and [image](https://challenge-files.cylabacademy.net/library/4c19613e66e3f22baabf929555a826f8ebd997a002b008eb4e51dc2849aca14e/image.jpg).

1.- Metadata can tell you more than you expect.

2.- Hex can be turned back into a key file.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf-crypto/03-stegorsa
cd ~/picoctf-crypto/03-stegorsa
wget -O flag.enc 'https://challenge-files.cylabacademy.net/library/4c19613e66e3f22baabf929555a826f8ebd997a002b008eb4e51dc2849aca14e/flag.enc'
wget -O image.jpg 'https://challenge-files.cylabacademy.net/library/4c19613e66e3f22baabf929555a826f8ebd997a002b008eb4e51dc2849aca14e/image.jpg'
--2026-10-26 23:45:24--  https://challenge-files.cylabacademy.net/library/4c19613e66e3f22baabf929555a826f8ebd997a002b008eb4e51dc2849aca14e/flag.enc
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.22, 13.226.187.37, 13.226.187.40, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 256 [application/octet-stream]
Saving to: ‘flag.enc’

flag.enc                     100%[=============================================>]     256  --.-KB/s    in 0s      

2026-10-26 23:45:25 (451 MB/s) - ‘flag.enc’ saved [256/256]

--2026-10-26 23:45:25--  https://challenge-files.cylabacademy.net/library/4c19613e66e3f22baabf929555a826f8ebd997a002b008eb4e51dc2849aca14e/image.jpg
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.22, 13.226.187.37, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 20794 (20K) [application/octet-stream]
Saving to: ‘image.jpg’

image.jpg                    100%[=============================================>]  20.31K  --.-KB/s    in 0.07s   

2026-10-26 23:45:26 (292 KB/s) - ‘image.jpg’ saved [20794/20794]

                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/03-stegorsa]
└─$ exiftool -Comment image.jpg4
Error: File not found - image.jpg4
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/03-stegorsa]
└─$ exiftool -Comment image.jpg 
Comment                         : 2d2d2d2d2d424547494e2050524956415445204b45592d2d2d2d2d0a4d494945764149424144414e42676b71686b6947397730424151454641415343424b59776767536941674541416f4942415143734d6179734e586530784b45720a3343786a75324d355a384c6a485876684c76767471726c6c376c79794a457639597835613579465a6248727859344f647472636f4f653364416237764638376d0a4b566f4a4b614b4d4472596957377257536b786e732f392b616c52744b6d4a4f767875474f47562b6e453765724d4d766949777830747178596b364b676253790a6f5a5546344c6b58744e676567384363647651464537497555493754325a6b5759552b4c6f2b585279315830336f6c6338614135504e4b6b42747966723476790a64774f7755376f64692b313449394b51584b6c744c306c623264366651554658552b61476c596a64514e53654f3141307237484571514d54717a646d6f5a78390a49766a636473623638514e70612f2f56583169435a6662516d7359336a785443574e306a4d754470733167436b45385365755a5853454874775a4f5337474d620a306b34495944733941674d42414145436767454142566670725958354f78613358554264764b752f646d64462f614d2b664a4b7a2b616249744b556d504b4f2f0a473462766c62575062424a467a35707151454c79394b314f75476c394b4465686e6b33524d79504b485455665179313849784d32396c7572654c5639593834380a6d5655737076754450537973572b457a6b636678526369496b70663971316d6c707233523437314e2f655769703656626e524b51547662537a6356546c3763660a5455645175777255432b5671706b4273774a3231565638594a7061743770584d4e5a6169556b4d43684a766a6d4d4c676c4248506f742b614a634f62724570340a4d735566425748452b63683548786f794f592b6668384c626932585138487965546d476e507044426548763538756e75784d3550676a4e6854556b6e677573350a4e4879623168325569363331635a76342b4a6f53306f397749766b557647306a4a4456534f2f446c74774b4267514471763862456f7855764b6c57515471542b0a484371776d32782f4a3043707032517269626d73784b47626f30424361652b38314e633752764f613173776c6450645352665558507a4c766c6249497134676d0a6656387558794e50595350692b5763457a706d726472472b5a7567566f364e3851334b78327973686c2b47444c755a6577456b77574635594e4d6877512b48370a4b4d4176713532444e524b54596d36744e6c56774e3465534e774b42675143377944554f7a306c42516144754973393347335638634a543735796e4e394e336d0a663051337441633350466d446e3758506a4a48585753766f4450682b31554352332b777973706a794c6d4e7867644a746945346c32476169596336797a33486e0a6b384567577736755249595a514a3546617a477559587453416e6d7866766666692f77735a496e306f2b2b634e587644776e6d456a633046734d6e73314179470a4e532b34397053304b774b4267466b4955304c5139332f6a396e2b3831436273562b53546a68724c73474b6e38663378526c4b5959524b2b582b6a51645053520a5a50412b674c59424d58776a57496f44726d6b6174783758443662714a3845785736416978536d6546685a4873534c4a6d4d374850624b524a51545141336c6c0a75324a70565870774f442b67306736747278522b37346c5575354359726d53726c2f6838686b6a31494135324472507a4834526f43797352416f4741513939780a6a68444f59592f66497a506832534e4c7139626c6773646a444e5a632f6c7378785243464b796e64455035424d4f75574b306848336e415277595a432b48622f0a594c4f394a497776315738664b41674564786c6f763369717857624676505a69373962357a334e6c4a4f742b53596b64512f4a6f4b4a524d65434e305a4a43730a6254394a7665736a534572736d53314a7a7565534732527a462b37744e2f5578637146747a6c4543675942574936336b654b58506236365544655034363546470a7466756159435030526b5a776453652b737a644b396e587a2f50634b42663053342f6977746d4b42676f384d50363059572b797777302f73356a534c344450680a446834316f4b43373738475837374a4f625638534f486b44557a6255456d4e7252694b6f4a3774674c62343042536e663555515338496c6d3873792f38376c440a41624f3259623558477056344641674b4e6d75737a773d3d0a2d2d2d2d2d454e442050524956415445204b45592d2d2d2d2d0a
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/03-stegorsa]
└─$ exiftool -s3 -Comment image.jpg > clave_hex.txt
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/03-stegorsa]
└─$ openssl pkey -in privada.pem -check -noout
Could not open file or uri for loading private key of key from privada.pem: No such file or directory
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/03-stegorsa]
└─$ openssl pkeyutl -decrypt -inkey privada.pem -in flag.enc -pkeyopt rsa_padding_mode:pkcs1 -out flag.txt
cat flag.txt
Could not open file or uri for loading private key from privada.pem: No such file or directory
pkeyutl: Error loading key
cat: flag.txt: No such file or directory
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/03-stegorsa]
└─$ 
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/03-stegorsa]
└─$ xxd -r -p clave_hex.txt > privada.pem
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/03-stegorsa]
└─$ head -n 1 privada.pem
-----BEGIN PRIVATE KEY-----
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/03-stegorsa]
└─$ openssl pkey -in privada.pem -check -noout
Key is valid
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/03-stegorsa]
└─$ openssl pkeyutl -decrypt -inkey privada.pem -in flag.enc -pkeyopt rsa_padding_mode:pkcs1 -out flag.txt
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/03-stegorsa]
└─$ cat flag.txt
academy{rs4_k3y_1n_1mg_d97b7bfb}
```
```

```
```
```
```

```

## Notas Adicionales
- La clave privada completa está filtrada en los metadatos. Recuperarla permite descifrar el archivo directamente.
## Referencias
