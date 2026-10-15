# Memoria de Práctica: Instalación de MariaDB y PHP en Ubuntu 24.04 (LAMP)

**Curso:** Sistemas Microinformáticos y Redes (SMR)  
**Módulo:** Aplicaciones Web  
**Alumno:** [Tu Nombre y Apellidos]  
**Fecha:** [Fecha de hoy]  

---

## Apartado 1. Preparación del sistema

En este primer paso actualizamos el listado de paquetes de los repositorios oficiales de Ubuntu para asegurar la descarga de las versiones estables más recientes. Posteriormente, verificamos que el servidor web Apache instalado en la práctica anterior se encuentra activo y respondiendo correctamente.

```bash
sudo apt update
systemctl is-active apache2
```

### Salida del terminal:
```text
active
```

### Captura de pantalla:
`![Estado operativo de Apache](img/apartado1_apache_active.png)`

---

## Apartado 2. Instalación de MariaDB

Procedemos a realizar la instalación del motor y sistema de gestión de bases de datos MariaDB. Una vez finalizada, comprobamos la versión exacta que se ha desplegado en el servidor.

```bash
sudo apt install mariadb-server -y
mariadb --version
```

### Salida del terminal:
```text
mariadb Ver 15.1 Distrib 10.11.14-MariaDB, for debian-linux-gnu (x86_64)
```

### Captura de pantalla:
`![Versión de MariaDB](img/apartado2_version_mariadb.png)`

### ❓ Pregunta de reflexión:
**¿Qué diferencia hay entre el paquete `mariadb-server` y el paquete `mariadb-client`? ¿Cuál de los dos has instalado?**  
* **mariadb-server:** Es el motor de la base de datos central. Se ejecuta como un servicio en segundo plano (demonio) y se encarga de almacenar físicamente la información, proteger los accesos y procesar las consultas de manera interna.
* **mariadb-client:** Es el conjunto de herramientas de software (como la consola de comandos terminal) que permite a los usuarios o a aplicaciones locales/remotas conectarse e interactuar con el servidor enviándole instrucciones SQL.
* **Paquete instalado:** He ejecutado la instalación de `mariadb-server`. No obstante, el gestor de paquetes instala de manera automática el cliente como una dependencia necesaria para que podamos administrarlo de forma nativa desde el terminal.

---

## Apartado 3. Comprobación del funcionamiento

### 3.1. Estado del servicio
Verificamos el estado detallado del proceso dentro del sistema operativo y consultamos si está configurado para arrancar de forma automática cada vez que se encienda la máquina virtual.

```bash
sudo systemctl status mariadb
systemctl is-enabled mariadb
```

### 3.2. Entrar en la base de datos
Realizamos una prueba de acceso administrativo directo a la shell nativa de MariaDB utilizando privilegios elevados de sudo. Una vez dentro, salimos del monitor para regresar a la terminal de Linux.

```bash
sudo mariadb
```
*(Dentro del monitor de MariaDB)*
```sql
exit
```

### Salida del terminal:
```text
Welcome to the MariaDB monitor. Commands end with ; or \g.
Server version: 10.11.14-MariaDB-0ubuntu0.24.04.1 Ubuntu 24.04

MariaDB [(none)]>
```

### Captura de pantalla:
`![Comprobaciones de MariaDB](img/apartado3_estado_y_consola.png)`

### ❓ Pregunta de reflexión:
**¿Qué diferencia hay entre `active (running)` y `enabled`? ¿Qué pasaría con la web de WordPress si MariaDB estuviera `active` pero no `enabled` y se reiniciara el servidor?**  
* **active (running):** Significa que el programa está cargado en la memoria RAM y funcionando en este preciso instante.
* **enabled:** Significa que el servicio está configurado en el gestor de arranque del sistema (`systemd`) para iniciarse automáticamente durante el encendido de la máquina.
* **Comportamiento si no estuviera `enabled`:** Si el servidor se reinicia, la base de datos permanecerá totalmente apagada. Al intentar acceder a la página web de WordPress, se romperá la carga del sitio y el navegador mostrará un mensaje de error crítico indicando que no se ha podido establecer una conexión con la base de datos, obligando a un administrador a iniciarla manualmente en la terminal.

---

## Apartado 4. Comandos principales

A continuación se detalla la función técnica de los comandos de administración nativos de `systemctl` utilizados para la gestión diaria del servicio:

