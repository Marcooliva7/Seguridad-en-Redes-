## Descripción
An attacker was able to intercept communications between a bank and a fintech company. They managed to get the [message](https://challenge-files.cylabacademy.net/library/1b39f2751ae1461b00924da90f25e9803b0cee634d2244dccf6554277057994e/secret.enc) (ciphertext) and the [password](https://challenge-files.cylabacademy.net/library/1b39f2751ae1461b00924da90f25e9803b0cee634d2244dccf6554277057994e/password.enc) that was used to encrypt the message. After some intensive reconassainance they found out that the bank has an oracle that was used to encrypt the password and can be found here nc chatelaine.cylabacademy.net 48712. Decrypt the password and use it to decrypt the message. The oracle can decrypt anything except the password.

1.- Crytography Threat models: chosen plaintext attack.

2.- OpenSSL can be used to decrypt the message. e.g `openssl enc -aes-256-cbc -d ...`

3.- The key to getting the flag is by sending a custom message to the server by taking advantage of the RSA encryption algorithm.

4.- Minimum requirements for a useful cryptosystem is CPA security.
## Solución
```
mkdir -p /tmp/rsa-oracle && cd /tmp/rsa-oracle

wget https://challenge-files.cylabacademy.net/library/1b39f2751ae1461b00924da90f25e9803b0cee634d2244dccf6554277057994e/password.enc

wget https://challenge-files.cylabacademy.net/library/1b39f2751ae1461b00924da90f25e9803b0cee634d2244dccf6554277057994e/secret.enc

sudo apt update && sudo apt install python3-pwntools -y

openssl enc -aes-256-cbc -d -in secret.enc

academy{su((3ss_(r@ck1ng_r3@_20373ec2}

```
```

```

## Notas Adicionales
- RSA sin relleno seguro es multiplicativamente maleable: modificar el ciphertext de esta manera permite obtener información sobre el mensaje original. El oráculo evita el descifrado directo, pero la restricción no impide este ataque de texto elegido.
## Referencias
- Reto y archivos: [rsa_oracle](https://challenge-files.cylabacademy.net/library/1b39f2751ae1461b00924da90f25e9803b0cee634d2244dccf6554277057994e/)
- Servicio: `nc chatelaine.cylabacademy.net 48712`
- [https://gabbage.medium.com/rsa-oracle-guide-picoctf-54372033eadb](https://gabbage.medium.com/rsa-oracle-guide-picoctf-54372033eadb)