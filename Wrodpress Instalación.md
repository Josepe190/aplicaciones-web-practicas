# Instalación de Wordpress

Esto solo lo puedes hacer después de instalar mariadb


1.Az sudo mariadb después de poner eso te tiene que salir algo parecido:


2.Ahora escribe:
CREATE DATABASE wordpress CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'wp_user'@'localhost' IDENTIFIED BY 'josepe190';
GRANT ALL PRIVILEGES ON wordpress.* TO 'wp_user'@'localhost';
FLUSH PRIVILEGES;
EXIT;


josepe190 esto es la contraseña lo digo para que la puedas cambiar


3.Luego escribe mariadb -u wp_user -p wordpress y luego tu contraseña de antes y despues escribe SHOW TABLES; y cuando acabe escribe EXIT;


4.Luego escribe:cd /tmp para acceder a este directorio y luego escribe:wget https://wordpress.org


5.Ejecuta el editor para modificar los puertos:

sudo nano /etc/apache2/ports.conf

Dentro del archivo, baja con las flechas del teclado y añade la línea Listen 8080 justo debajo de donde pone Listen 80.

captura 1

luego guarda y sal al directorio principal

luego escribe sudo mariadb

luego escribe uno por uno:CREATE DATABASE wordpress CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'wp_user'@'localhost' IDENTIFIED BY 'CAMBIA_ESTA_CLAVE';
GRANT ALL PRIVILEGES ON wordpress.* TO 'wp_user'@'localhost';
FLUSH PRIVILEGES;
EXIT;

Recuerda cambia la clave

luego pon esto:mariadb -u wp_user -p wordpress y te pedira la clave de antes ponla y escribe:SHOW TABLES; y EXIT;


y te saldrá algo asi

captura 2
