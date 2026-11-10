## Descripción
What does asm1(0x31e) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://challenge-files.cylabacademy.net/library/ecdcfe0ee1b9b4189f78f6f08260b2a0d4b94eb22077345c817ea8b9cda064ac/test.S)

1.- assembly [conditions](https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm)
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p /tmp/asm1 && cd /tmp/asm1
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[/tmp/asm1]
└─$ wget https://challenge-files.cylabacademy.net/library/ecdcfe0ee1b9b4189f78f6f08260b2a0d4b94eb22077345c817ea8b9cda064ac/test.S
--2026-11-09 12:22:01--  https://challenge-files.cylabacademy.net/library/ecdcfe0ee1b9b4189f78f6f08260b2a0d4b94eb22077345c817ea8b9cda064ac/test.S
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.66, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 644 [application/octet-stream]
Saving to: ‘test.S’

test.S                                                     100%[========================================================================================================================================>]     644  --.-KB/s    in 0s      

2026-11-09 12:22:01 (38.5 MB/s) - ‘test.S’ saved [644/644]

                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[/tmp/asm1]
└─$ cat test.S
asm1:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   cmp    DWORD PTR [ebp+0x8],0x2fa
        <+10>:  jg     0x11a2 <asm1+37>
        <+12>:  cmp    DWORD PTR [ebp+0x8],0x14b
        <+19>:  jne    0x119a <asm1+29>
        <+21>:  mov    eax,DWORD PTR [ebp+0x8]
        <+24>:  add    eax,0x17
        <+27>:  jmp    0x11b9 <asm1+60>
        <+29>:  mov    eax,DWORD PTR [ebp+0x8]
        <+32>:  sub    eax,0x17
        <+35>:  jmp    0x11b9 <asm1+60>
        <+37>:  cmp    DWORD PTR [ebp+0x8],0x31e
        <+44>:  jne    0x11b3 <asm1+54>
        <+46>:  mov    eax,DWORD PTR [ebp+0x8]
        <+49>:  sub    eax,0x17
        <+52>:  jmp    0x11b9 <asm1+60>
        <+54>:  mov    eax,DWORD PTR [ebp+0x8]
        <+57>:  add    eax,0x17
        <+60>:  pop    ebp
        <+61>:  ret

                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[/tmp/asm1]
└─$ python3 -c 'print(hex(0x31e - 0x17))'

0x307

```
```

```

## Notas Adicionales

## Referencias
-- [https://www.felixcloutier.com/x86/cmp](https://www.felixcloutier.com/x86/cmp)
- [https://www.felixcloutier.com/x86/jcc](https://www.felixcloutier.com/x86/jcc)