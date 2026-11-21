## Descripción
The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://challenge-files.cylabacademy.net/library/6dfc63d7e4ee66dec270d4f50ae9e6c2b1ed3c6364b723c94f23210d2ab91740/need-for-speed)

1.- What is the final key?
## Solución
```
mkdir -p ~/reverse_cipher && cd ~/reverse_cipher

wget -O rev https://challenge-files.cylabacademy.net/library/4de47cc73b1c6e4976e058249b7181cfe15c64e28b5a4a0a54edefdf6608f118/rev

wget -O rev_this https://challenge-files.cylabacademy.net/library/4de47cc73b1c6e4976e058249b7181cfe15c64e28b5a4a0a54edefdf6608f118/rev_this

objdump -d -M intel rev | less

python3 - <<'PY'
from pathlib import Path

data = bytearray(Path("rev_this").read_bytes())

for i in range(8, len(data) - 1):
    if i % 2 == 0:
        data[i] = (data[i] - 5) % 256
    else:
        data[i] = (data[i] + 2) % 256

print(data.decode())
PY

academy{r3v3rs354680934}
```
```

```

## Notas Adicionales

## Referencias