## Descripción
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://challenge-files.cylabacademy.net/library/e4963169ad8e63b55d19fbf55ec800339ef0aa77274fdf2f1bdb7632246d514d/VaultDoor5.java)

1.- You may find an encoder/decoder tool helpful, such as [https://encoding.tools/](https://encoding.tools/)

2.- Read the wikipedia articles on URL encoding and base 64 encoding to understand how they work and what the results look like.
## Solución
```
mkdir -p ~/vault-door-5
cd ~/vault-door-5
wget -O VaultDoor5.java 'https://challenge-files.cylabacademy.net/library/e4963169ad8e63b55d19fbf55ec800339ef0aa77274fdf2f1bdb7632246d514d/VaultDoor5.java'
cat VaultDoor5.java
nano exp.py

python3 exp.py

academy{c0nv3rt1ng_fr0m_ba5e_64_3cc8a9d6}
```
```

```

## Notas Adicionales

## Referencias