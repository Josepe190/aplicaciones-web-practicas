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
