## Descripción
Download this disk image, find the key and log into the remote machine.

Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download disk image](https://challenge-files.cylabacademy.net/library/bac64668d6b7caead36e15b7bfc362eeea2c831d367e655a082b9fe63bd85610/disk.img.gz)
- Remote machine: `ssh -i key_file -p 39777 ctf-player@chatelaine.cylabacademy.net`
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p /tmp/operation-oni && cd /tmp/operation-oni
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[/tmp/operation-oni]
└─$ wget https://challenge-files.cylabacademy.net/library/bac64668d6b7caead36e15b7bfc362eeea2c831d367e655a082b9fe63bd85610/disk.img.gz
--2026-10-07 17:08:29--  https://challenge-files.cylabacademy.net/library/bac64668d6b7caead36e15b7bfc362eeea2c831d367e655a082b9fe63bd85610/disk.img.gz
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.66, 13.226.187.40, 13.226.187.37, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.66|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 48132743 (46M) [application/octet-stream]
Saving to: ‘disk.img.gz’

disk.img.gz                                                100%[=======================================================================================================================================>]  45.90M  3.76MB/s    in 11s     

2026-10-07 17:08:40 (4.14 MB/s) - ‘disk.img.gz’ saved [48132743/48132743]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[/tmp/operation-oni]
└─$ gzip -d disk.img.gz
gzip: disk.img already exists; do you wish to overwrite (y or n)? y
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[/tmp/operation-oni]
└─$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[/tmp/operation-oni]
└─$ fls -r -o 206848 disk.img | grep id_ed25519
++ r/r 2345:    id_ed25519
++ r/r 2346:    id_ed25519.pub
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[/tmp/operation-oni]
└─$ icat -o 206848 disk.img 2345 > key_file
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[/tmp/operation-oni]
└─$ chmod 600 key_file
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[/tmp/operation-oni]
└─$ ssh -i key_file -p 36778 ctf-player@chatelaine.cylabacademy.net
The authenticity of host '[chatelaine.cylabacademy.net]:36778 ([18.227.187.235]:36778)' can't be established.
ED25519 key fingerprint is: SHA256:ZzFWPkrkkhq4v3aMejPdeBM6CxOJEdDfCOqwc0eXgfY
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[chatelaine.cylabacademy.net]:36778' (ED25519) to the list of known hosts.
Welcome to Ubuntu 24.04.4 LTS (GNU/Linux 7.0.0-1013-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ cat flag.txt
academy{k3y_5l3u7h_127b8b44}ctf-player@challenge:~$ Connection to chatelaine.cylabacademy.net closed by remote host.
Connection to chatelaine.cylabacademy.net closed.


academy{k3y_5l3u7h_f52dbc2c}
```
```

```

## Notas Adicionales

## Referencias
