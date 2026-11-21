## Descripción
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://challenge-files.cylabacademy.net/library/fa686cfe375627b0131e670a19ec4775a873562ee3006dae8a40796e3e2b5e3c/scrambled1.png) [scrambled2.png](https://challenge-files.cylabacademy.net/library/fa686cfe375627b0131e670a19ec4775a873562ee3006dae8a40796e3e2b5e3c/scrambled2.png)

1.-[https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)

2.- Think of different ways you can "stack" images
## Solución
```
wget: https://challenge-files.cylabacademy.net/library/fa686cfe375627b0131e670a19ec4775a873562ee3006dae8a40796e3e2b5e3c/scrambled1.png

wget: https://challenge-files.cylabacademy.net/library/fa686cfe375627b0131e670a19ec4775a873562ee3006dae8a40796e3e2b5e3c/scrambled2.png

from PIL import Image
import numpy as np

img1 = Image.open('scrambled1.png')
img2 = Image.open('scrambled2.png')

matriz1 = np.asarray(img1)
matriz2 = np.asarray(img2)

mflag = matriz1 + matriz2 

resultado = Image.fromarray(mflag.astype(np.uint8))
resultado.save('flag.png')

academy{2f16d0c4}
```
```

```

## Notas Adicionales
- La criptografía visual es una técnica criptográfica que permite cifrar información visual (imágenes, texto, etc.) de tal manera que la información descifrada aparezca como una imagen visual.
## Referencias
- [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)