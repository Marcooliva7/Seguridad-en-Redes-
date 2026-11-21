## Descripción
We have recovered a [binary](https://challenge-files.cylabacademy.net/library/4de47cc73b1c6e4976e058249b7181cfe15c64e28b5a4a0a54edefdf6608f118/rev) and a [text file](https://challenge-files.cylabacademy.net/library/4de47cc73b1c6e4976e058249b7181cfe15c64e28b5a4a0a54edefdf6608f118/rev_this). Can you reverse the flag.

1.- objdump and Gihdra are some tools that could assist with this
## Solución
```
wget -O need-for-speed https://challenge-files.cylabacademy.net/library/6dfc63d7e4ee66dec270d4f50ae9e6c2b1ed3c6364b723c94f23210d2ab91740/need-for-speed

chmod +x need-for-speed

objdump -d -M intel need-for-speed | less

gdb ./need-for-speed

break main

run

set variable key = 0xdf489ce8

call (void) print_flag()

academy{Good job keeping bus #1fb8d167 speeding along!}
```
```

```

## Notas Adicionales

## Referencias