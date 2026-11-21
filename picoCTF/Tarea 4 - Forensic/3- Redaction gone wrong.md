## Descripción
Now you DON’T see me. This [report](https://challenge-files.cylabacademy.net/library/455e6e9581a9272cf0cd6a8f2da0a7cdcfefdb52dc7a7f9c09a27705e2c94103/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

1.- How can you be sure of the redaction?
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/picoctf/redaction
                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ cd ~/picoctf/redaction
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/redaction]
└─$ curl -L --fail --show-error -o report.pdf 'https://challenge-files.cylabacademy.net/library/455e6e9581a9272cf0cd6a8f2da0a7cdcfefdb52dc7a7f9c09a27705e2c94103/Financial_Report_for_ABC_Labs.pdf'
  % Total    % Received % Xferd  Average Speed  Time    Time    Time   Current
                                 Dload  Upload  Total   Spent   Left   Speed
100   1817 100   1817   0      0  10395      0                              0
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/redaction]
└─$ sudo apt update
[sudo] password for kali: 
Hit:1 http://http.kali.org/kali kali-rolling InRelease
950 packages can be upgraded. Run 'apt list --upgradable' to see them.
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/redaction]
└─$ sudo apt install -y poppler-utils        
poppler-utils is already the newest version (26.07.0-2).
poppler-utils set to manually installed.
Summary:                    
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 950
                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/redaction]
└─$ pdftotext -layout report.pdf -
Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.

Breakdown - Just painted over in MS word.



Cost Benefit Analysis

Credit             Debit



This is not the flag, keep looking



Expenses from the

academy{C4n_Y0u_S33_m3_fully}



Redacted document.

                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/redaction]
└─$ pdftotext -layout report.pdf - | grep -oE 'academy\{[^}]+\}'
academy{C4n_Y0u_S33_m3_fully}
                                


academy{C4n_Y0u_S33_m3_fully}
```
```

```

## Notas Adicionales

## Referencias
