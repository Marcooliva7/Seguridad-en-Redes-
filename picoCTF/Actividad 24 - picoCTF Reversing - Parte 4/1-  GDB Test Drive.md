## Descripción
Can you get the flag? Download this [binary](https://challenge-files.cylabacademy.net/library/4923664c378efee1cf819f12d90c49c484d3749bfebe4e0c13976ca588154f37/gdbme).

Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`
## Solución
```
wget -O gdbme https://challenge-files.cylabacademy.net/library/4923664c378efee1cf819f12d90c49c484d3749bfebe4e0c13976ca588154f37/gdbme

chmod +x gdbme

gdb ./gdbme

layout asm

break *(main+99)

run

jump *(main+104)

academy{d3bugg3r_dr1v3_4cc75120}
```
```

```

## Notas Adicionales

## Referencias