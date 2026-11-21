## Descripción
Decode this [message](https://challenge-files.cylabacademy.net/library/d825fde6581b1311eafdd403da1cc96f1f98fe3fe84cd71d850310ebb3908088/message.wav) from the moon.

1.- How did pictures from the moon landing get sent back to Earth?

2.- What is the CMU mascot?, that might help select a RX option
## Solución
```
┌──(kali㉿kali)-[~]
└─$ git clone https://github.com/colaclanth/sstv.git
fatal: destination path 'sstv' already exists and is not an empty directory.
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ cd sstv
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/sstv]
└─$ python3 -m venv .venv
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/sstv]
└─$ source .venv/bin/activate
                                                                                                                                                                                                                                           
┌──(.venv)─(kali㉿kali)-[~/sstv]
└─$ pip list | grep -i sstv
sstv        0.1
                                                                                                                                                                                                                                           
┌──(.venv)─(kali㉿kali)-[~/sstv]
└─$ sstv -d ~/Downloads/message.wav -o ~/Downloads/flag.png
usage: sstv [-h] [-d AUDIO_FILE] [-o OUTPUT_FILE] [-s SKIP] [-V] [--list-modes] [--list-audio-formats] [--list-image-formats]
sstv: error: argument -d/--decode: can't open '/home/kali/Downloads/message.wav': [Errno 2] No such file or directory: '/home/kali/Downloads/message.wav'
                                                                                                                                                                                                                                           
┌──(.venv)─(kali㉿kali)-[~/sstv]
└─$ xdg-open ~/Downloads/flag.png
                                                                                                                                                                                                                                           
┌──(.venv)─(kali㉿kali)-[~/sstv]
└─$ ls                           
build  examples  LICENSE  README.md  setup.py  sstv  sstv.egg-info  test
                                                                                                                                                                                                                                           
┌──(.venv)─(kali㉿kali)-[~/sstv]
└─$ cd ~/         
                                                                                                                                                                                                                                           
┌──(.venv)─(kali㉿kali)-[~]
└─$ cd ~/Downloads
                                                                                                                                                                                                                                           
┌──(.venv)─(kali㉿kali)-[~/Downloads]
└─$ wget https://challenge-files.cylabacademy.net/library/d825fde6581b1311eafdd403da1cc96f1f98fe3fe84cd71d850310ebb3908088/message.wav
--2026-09-30 21:44:58--  https://challenge-files.cylabacademy.net/library/d825fde6581b1311eafdd403da1cc96f1f98fe3fe84cd71d850310ebb3908088/message.wav
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.22, 13.226.187.40, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.37|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 11066998 (11M) [application/octet-stream]
Saving to: ‘message.wav’

message.wav                                                100%[=======================================================================================================================================>]  10.55M  12.8MB/s    in 0.8s    

2026-09-30 21:44:59 (12.8 MB/s) - ‘message.wav’ saved [11066998/11066998]

                                                                                                                                                                                                                                           
┌──(.venv)─(kali㉿kali)-[~/Downloads]
└─$ ls -l ~/Downloads/message.wav
-rw-rw-r-- 1 kali kali 11066998 Sep 22 21:47 /home/kali/Downloads/message.wav
                                                                                                                                                                                                                                           
┌──(.venv)─(kali㉿kali)-[~/Downloads]
└─$ cd ~/sstv
                                                                                                                                                                                                                                           
┌──(.venv)─(kali㉿kali)-[~/sstv]
└─$ source .venv/bin/activate
                                                                                                                                                                                                                                           
┌──(.venv)─(kali㉿kali)-[~/sstv]
└─$ sstv -d ~/Downloads/message.wav -o ~/Downloads/flag.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...                                                                                                        [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                                                                                                                                                                                           
┌──(.venv)─(kali㉿kali)-[~/sstv]
└─$ xdg-open ~/Downloads/flag.png



picoCTF{beep_boop_im_in_space}
```
```

```

## Notas Adicionales

## Referencias
