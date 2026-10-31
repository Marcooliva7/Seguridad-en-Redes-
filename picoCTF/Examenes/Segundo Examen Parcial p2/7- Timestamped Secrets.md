## Descripción
Someone encrypted a message using AES in ECB mode but they weren’t very careful with their key. Turns out it’s derived from something as simple as the current time! Can you uncover the key and decrypt the flag? Download the encrypted message: [message](https://challenge-files.cylabacademy.net/library/838909e4e064bca5edc41edd46ebb4f8350eb82f2aea2540ea564e491c6d437e/message.txt)  
You may also find the encryption script helpful: [code](https://challenge-files.cylabacademy.net/library/838909e4e064bca5edc41edd46ebb4f8350eb82f2aea2540ea564e491c6d437e/encryption.py)

1.- `encryption.py` is a redacted example of the program
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf-crypto/07-timestamped-secrets
cd ~/picoctf-crypto/07-timestamped-secrets
wget -O message.txt 'https://challenge-files.cylabacademy.net/library/838909e4e064bca5edc41edd46ebb4f8350eb82f2aea2540ea564e491c6d437e/message.txt'
wget -O encryption.py 'https://challenge-files.cylabacademy.net/library/838909e4e064bca5edc41edd46ebb4f8350eb82f2aea2540ea564e491c6d437e/encryption.py'
cat message.txt
cat encryption.py
--2026-10-26 23:55:59--  https://challenge-files.cylabacademy.net/library/838909e4e064bca5edc41edd46ebb4f8350eb82f2aea2540ea564e491c6d437e/message.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.66, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.37|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 135 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                  100%[=============================================>]     135  --.-KB/s    in 0s      

2026-10-26 23:56:00 (321 MB/s) - ‘message.txt’ saved [135/135]

--2026-10-26 23:56:00--  https://challenge-files.cylabacademy.net/library/838909e4e064bca5edc41edd46ebb4f8350eb82f2aea2540ea564e491c6d437e/encryption.py
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.66, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.37|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 629 [application/octet-stream]
Saving to: ‘encryption.py’

encryption.py                100%[=============================================>]     629  --.-KB/s    in 0s      

2026-10-26 23:56:01 (11.3 MB/s) - ‘encryption.py’ saved [629/629]

Hint: The encryption was done around 1790147519 UTC
Ciphertext (hex): 44e98ac8b821d1b561b49f38c114c89405c1895b1f9425b6adc8e0911b68731a
from hashlib import sha256
import time
from Crypto.Cipher import AES
from Crypto.Util.Padding import pad

def encrypt(plaintext: str, timestamp: int) -> str:
    timestamp = int(time.time())
    key = sha256(str(timestamp).encode()).digest()[:16]
    cipher = AES.new(key, AES.MODE_ECB)
    padded = pad(plaintext.encode(), AES.block_size)
    ciphertext = cipher.encrypt(padded)
    return ciphertext.hex()

if __name__ == "__main__":
  
    plaintext = "academy{...}"
    result = encrypt(plaintext, key)
    print(f"Hint: The encryption was done around {timestamp} UTC\n")
    print(f"Ciphertext (hex): {ciphertext.hex()}\n")
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/07-timestamped-secrets]
└─$ nano exp.py
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf-crypto/07-timestamped-secrets]
└─$ source ~/picoctf-crypto/entorno/bin/activate
python3 exp.py
academy{sa3S_sEc9t_3b464909}
```
```

```

## Notas Adicionales
- La clave se puede reconstruir porque depende de un timestamp revelado por la pista. Comprobé que recifrar la bandera con esa clave reproduce el archivo original.
## Referencias
