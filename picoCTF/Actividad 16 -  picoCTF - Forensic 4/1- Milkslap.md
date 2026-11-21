## Descripción

1.- Look at the problem category
## Solución
```
Revisar la hoja de estilos para identificar la imagen que usa la página:
curl -s http://xebec.cylabacademy.net:17744/style.css | grep background-image

Descargar la imagen y confirmar su formato y dimensiones:
wget http://xebec.cylabacademy.net:17744/concat_v.png file concat_v.png

Instalar zsteg en Kali si aún no está disponible. La herramienta analiza datos ocultos en imágenes PNG y BMP:
sudo gem install zsteg

Buscar datos ocultos en la imagen:
zsteg -a concat_v.png


academy{imag3_m4n1pul4t10n_sl4p5}
```
```

```

## Notas Adicionales

## Referencias
