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
# COMPLETAR

**¿Qué es nginx**
# COMPLETAR 

Descargar la imagen  **nginx** en la versión **alpine**
# COMPLETAR

### Listar imágenes

```
docker images
```

# COLOCAR UNA CAPTURA DE PANTALLA DEL RESULTADO 

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

