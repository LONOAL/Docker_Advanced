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

## Paso 3: Acceder desde el navegador

Para poder acceder desde el navegador de tu equipo al servidor Apache en 'dam_web1', debes abrir un puerto. Los contenedores de Docker están aislados por defecto, por lo que necesitas hacerlo explícitamente.

Puedes utilizar la opción `-p` para publicar un puerto del contenedor en el puerto de tu sistema host. Por ejemplo, para exponer el puerto 80 del contenedor al puerto 8000 de tu sistema host:

```bash
docker run --name dam_web1 -di -p 8000:80 httpd:2.4
```

Ahora podrás acceder desde tu navegador a [http://localhost:8000](http://localhost:8000) y ver la página por defecto de Apache.

## Paso 4: Utilizar Bind Mount para el directorio 'htdocs'

Utilizaremos Bind Mount para montar el directorio 'htdocs' del contenedor en un directorio de tu elección en tu sistema host. Esto facilitará la edición de archivos HTML y su persistencia.

```bash
docker run --name dam_web1 -di -p 8000:80 -v $PWD/htdocs:/usr/local/apache2/htdocs/ httpd:2.4
```


