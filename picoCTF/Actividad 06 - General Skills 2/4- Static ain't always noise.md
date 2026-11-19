## Descripción

Can you look at the data in this binary? The bash script might help!
## Solución
```
Obtengo ambos archivos con wget.
wget https://challenge-files.picoctf.net/c_wily_courier/418e2775a501eaabeb99a96c5c467a83539369fe9649e8234644250cfb72d717/static

wget https://challenge-files.picoctf.net/c_wily_courier/418e2775a501eaabeb99a96c5c467a83539369fe9649e8234644250cfb72d717/ltdis.sh

XlayersCeboso-academy@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  HOLA  HOLA.txt  README.txt  file  file.1  flag  hola  koala  ltdis.sh  ltdis.sh.1  salida.txt  static  static.1  strings  warm
XlayersCeboso-academy@webshell:~$ file ltdis.sh
ltdis.sh: Bourne-Again shell script, ASCII text executable
XlayersCeboso-academy@webshell:~$ cat ltdis.sh
#!/bin/bash



echo "Attempting disassembly of $1 ..."


#This usage of "objdump" disassembles all (-D) of the first file given by 
#invoker, but only prints out the ".text" section (-j .text) (only section
#that matters in almost any compiled program...

objdump -Dj .text $1 > $1.ltdis.x86_64.txt


#Check that $1.ltdis.x86_64.txt is non-empty
#Continue if it is, otherwise print error and eject

if [ -s "$1.ltdis.x86_64.txt" ]
then
        echo "Disassembly successful! Available at: $1.ltdis.x86_64.txt"

        echo "Ripping strings from binary with file offsets..."
        strings -a -t x $1 > $1.ltdis.strings.txt
        echo "Any strings found in $1 have been written to $1.ltdis.strings.txt with file offset"



else
        echo "Disassembly failed!"
        echo "Usage: ltdis.sh <program-file>"
        echo "Bye!"
fi
XlayersCeboso-academy@webshell:~$ cat static.ltdis.strings.txt | grep pico
cat: static.ltdis.strings.txt: No such file or directory
XlayersCeboso-academy@webshell:~$ bash ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
XlayersCeboso-academy@webshell:~$ cat static.ltdis.strings.txt | grep pico
   3020 
   
   academy{d15a5m_t34s3r_fac3431a}
```
```

```

## Notas Adicionales

## Referencias
-- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)