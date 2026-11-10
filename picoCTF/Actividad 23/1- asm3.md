## Descripción
What does asm3(0xcc000a09,0xcdb0b591,0xc1116756) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://challenge-files.cylabacademy.net/library/6c8bb7b347323c2e23b59e4c9e2a022f63c773e945a2c9b9dc445848256b732d/test.S)

1.- more(?) [registers](https://wiki.skullsecurity.org/index.php?title=Registers)
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p /tmp/asm3 && cd /tmp/asm3
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[/tmp/asm3]
└─$ wget https://challenge-files.cylabacademy.net/library/6c8bb7b347323c2e23b59e4c9e2a022f63c773e945a2c9b9dc445848256b732d/test.S
--2026-11-09 12:33:49--  https://challenge-files.cylabacademy.net/library/6c8bb7b347323c2e23b59e4c9e2a022f63c773e945a2c9b9dc445848256b732d/test.S
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.40, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.37|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 282 [application/octet-stream]
Saving to: ‘test.S’

test.S                                                     100%[========================================================================================================================================>]     282  --.-KB/s    in 0s      

2026-11-09 12:33:49 (571 MB/s) - ‘test.S’ saved [282/282]

                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[/tmp/asm3]
└─$ ls
test.S
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[/tmp/asm3]
└─$ cat test.S
asm3:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   xor    eax,eax
        <+5>:   mov    ah,BYTE PTR [ebp+0xb]
        <+8>:   shl    ax,0x10
        <+12>:  sub    al,BYTE PTR [ebp+0xe]
        <+15>:  add    ah,BYTE PTR [ebp+0xf]
        <+18>:  xor    ax,WORD PTR [ebp+0x12]
        <+22>:  nop
        <+23>:  pop    ebp
        <+24>:  ret

                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[/tmp/asm3]
└─$ python3 - <<'PY'
p1, p2, p3 = 0xcc000a09, 0xcdb0b591, 0xc1116756
eax = 0

ah = (p1 >> 24) & 0xff
eax = (eax & 0xffff00ff) | (ah << 8)

eax &= 0xffff0000

al = ((eax & 0xff) - ((p2 >> 16) & 0xff)) & 0xff
eax = (eax & 0xffffff00) | al

ah = (((eax >> 8) & 0xff) + ((p2 >> 24) & 0xff)) & 0xff
eax = (eax & 0xffff00ff) | (ah << 8)

ax = (eax & 0xffff) ^ ((p3 >> 16) & 0xffff)
eax = (eax & 0xffff0000) | ax

print(hex(eax))
PY
0xc7c
```
```

```

## Notas Adicionales

## Referencias
-