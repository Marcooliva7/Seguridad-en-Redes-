## Descripción
We found this [packet capture](https://challenge-files.cylabacademy.net/library/f76620763560ca0683be36e0ed4648743f969ab4d852fda0d8fb4d3ae21a173d/shark-on-wire-2-capture.pcap). Recover the flag that was pilfered from the network.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ cd ~/Downloads
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ wget https://challenge-files.cylabacademy.net/library/f76620763560ca0683be36e0ed4648743f969ab4d852fda0d8fb4d3ae21a173d/shark-on-wire-2-capture.pcap
--2026-09-30 22:17:39--  https://challenge-files.cylabacademy.net/library/f76620763560ca0683be36e0ed4648743f969ab4d852fda0d8fb4d3ae21a173d/shark-on-wire-2-capture.pcap
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.22, 13.226.187.66, 13.226.187.37, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 112318 (110K) [application/octet-stream]
Saving to: ‘shark-on-wire-2-capture.pcap’

shark-on-wire-2-capture.pcap                               100%[=======================================================================================================================================>] 109.69K  --.-KB/s    in 0.05s   

2026-09-30 22:17:39 (2.07 MB/s) - ‘shark-on-wire-2-capture.pcap’ saved [112318/112318]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ tshark -r shark-on-wire-2-capture.pcap -Y "udp.dstport == 22 && udp.srcport > 5000 && udp.srcport <= 5200" -T fields -e udp.srcport
\5097
5099
5097
5100
5101
5109
5121
5123
5112
5049
5076
5076
5102
5051
5114
5051
5100
5095
5100
5097
5116
5097
5095
5118
5049
5097
5095
5115
5116
5051
5103
5048
5125
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ tshark -r shark-on-wire-2-capture.pcap -Y "udp.dstport == 22 && udp.srcport > 5000 && udp.srcport <= 5200" -T fields -e udp.srcport | awk '{printf "%c", $1-5000} END {print ""}' 
academy{p1LLf3r3d_data_v1a_st3g0}
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ 



academy{p1LLf3r3d_data_v1a_st3g0}
```
```

```

## Notas Adicionales

## Referencias
