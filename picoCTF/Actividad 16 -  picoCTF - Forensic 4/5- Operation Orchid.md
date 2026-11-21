## Descripción
Download this disk image and find the flag.

Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://challenge-files.cylabacademy.net/library/7d645367284f9df9139dd5ad212e5c3bd0815b7674ca700648a3983158394892/disk.flag.img.gz)
## Solución
```
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/7d645367284f9df9139dd5ad212e5c3bd0815b7674ca700648a3983158394892/disk.flag.img.gz
--2026-10-07 13:54:02--  https://challenge-files.cylabacademy.net/library/7d645367284f9df9139dd5ad212e5c3bd0815b7674ca700648a3983158394892/disk.flag.img.gz
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.66, 13.226.187.37, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 44360921 (42M) [application/octet-stream]
Saving to: ‘disk.flag.img.gz’

disk.flag.img.gz                                           100%[=======================================================================================================================================>]  42.31M  3.49MB/s    in 11s     

2026-10-07 13:54:15 (3.82 MB/s) - ‘disk.flag.img.gz’ saved [44360921/44360921]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ gzip -d disk.flag.img.gz
gzip: disk.flag.img already exists; do you wish to overwrite (y or n)? y
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ mmls disk.flag.img        
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
                                                                                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ fls -r -o 411648 disk.flag.img | grep -E 'flag|ash_history'
+ r/r 1875:     .ash_history
+ r/r * 1876(realloc):  flag.txt
+ r/r 1782:     flag.txt.enc
                                                                                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ icat -o 411648 disk.flag.img 1875
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
                                                                                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ icat -o 411648 disk.flag.img 1782 > flag.txt.enc
                                                                                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ openssl aes256 -d -salt -in flag.txt.enc -out flag.txt -k 'unbreakablepassword1234567'
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
80D71303FD7E0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
                                                                                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ cat flag.txt
academy{h4un71ng_p457_718ebd29}


academy{h4un71ng_p457_0b36d810}
```
```

```

## Notas Adicionales

## Referencias
