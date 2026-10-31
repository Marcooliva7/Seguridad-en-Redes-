## Descripción
Can you get sense of this code file and write the function that will decode the given encrypted file content.

Find the encrypted file here [flag_info](https://challenge-files.cylabacademy.net/library/168dfb66953daef3e9c494a5ee63a78f09370e1e39d8b1489d5f9c090acd2a8f/enc_flag) and [code file](https://challenge-files.cylabacademy.net/library/168dfb66953daef3e9c494a5ee63a78f09370e1e39d8b1489d5f9c090acd2a8f/custom_encryption.py) might be good to analyze and get the flag.

1.- Understanding encryption algorithm to come up with decryption algorithm.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf-crypto/06-custom-encryption
cd ~/picoctf-crypto/06-custom-encryption
wget -O enc_flag 'https://challenge-files.cylabacademy.net/library/168dfb66953daef3e9c494a5ee63a78f09370e1e39d8b1489d5f9c090acd2a8f/enc_flag'
wget -O custom_encryption.py 'https://challenge-files.cylabacademy.net/library/168dfb66953daef3e9c494a5ee63a78f09370e1e39d8b1489d5f9c090acd2a8f/custom_encryption.py'
cat enc_flag
cat custom_encryption.py
--2026-10-26 23:53:47--  https://challenge-files.cylabacademy.net/library/168dfb66953daef3e9c494a5ee63a78f09370e1e39d8b1489d5f9c090acd2a8f/enc_flag
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.66, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 280 [application/octet-stream]
Saving to: ‘enc_flag’

enc_flag                     100%[=============================================>]     280  --.-KB/s    in 0s      

2026-10-26 23:53:48 (306 MB/s) - ‘enc_flag’ saved [280/280]

--2026-10-26 23:53:48--  https://challenge-files.cylabacademy.net/library/168dfb66953daef3e9c494a5ee63a78f09370e1e39d8b1489d5f9c090acd2a8f/custom_encryption.py
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.66, 13.226.187.37, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.66|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1411 (1.4K) [application/octet-stream]
Saving to: ‘custom_encryption.py’

custom_encryption.py         100%[=============================================>]   1.38K  --.-KB/s    in 0s      

2026-10-26 23:53:49 (31.2 MB/s) - ‘custom_encryption.py’ saved [1411/1411]

a = 91
b = 25
cipher is: [148347, 379109, 313177, 82415, 98898, 32966, 1137327, 1120844, 1054912, 692286, 0, 1368089, 346143, 82415, 1120844, 0, 362626, 1417538, 16483, 1021946, 395592, 445041, 98898, 98898, 280211, 98898, 428558, 197796, 412075, 379109, 280211, 82415, 98898, 0]
from random import randint
import sys


def generator(g, x, p):
    return pow(g, x) % p


def encrypt(plaintext, key):
    cipher = []
    for char in plaintext:
        cipher.append(((ord(char) * key*311)))
    return cipher


def is_prime(p):
    v = 0
    for i in range(2, p + 1):
        if p % i == 0:
            v = v + 1
    if v > 1:
        return False
    else:
        return True


def dynamic_xor_encrypt(plaintext, text_key):
    cipher_text = ""
    key_length = len(text_key)
    for i, char in enumerate(plaintext[::-1]):
        key_char = text_key[i % key_length]
        encrypted_char = chr(ord(char) ^ ord(key_char))
        cipher_text += encrypted_char
    return cipher_text


def test(plain_text, text_key):
    p = 97
    g = 31
    if not is_prime(p) and not is_prime(g):
        print("Enter prime numbers")
        return
    a = randint(p-10, p)
    b = randint(g-10, g)
    print(f"a = {a}")
    print(f"b = {b}")
    u = generator(g, a, p)
    v = generator(g, b, p)
    key = generator(v, a, p)
    b_key = generator(u, b, p)
    shared_key = None
    if key == b_key:
        shared_key = key
    else:
        print("Invalid key")
        return
    semi_cipher = dynamic_xor_encrypt(plain_text, text_key)
    cipher = encrypt(semi_cipher, shared_key)
    print(f'cipher is: {cipher}')


if __name__ == "__main__":
    message = sys.argv[1]
    test(message, "trudeau")
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/06-custom-encryption]
└─$ nano exp.py
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/06-custom-encryption]
└─$ python3 exp.py

academy{custom_d2cr0pt6d_5826e4ee}
```
```

```

## Notas Adicionales
- XOR se deshace aplicando de nuevo la misma clave.
- El script lee los parámetros de tu archivo para evitar copiar valores de otra instancia.
## Referencias
