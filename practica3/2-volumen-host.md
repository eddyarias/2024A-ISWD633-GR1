# VOLUMEN TIPO HOST
Un volumen host (o bind mount) es un tipo de volumen donde se monta un directorio o archivo específico del sistema de archivos del host en un contenedor.

```
docker run -d --name <nombre contenedor> -v <ruta carpeta host>:<ruta carpeta contenedor> <imagen> 
```

### Crear un volumen tipo host con la imagen nginx:alpine, para la ruta carpeta host: directorio en donde se encuentra la carpeta html en tu computador y para la ruta carpeta contenedor: /usr/share/nginx/html esta ruta se obtiene al revisar la se obtiene desde la documentación
![Volúmenes](imagenes/volumen-host.PNG)
# COMPLETAR CON EL COMANDO

### ¿Qué sucede al ingresar al servidor de nginx?

Al ingresar al servidor de Nginx en http://localhost, verás el contenido del directorio /usr/share/nginx/html del contenedor, que estará sincronizado con el directorio especificado en tu host (/Users/LabP3E004/Documents/Docker). Esto significa que cualquier archivo que esté en esa carpeta de tu host será servido por el servidor Nginx.

### ¿Qué pasa con el archivo index.html del contenedor?

El archivo index.html original del contenedor de Nginx será reemplazado por el archivo index.html presente en el directorio montado desde tu host. Si no hay un index.html en el directorio de tu host, entonces cuando intentes acceder a http://localhost, verás un error 403 Forbidden o un listado del directorio si la configuración de Nginx lo permite.

### Ir a https://html5up.net/ y descargar un template gratuito, descomprirlo dentro de nginx/html
### ¿Qué sucede al ingresar al servidor de nginx?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### Eliminar el contenedor
# COMPLETAR CON EL COMANDO

### ¿Qué sucede al crear nuevamente el mismo contenedor con volumen de tipo host a los directorios definidos anteriormente?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### ¿Qué hace el comando pwd?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA
Si quieres incluir el comando pwd dentro de un comando de Docker, lo puedes hacer de diferentes maneras dependiendo del shell que estés utilizando.


### Volumen tipo host usando PWD y PowerShell
```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v ${PWD}/<ruta relativa>:<ruta absoluta> <nombre imagen>:<tag> 
```

### Volumen tipo host usando PWD (Git Bash)

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v $(pwd -W)/html:/usr/share/nginx/html <nombre imagen>:<tag> 
```

### Volumen tipo host usando PWD (en Linux)

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v $(pwd)/html:/usr/share/nginx/html <nombre imagen>:<tag> 
```

