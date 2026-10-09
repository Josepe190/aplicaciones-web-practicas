1. Instalar VirtualBox

2. Istalar iso ubuntu Srever

3. Abrir Virtual Vox

4. Configurar la maquina virtual

5. Arreglar el error

6. ![Error del VirtualBox](Error%20VirtualBox.png)

7. Al final hemos tenido que desinstalar el BirtualBox y luego volver a instalar el BirtualBox a su ultima versión para arreglar el error

8. Después de la instalación de la maquina elegimos el idioma del teclado y del sistema

9. Elegimos el tipo de instalación de ubuntu server el minimized no

10. La proxy se deja en blanco

11. para el almacenamiento elegimos nustro disco duro completo

12. Ahora pon el nombre del servidor y luego tu usuario y contraseña (Recomendado apuntar en un papel)

13. y para terminar la instalación marca la casilla Install OpenSSH server

14. si por alguna razón no la as marcado o no te sale por alguna extraña razon escribe en la terminal(sudo apt update && sudo apt install
openssh-server)todo junto

15. no istales nada cada sevicio lo intalaremos nosotros mismos para saber que hace cada uno en detalle

16. luego espera a que termine y dale a reboot now y listo la instalación está terminada

17. ahora solo queda iniciar sesión con nuestro usuario y contraseña.

18. es un protocolo de red que permite acceder y administrar un ordenador o servidor de forma remota y segura a través de una red.

19. luego para configurar el SSH hacemos cd /etc/netplan luego haz ls y luego sudo nano el numero del archivo y pulsa el icono de las dos flechas (tabulador)

20. es un servidor web de código abierto, gratuito y multiplataforma. Su función principal es procesar las peticiones de los usuarios y entregarles las páginas o archivos de un sitio web a través de internet.

![Revisa los espacios tener muy encuenta](Sense%20títol.png)

Revisar los espacios tener muy encuenta

21.  1. Actualiza el índice de paquetes locales
sudo apt update

2. Instala el servidor web Apache2
sudo apt install apache2 -y

22.sudo systemctl status apache2

23.sudo systemctl start apache2

24.ports.conf	Es el archivo de Apache donde se definen las direcciones IP y los puertos de escucha del servidor web (por ejemplo, el puerto 80 para HTTP o el 443 para HTTPS).

25.sites-available/	Es la carpeta que almacena los archivos de configuración de todos los sitios web (hosts virtuales) que tienes creados y listos para usar. Los archivos guardados aquí no están activos de forma automática ni los lee el servidor directamente.

26.sites-enabled/	Es la carpeta que contiene los sitios web actualmente activos. No guarda archivos reales, sino enlaces simbólicos (accesos directos) que apuntan a los archivos correspondientes dentro de sites-available/.

27.Un Virtual Host permite alojar múltiples páginas web independientes en un mismo servidor. El servidor web decide qué sitio mostrar según la IP o el puerto de la petición.

28.Paso 1 · Crear las carpetas y las páginas
sudo mkdir -p /var/www/smr/web /var/www/smr/intranet
echo "<h1>Bienvenidos a SMR</h1>" | sudo tee /var/www/smr/web/index.html
echo "<h1>Intranet de SMR</h1>" | sudo tee /var/www/smr/intranet/intranet.html

29.Paso 2 · Crear el usuario de la intranet
sudo apt install apache2-utils -y
sudo htpasswd -c /etc/apache2/.htpasswd alumno

30.Paso 3 · Decirle a Apache que escuche en el puerto 9999
sudo nano /etc/apache2/ports.conf
Debajo de la línea Listen 80 añadid una línea nueva:
Listen 80
Listen 9999

31.Paso 4 · Crear el virtualhost
sudo nano /etc/apache2/sites-available/smr.conf
Llegados a este punto tenemos dos opciones:
1. Crear dos ficheros de configuración como hemos hecho habitualmente en clase (eso significará
tener que habilitar ambos sitios) o
2. En un único fichero de configuración crear dos VirtualHost.
Puedes realizarlo de la manera que consideres (o incluso de las dos, y documentarlo, lo que aumentará tu
destreza y te ayudará a estudiar).
A continuación un ejemplo de cómo realizarlo según la opción 2:

• ServerName: el nombre de la web (igual en los dos bloques).
• DocumentRoot: la carpeta donde están las páginas de cada web.
• DirectoryIndex: la página principal de la intranet, ya que no es index.html.
• El bloque Directory es lo que pide usuario y contraseña (ya lo conocéis de la práctica anterior).


![Revisa los espacios tener muy encuenta](para%20github.png)
