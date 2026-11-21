## Descripción
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility.

The source code for the training vault is here: [VaultDoorTraining.java](https://challenge-files.cylabacademy.net/library/78ec91618d4c4219c55fbe2c9fc67ec6e248664564e6b2f13a54534aaf1d1000/VaultDoorTraining.java)
## Solución
```
mkdir -p ~/vault-door-training
cd ~/vault-door-training
wget -O VaultDoorTraining.java 'https://challenge-files.cylabacademy.net/library/78ec91618d4c4219c55fbe2c9fc67ec6e248664564e6b2f13a54534aaf1d1000/VaultDoorTraining.java'
cat VaultDoorTraining.java

awk -F'"' '/return password[.]equals/ {printf "academy{%s}\n", $2}' VaultDoorTraining.java


academy{w4rm1ng_Up_w1tH_jAv4_8352733cecd}
```
```

```

## Notas Adicionales

## Referencias