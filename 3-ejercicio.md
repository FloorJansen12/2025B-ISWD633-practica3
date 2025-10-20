## Esquema para el ejercicio
![Imagen](esquema-ejercicio3.PNG)

### Crear red net-wp

```
docker network create net-wp
```

# COMPLETAR CON EL COMANDO COMANDO

### Para que persista la información es necesario conocer en dónde mysql almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/
En el esquema del ejercicio carpeta del contenedor (a) es /var/lib/mysql

Ruta carpeta host: .../ejercicio3/db

### ¿Qué contiene la carpeta db del host?

- La carpeta se encuentra vacía.

### Crear un contenedor con la imagen mysql:8  en la red net-wp, configurar las variables de entorno: MYSQL_ROOT_PASSWORD, MYSQL_DATABASE, MYSQL_USER y MYSQL_PASSWORD

```
docker run -d --name mysql --network net-wp -e MYSQL_ROOT_PASSWORD=bernibd -e MYSQL_DATABASE=bernibd -e MYSQL_USER=berni -e MYSQL_PASSWORD=bernibd -v "C:\Users\jorgi\Documents\Construccion\ejercicio3\db":/var/lib/mysql mysql:8
```

# COMPLETAR CON EL COMANDO

### ¿Qué observa en la carpeta db que se encontraba inicialmente vacía?

- Se crearon varios archivos de MySql.

# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### Para que persista la información es necesario conocer en dónde wordpress almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/
En el esquema del ejercicio la carpeta del contenedor (b) es /var/www/html

Ruta carpeta host: .../ejercicio3/www

### Crear un contenedor con la imagen wordpress en la red net-wp, configurar las variables de entorno WORDPRESS_DB_HOST, WORDPRESS_DB_USER, WORDPRESS_DB_PASSWORD y WORDPRESS_DB_NAME (los valores de estas variables corresponden a los del contenedor creado previamente)

```
docker run -d --name wordpress --network net-wp -v "C:\Users\jorgi\Documents\Construccion\ejercicio3\www":/var/www/html/ -p 9500:80 -e WORDPRESS_DB_HOST=mysql -e WORDPRESS_DB_USER=berni -e WORDPRESS_DB_PASSWORD=bernibd -e WORDPRESS_DB_NAME=bernibd wordpress
```
# COMPLETAR CON EL COMANDO

### Personalizar la apariencia de wordpress y agregar una entrada

<img width="1919" height="878" alt="image" src="https://github.com/user-attachments/assets/55a339f0-80b6-4260-a3f6-7b86ba296b96" />

### Eliminar el contenedor y crearlo nuevamente, ¿qué ha sucedido?

- Se creó nuevamente el contenedor, pero con la entrada del anterior contenedor.

# COMPLETAR CON LA RESPUESTA A LA PREGUNTA 

