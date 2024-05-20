# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](imagenes/imagen.PNG)


## ¿Cuál es la relación entre una imagen y un contenedor? 
**Creación:** Los contenedores se crean a partir de imágenes. Una imagen actúa como el plano (blueprint) que define qué se incluye en el contenedor.

**Instancia:** Cada contenedor es una instancia separada de una imagen. Puedes tener múltiples contenedores corriendo simultáneamente a partir de la misma imagen.

**Inmutabilidad vs. Mutabilidad:** Mientras que la imagen es inmutable y no cambia, los contenedores son mutables y pueden tener cambios durante su ejecución. Sin embargo, estos cambios no afectan la imagen original.

**Aislamiento:** Los contenedores proporcionan un entorno aislado y replicable basado en la imagen. Esto garantiza que la aplicación se ejecute de manera consistente sin importar dónde se implemente el contenedor.

**Portabilidad:** Las imágenes se pueden transferir entre diferentes entornos (como entre desarrolladores y servidores de producción), y se puede garantizar que los contenedores creados a partir de estas imágenes se comportarán de manera idéntica. 

![Imagen y contenedores](imagenes/imagenYcontenedores.JPG)
## Comandos para imágenes

### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**

C:\Docker>docker pull hello-world
Using default tag: latest
latest: Pulling from library/hello-world
c1ec31eb5944: Pull complete
Digest: sha256:266b191e926f65542fa8daaec01a192c4d292bff79426f47300a046e1bc576fd
Status: Downloaded newer image for hello-world:latest
docker.io/library/hello-world:latest

What's Next?
  View a summary of image vulnerabilities and recommendations → docker scout quickview hello-world


**¿Qué es nginx**
es un servidor web de código abierto que también puede funcionar como un servidor proxy inverso, balanceador de carga, y un caché HTTP. Desarrollado inicialmente por Igor Sysoev y lanzado en 2004, Nginx ha ganado popularidad por su alta performance, estabilidad, y bajo consumo de recursos


Descargar la imagen  **nginx** en la versión **alpine**

C:\Docker>docker pull nginx:alpine
alpine: Pulling from library/nginx
4abcf2066143: Pull complete
fc21a1d387f5: Pull complete
e6ef242c1570: Pull complete
13fcfbc94648: Pull complete
d4bca490e609: Pull complete
5406ed7b06d9: Pull complete
8a3742a9529d: Pull complete
0d0c16747d2c: Pull complete
Digest: sha256:516475cc129da42866742567714ddc681e5eed7b9ee0b9e9c015e464b4221a00
Status: Downloaded newer image for nginx:alpine
docker.io/library/nginx:alpine

What's Next?
  View a summary of image vulnerabilities and recommendations → docker scout quickview nginx:alpine


### Listar imágenes

```
docker images
```

# COLOCAR UNA CAPTURA DE PANTALLA DEL RESULTADO 
![image](https://github.com/eddyarias/2024A-ISWD633-GR1/assets/94008713/6bd46260-a197-46bf-bfb8-c7af0c602644)



**Identificadores**
En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
# COMPLETAR

**¿Con qué algoritmo se está generando el ID de la imagen**
# COMPLETAR

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 
# COMPLETAR

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

