# Práctica: Trabajando con Volúmenes en Docker

En esta práctica, aprenderemos a trabajar con volúmenes en Docker utilizando la imagen de Apache (tag 2.4) y Visual Studio Code. formato Markdown.

## Paso 1: Descargar la imagen 'httpd' y comprobar su existencia

Para comenzar, descargaremos la imagen de Apache (tag 2.4) y comprobaremos que está disponible en nuestro sistema.

```bash
docker pull httpd:2.4
docker images
```

Verifica que la imagen 'httpd:2.4' está en la lista de imágenes descargadas.

## Paso 2: Crear un contenedor con el nombre 'dam_web1'

Ahora, crearemos un contenedor con el nombre 'dam_web1' utilizando la imagen de Apache que descargamos en el paso anterior.

```bash
docker run --name dam_web1 -di httpd:2.4
```


