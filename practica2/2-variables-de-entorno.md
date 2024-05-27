# Variables de Entorno
### ¿Qué son las variables de entorno

Las variables de entorno son variables definidas en el entorno del sistema operativo que pueden afectar el comportamiento de los procesos que se ejecutan en ese entorno. Son una forma de pasar información al software y scripts sobre el entorno en el que se están ejecutando.

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

```docker run -d --name nginx-container -e username=myuser -e role=admin nginx:alpine```

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR

![image](https://github.com/eddyarias/2024A-ISWD633-GR1/assets/94008713/c828515e-63a5-45a3-ae4f-9195d6736ece)

### Crear un contenedor con mysql:8 , mapear todos los puertos

```docker run -d --name mysql-container -P mysql:8```


### ¿El contenedor se está ejecutando?
```docker ps -a```

### Identificar el problema

```docker rm mysql-container```

Si el contenedor de MySQL no se está ejecutando, puede haber varias razones. Aquí hay algunos pasos que puedes seguir para identificar el problema:

Verificar el estado del contenedor: Utiliza el comando docker ps -a para verificar si el contenedor aparece en la lista y si está detenido o en ejecución.

Revisar los registros del contenedor: Los registros pueden contener información sobre por qué el contenedor no se está ejecutando correctamente. Puedes ver los registros de un contenedor específico utilizando el comando docker logs <nombre_contenedor>.

Verificar errores de creación del contenedor: Si el contenedor no se creó correctamente, puede haber errores en la salida del comando docker run. Revisa la salida del comando para detectar posibles errores.



### Eliminar el contenedor creado con mysql:8 
```docker rm mysql-container```


### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

Previo a esto es necesario crear el archivo y colocar las variables en un archivo, **.env** se ha convertido en una convención estándar, pero también es posible usar cualquier extensión como **.txt**.
```
docker run -d --name <nombre contenedor> --env-file=<nombreArchivo>.<extensión> <nombre imagen>
```
**Considerar**
Es necesario especificar la ruta absoluta del archivo si este se encuentra en una ubicación diferente a la que estás ejecutando el comando docker run.

### Crear un contenedor con mysql:8 , mapear todos los puertos y configurar las variables de entorno mediante un archivo
```docker run -d --name mysql-container1 --env-file=C:\Users\eddya\OneDrive\Documentos\holi.txt -P mysql:8```

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR 
![image](https://github.com/eddyarias/2024A-ISWD633-GR1/assets/94008713/87ee2318-7003-460b-b066-28982c90c0d0)


### ¿Qué bases de datos existen en el contenedor creado?

mysql: [Warning] Using a password on the command line interface can be insecure.
Database
information_schema
mydatabase
mysql
performance_schema
sys