| Comando | Función con mis propias palabras |
| :--- | :--- |
| `sudo systemctl start mariadb` | Arranca y pone en funcionamiento el motor de la base de datos si se encontraba apagado. |
| `sudo systemctl stop mariadb` | Detiene y apaga de forma segura el servicio, liberando los recursos de memoria. |
| `sudo systemctl restart mariadb` | Apaga y vuelve a encender de manera inmediata el servicio. Se emplea para aplicar nuevas configuraciones. |
| `sudo systemctl status mariadb` | Muestra el estado operativo, registros de eventos en directo y si se han producido fallos. |
| `sudo systemctl enable mariadb` | Registra el servicio para que se active automáticamente durante la secuencia de arranque del equipo. |

---

## Apartado 5. ¿Qué pasa si MariaDB está parado?

Simulamos un escenario real de caída del servicio de almacenamiento deteniendo el motor de manera intencionada, analizando el comportamiento de error que arroja el cliente interactivo y procediendo posteriormente con su restauración.

```bash
sudo systemctl stop mariadb
systemctl is-active mariadb
sudo mariadb
```

Volvemos a levantar el servicio para restablecer el entorno de trabajo:

```bash
sudo systemctl start mariadb
systemctl is-active mariadb
```

### Salida del terminal (con el servicio detenido):
```text
inactive
ERROR 2002 (HY000): Can't connect to local server through socket '/run/mysqld/mysqld.sock' (2)
```

### Captura de pantalla:
`![Error provocado y posterior recuperación](img/apartado5_error_socket.png)`

### ❓ Pregunta de reflexión:
**Si WordPress no pudiera conectar con la base de datos, ¿qué dos comandos de este apartado usarías para saber si el problema es que MariaDB está parado?**  
Utilizaría los siguientes comandos de diagnóstico:
1. `systemctl is-active mariadb` (o `sudo systemctl status mariadb`), para verificar al instante si el proceso de la base de datos está en ejecución o caído.
2. `sudo mariadb`, para tratar de forzar una conexión local a través del socket y comprobar si el demonio rechaza la comunicación o está completamente apagado.

---

## Apartado 6. Instalación de PHP

Procedemos a desplegar el intérprete de PHP en su versión nativa junto a las extensiones modulares requeridas por WordPress para tareas de compresión, gestión de strings multi-idioma, tratamiento de imágenes y conectividad de red.

```bash
sudo apt install php libapache2-mod-php php-mysql php-curl php-gd php-mbstring php-xml php-zip php-intl -y
php -v
sudo systemctl restart apache2
php -m | grep -i mysql
```

Para asegurar que Apache interpreta el lenguaje PHP correctamente de cara al servidor web, generamos un script temporal dinámico:

```bash
echo '<?php phpinfo();' | sudo tee /var/www/html/info.php
```

Tras validar la visualización de la interfaz en el navegador web accediendo a la URL correspondiente, eliminamos de forma obligatoria el archivo del espacio público del servidor:

```bash
sudo rm /var/www/html/info.php
ls /var/www/html
```

### Salida del terminal:
```text
PHP 8.3.x ...
mysqli
mysqlnd
pdo_mysql
```

### Captura de pantalla:
`![Verificación técnica de PHP y mod_php](img/apartado6_phpinfo.png)`

### ❓ Pregunta de reflexión:
**¿Por qué es peligroso dejar `info.php` en un servidor real? ¿Para qué sirve el paquete `php-mysql`?**  
* **Peligro de `info.php`:** Este script renderiza públicamente información muy sensible del servidor, tales como versiones detalladas de compilación, rutas del sistema de archivos, configuraciones de variables de entorno, extensiones activas y directivas de seguridad vigentes. Un usuario malintencionado podría utilizar estos datos estratégicos para planificar ataques dirigidos contra vulnerabilidades conocidas del sistema.
* **Utilidad de `php-mysql`:** Es el conector indispensable que actúa como traductor de software. Proporciona a las funciones de PHP las APIs necesarias (`mysqli` y `pdo_mysql`) para interactuar, enviar consultas e intercambiar flujos de datos estructurados con el servidor MariaDB.

---

## Apartado 7. Comprobación final

Llevamos a cabo un test final conjunto sobre los servicios esenciales del servidor LAMP para verificar que el entorno se encuentra completamente optimizado y listo para la futura instalación del CMS.

```bash
systemctl is-active apache2 mariadb
php -v
```

### Resumen del estado del LAMP:

| Pieza del LAMP | Programa | Estado |
| :--- | :--- | :--- |
| **Linux** | Ubuntu 24.04 | Instalado |
| **Apache** | Apache2 | Funcionando |
| **MariaDB** | MariaDB 10.11 | Funcionando |
| **PHP** | PHP 8.3 | Funcionando y preparado para MariaDB |

### Captura de pantalla:
`![Estado final del entorno LAMP](img/apartado7_lamp_comprobacion.png)`

---

## Conclusiones y problemas encontrados

