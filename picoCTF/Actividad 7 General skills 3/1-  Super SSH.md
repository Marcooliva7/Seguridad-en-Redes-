## Descripción
Using a Secure Shell (SSH) is going to be pretty important.

Can you `ssh` as `ctf-player` to `titan.picoctf.net` at port `60058` to get the flag?

You'll also need the password `1db87a14`. If asked, accept the fingerprint with `yes`.

If your device doesn't have a shell, you can use: [](https://webshell.picoctf.org/)[https://webshell.picoctf.org](https://webshell.picoctf.org/)

If you're not sure what a shell is, check out our Primer: [](https://primer.picoctf.com/#_the_shell)[https://primer.picoctf.com/#_the_shell](https://primer.picoctf.com/#_the_shell)
## Solución
```
ssh ctf-player@titan.picoctf.net -p 64321
The authenticity of host '[titan.picoctf.net]:64321 ([3.139.174.234]:64321)' can't be established.
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[titan.picoctf.net]:64321' (ED25519) to the list of known hosts.
ctf-player@titan.picoctf.net's password: 
Connection closed by 3.139.174.234 port 64321
XlayersCeboso-academy@webshell:~$ ssh ctf-player@titan.picoctf.net -p 64321
ctf-player@titan.picoctf.net's password: 
Welcome ctf-player, here's your flag: academy{s3cur3_c0nn3ct10n_fbd97b2a}
Connection to titan.picoctf.net closed.
```
```

```

## Notas Adicionales

## Referencias
- [ttps://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)
- [https://linux.die.net/man/1/ssh](https://linux.die.net/man/1/ssh)
-