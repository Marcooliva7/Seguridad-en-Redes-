## Descripción
Python scripts are invoked kind of like programs in the Terminal... Can you run [ende.py](https://challenge-files.cylabacademy.net/library/6d20533ced9029ce644ff2c2bcaaa8a7c95b46963bfde810a8d69484d1db4ccd/ende.py) using [password.txt](https://challenge-files.cylabacademy.net/library/6d20533ced9029ce644ff2c2bcaaa8a7c95b46963bfde810a8d69484d1db4ccd/password.txt) to get [flag.txt.en](https://challenge-files.cylabacademy.net/library/6d20533ced9029ce644ff2c2bcaaa8a7c95b46963bfde810a8d69484d1db4ccd/flag.txt.en)?

1.- Get the Python script accessible in your shell by entering the following command in the Terminal prompt: `$ wget` followed by a link to the script. The link can be copied from the details section.

2.- `$ man python`
## Solución
```
┌──(kali㉿kali)-[~]
└─$ ls
Desktop  Documents  Downloads  ende.py  flag.txt.en  LaboratorioSeguridad  Music  password.txt  Pictures  Public  Templates  Videos
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ cat ende.py 

import sys
import base64
from cryptography.fernet import Fernet



usage_msg = "Usage: "+ sys.argv[0] +" (-e/-d) [file]"
help_msg = usage_msg + "\n" +\
        "Examples:\n" +\
        "  To decrypt a file named 'pole.txt', do: " +\
        "'$ python "+ sys.argv[0] +" -d pole.txt'\n"



if len(sys.argv) < 2 or len(sys.argv) > 4:
    print(usage_msg)
    sys.exit(1)



if sys.argv[1] == "-e":
    if len(sys.argv) < 4:
        sim_sala_bim = input("Please enter the password:")
    else:
        sim_sala_bim = sys.argv[3]

    ssb_b64 = base64.b64encode(sim_sala_bim.encode())
    c = Fernet(ssb_b64)

    with open(sys.argv[2], "rb") as f:
        data = f.read()
        data_c = c.encrypt(data)
        sys.stdout.write(data_c.decode())


elif sys.argv[1] == "-d":
    if len(sys.argv) < 4:
        sim_sala_bim = input("Please enter the password:")
    else:
        sim_sala_bim = sys.argv[3]

    ssb_b64 = base64.b64encode(sim_sala_bim.encode())
    c = Fernet(ssb_b64)

    with open(sys.argv[2], "r") as f:
        data = f.read()
        data_c = c.decrypt(data.encode())
        sys.stdout.buffer.write(data_c)


elif sys.argv[1] == "-h" or sys.argv[1] == "--help":
    print(help_msg)
    sys.exit(1)


else:
    print("Unrecognized first argument: "+ sys.argv[1])
    print("Please use '-e', '-d', or '-h'.")

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ python3 ende.py                                                            
Usage: ende.py (-e/-d) [file]
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ python3 ende.py
Usage: ende.py (-e/-d) [file]
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ python3 ende.py -d flag.txt.en
Please enter the password:^CTraceback (most recent call last):
  File "/home/kali/ende.py", line 39, in <module>
    sim_sala_bim = input("Please enter the password:")
KeyboardInterrupt

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ ls         
Desktop  Documents  Downloads  ende.py  flag.txt.en  LaboratorioSeguridad  Music  password.txt  Pictures  Public  Templates  Videos
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ cat password.txt 
563e47ddeaf84eca8b2a31201381a898
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ python3 ende.py -d flag.txt.en
Please enter the password:563e47ddeaf84eca8b2a31201381a898
academy{4p0110_1n_7h3_h0us3_d6af8f37}



academy{4p0110_1n_7h3_h0us3_d6af8f37}
```

## Notas Adicionales

## Referencias
-