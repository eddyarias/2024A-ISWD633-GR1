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

Al ingresar nuevamente al servidor de Nginx en http://localhost, verás el contenido del template que descargaste y descomprimiste en el directorio /Users/LabP3E004/Documents/Docker. El servidor Nginx servirá estos archivos, por lo que verás la página del template en tu navegador.

### Eliminar el contenedor

```
docker rm -f primerContenedor
```

### ¿Qué sucede al crear nuevamente el mismo contenedor con volumen de tipo host a los directorios definidos anteriormente?

Al crear nuevamente el mismo contenedor con el volumen de tipo host a los directorios definidos anteriormente, el contenedor montará el mismo directorio del host (/Users/LabP3E004/Documents/Docker) en la misma ruta del contenedor (/usr/share/nginx/html). Por lo tanto, verás el mismo contenido que hayas colocado en ese directorio del host cuando accedas al servidor Nginx. Esto significa que cualquier cambio realizado en los archivos del directorio del host se reflejará inmediatamente en el servidor Nginx, ya que los archivos están compartidos entre el host y el contenedor.


### ¿Qué hace el comando pwd?

El comando pwd (print working directory) muestra la ruta completa del directorio de trabajo actual en la línea de comandos. Es útil para saber en qué directorio te encuentras actualmente al trabajar en la terminal. Por ejemplo, si estás en el directorio /home/user/projects, al ejecutar pwd, obtendrás /home/user/projects como salida.

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

