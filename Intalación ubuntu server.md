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

![Revisa los espacios tener muy encuenta]()


21.  1. Actualiza el índice de paquetes locales
sudo apt update

2. Instala el servidor web Apache2
sudo apt install apache2 -y

22.sudo systemctl status apache2

23.sudo systemctl start apache2

24.ports.conf	Es el archivo de Apache donde se definen las direcciones IP y los puertos de escucha del servidor web (por ejemplo, el puerto 80 para HTTP o el 443 para HTTPS).

25.sites-available/	Es la carpeta que almacena los archivos de configuración de todos los sitios web (hosts virtuales) que tienes creados y listos para usar. Los archivos guardados aquí no están activos de forma automática ni los lee el servidor directamente.

26.sites-enabled/	Es la carpeta que contiene los sitios web actualmente activos. No guarda archivos reales, sino enlaces simbólicos (accesos directos) que apuntan a los archivos correspondientes dentro de sites-available/.

27
