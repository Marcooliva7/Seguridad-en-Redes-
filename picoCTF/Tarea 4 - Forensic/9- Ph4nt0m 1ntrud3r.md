## Descripción
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.

To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!

Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.cylabacademy.net/library/828ca80eed550dbc9645ad6c2aa5c2061b2dd2e8e4098b1c7fe6d639459ea5a5/myNetworkTraffic.pcap) and try to get the flag.

1.- Filter your packets to narrow down your search.

2.- Attacks were done in timely manner.

3.- Time is essential
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf/phantom
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ cd ~/picoctf/phantom
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/phantom]
└─$ curl -L --fail --show-error -o myNetworkTraffic.pcap 'https://challenge-files.cylabacademy.net/library/828ca80eed550dbc9645ad6c2aa5c2061b2dd2e8e4098b1c7fe6d639459ea5a5/myNetworkTraffic.pcap'
  % Total    % Received % Xferd  Average Speed  Time    Time    Time   Current
                                 Dload  Upload  Total   Spent   Left   Speed
100   1452 100   1452   0      0   4185      0                              0
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/phantom]
└─$ python3 - <<'PY'
import base64
import struct

parts = []
with open('myNetworkTraffic.pcap', 'rb') as capture:
    capture.read(24)  # Cabecera del PCAP
    while header := capture.read(16):
        seconds, microseconds, size, _ = struct.unpack('<IIII', header)
        packet = capture.read(size)
        if packet[9] != 6:  # TCP
            continue

        ip_size = (packet[0] & 15) * 4
        tcp = packet[ip_size:]
        tcp_size = (tcp[12] >> 4) * 4
        payload = tcp[tcp_size:]

        try:
            text = base64.b64decode(payload, validate=True).decode('ascii')
        except (ValueError, UnicodeDecodeError):
            continue
        if text.isprintable():
            parts.append((seconds, microseconds, text))

for _, _, text in sorted(parts):
    print(text)
print('Bandera:', ''.join(text for _, _, text in sorted(parts)))
PY
academy
{1t_w4s
nt_th4t
_34sy_t
bh_4r_6
b09861f
}
Bandera: academy{1t_w4snt_th4t_34sy_tbh_4r_a55faeed}



academy{1t_w4snt_th4t_34sy_tbh_4r_a55faeed}
```
```

```

## Notas Adicionales

## Referencias


