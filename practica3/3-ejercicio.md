## Esquema para el ejercicio
![Imagen](imagenes/esquema-ejercicio3.PNG)

### Crear red net-wp
```docker network create net-wp```

### Para que persista la información es necesario conocer en dónde mysql almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/)
En el esquema del ejercicio la carpeta contenedor (a) es ```/var/lib/mysql```
Ruta carpeta host: .../ejercicio3/db

### ¿Qué contiene la carpeta db del host?

Inicialmente, la carpeta db del host está vacía. Una vez que el contenedor de MySQL esté en ejecución y almacene datos, esta carpeta contendrá los archivos de datos de MySQL, como las tablas y bases de datos.

### Crear un contenedor con la imagen mysql:8  en la red net-wp, configurar las variables de entorno: MYSQL_ROOT_PASSWORD, MYSQL_DATABASE, MYSQL_USER y MYSQL_PASSWORD
```docker run --name mysql-container --network net-wp -e MYSQL_ROOT_PASSWORD=P@ssw0rd -e MYSQL_DATABASE=mi_base_de_datos -e MYSQL_USER=user -e MYSQL_PASSWORD=P@ssw0rd -v /ruta/absoluta/a/tu/db:/var/lib/mysql -d mysql:8```

### ¿Qué observa en la carpeta db que se encontraba inicialmente vacía?

Después de iniciar el contenedor MySQL, la carpeta db que estaba inicialmente vacía ahora contiene los archivos y directorios de datos de MySQL. Estos archivos incluyen información sobre las bases de datos, tablas, índices y otros metadatos necesarios para el funcionamiento de MySQL. Podrás ver archivos como ibdata1, ib_logfile0, ib_logfile1, y carpetas con los nombres de las bases de datos creadas.

### Para que persista la información es necesario conocer en dónde wordpress almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/)
En el esquema del ejercicio la carpeta contenedor (b) es ```/var/www/html```
Ruta carpeta host: .../ejercicio3/www

### Crear un contenedor con la imagen wordpress en la red net-wp, configurar las variables de entorno WORDPRESS_DB_HOST, WORDPRESS_DB_USER, WORDPRESS_DB_PASSWORD y WORDPRESS_DB_NAME (los valores de estas variables corresponden a los del contenedor creado previamente)
```
docker run --name wordpress-container --network net-wp \
  -e WORDPRESS_DB_HOST=mysql-container \
  -e WORDPRESS_DB_USER=user \
  -e WORDPRESS_DB_PASSWORD=P@ssw0rd \
  -e WORDPRESS_DB_NAME=mi_base_de_datos \
  -v /Users/LabP3E004/Documents/ejercicio3/www:/var/www/html \
  -p 8080:80 \
  -d wordpress:latest
```

### Personalizar la apariencia de wordpress y agregar una entrada

### Eliminar el contenedor y crearlo nuevamente, ¿qué ha sucedido?


Cuando eliminas el contenedor de WordPress y lo creas nuevamente utilizando el mismo volumen para /var/www/html, todas las personalizaciones de la apariencia y las entradas que agregaste previamente se conservan. 



