## Descripción
Find the flag in this [picture](https://challenge-files.cylabacademy.net/library/8179732d3bcbaaf9dadfc7fe08aa5b7fbf1d3189b0a2dc90eca34dca38a85b4a/pico_img.png)

1.- What does meta mean in the context of files?

2.- Ever heard of metadata?
## Solución
```
┌──(kali㉿kali)-[~]
└─$ exiftool pico_img.png
ExifTool Version Number         : 13.55
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2026:09:22 21:49:08-04:00
File Access Date/Time           : 2026:09:28 12:45:27-04:00
File Inode Change Date/Time     : 2026:09:28 12:45:17-04:00
File Permissions                : -rw-rw-r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Artist                          : academy{s0_m3ta_45015e26}
Image Size                      : 600x600
Megapixels                      : 0.360
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/8179732d3bcbaaf9dadfc7fe08aa5b7fbf1d3189b0a2dc90eca34dca38a85b4a/pico_img.png
--2026-09-28 12:53:23--  https://challenge-files.cylabacademy.net/library/8179732d3bcbaaf9dadfc7fe08aa5b7fbf1d3189b0a2dc90eca34dca38a85b4a/pico_img.png
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.22, 13.226.187.66, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.37|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108795 (106K) [application/octet-stream]
Saving to: ‘pico_img.png.1’

pico_img.png.1                                             100%[=======================================================================================================================================>] 106.25K  --.-KB/s    in 0.1s    

2026-09-28 12:53:24 (748 KB/s) - ‘pico_img.png.1’ saved [108795/108795]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ open pico_img.png                                                                                                                  
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ file pico_img.png                                                                                                                  
pico_img.png: PNG image data, 600 x 600, 8-bit/color RGB, non-interlaced
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ exiftool pico_img.png                                                                                                              
ExifTool Version Number         : 13.55
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2026:09:22 21:49:08-04:00
File Access Date/Time           : 2026:09:28 12:45:27-04:00
File Inode Change Date/Time     : 2026:09:28 12:45:17-04:00
File Permissions                : -rw-rw-r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Artist                          : academy{s0_m3ta_45015e26}
Image Size                      : 600x600
Megapixels                      : 0.360


┌──(kali㉿kali)-[~]
└─$ strings -n 20 pico_img.png | grep academy 
academy{s0_m3ta_d4aa0408}


academy{s0_m3ta_d4aa0408}
```
```

```

## Notas Adicionales
Los metadatos son datos sobre los datos. es una descripción de los datos que están adentro.
## Referencias
