# Instalación de Wordpress

Esto solo lo puedes hacer después de instalar mariadb


1.Ejecuta el editor para modificar los puertos:

sudo nano /etc/apache2/ports.conf

Dentro del archivo, baja con las flechas del teclado y añade la línea Listen 8080 justo debajo de donde pone Listen 80.

![Captura 1Wordpress](Captura%201Wordpress.png)

luego guarda y sal al directorio principal



Az sudo mariadb después de poner eso te tiene que salir algo parecido:


2.Ahora escribe:
CREATE DATABASE wordpress CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'wp_user'@'localhost' IDENTIFIED BY 'josepe190';
GRANT ALL PRIVILEGES ON wordpress.* TO 'wp_user'@'localhost';
FLUSH PRIVILEGES;
EXIT;


josepe190 esto es la contraseña lo digo para que la puedas cambiar


3.Luego escribe mariadb -u wp_user -p wordpress y luego tu contraseña de antes y despues escribe SHOW TABLES; y cuando acabe escribe EXIT;

![Captura 2Wordpress](Captura%202Wordpress.png)


4.Luego escribe:cd /tmp para acceder a este directorio y luego escribe:wget https://wordpress.org

