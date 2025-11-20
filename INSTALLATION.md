### En esta parte de este repositorio es para hacer la explicacion de la instalación
## 1. Instalacion de LAMP stack a Ubuntu 24.04

Antes de empezar con todo debemos de abrir este punto con nombre: "Instalacion de LAMP stack a Ubuntu 24.04"

 # 1. Actualitzamos el sistema
```bash
sudo apt update && sudo apt upgrade -y
```
# 2. Instalamos Apache
```bash
sudo apt install apache2 -y
```

**Activamos i iniciamos el servidor:**
```bash
sudo systemctl enable apache2
sudo systemctl start apache2
```
**Verificamos el estado:**
```bash
sudo systemctl status apache2
```
Visite `http://localhost` para ver la pagina Apache predeterminada.

### 3. **Instalar MySQL**

Ubuntu 24.04 ya incluye el paquete `mysql-server` en los repositorios oficiales (versión 8.0 o superior):

```bash
sudo apt install mysql-server mysql-client -y
```

**Iniciar y habilitar el servicio:**
```bash
Sudo systemctl habilitar mysql
Sudo systemctl iniciar mysql
```
**Configurar MySQL:**

### Acceso a la consola MySQL
```bash
Sudo mysql
```
### Creación de base de datos
```sal
CREAR BASE DE DATOS bbdd;
```

#### Creación del usuario local
```sal
CREAR USUARIO 'user'@'localhost' IDENTIFICADO CON mysql_native_password POR 'password';
OTORGAR TODOS LOS PRIVILEGIOS EN BBDD. * A 'usero'@'localhost';
PRIVILEGIOS DE RAFAGA;
SALIDA;

> **Nota:** Este usuario solo puede conectarse desde el servidor local (`localhost`), que es suficiente si la aplicacion web y la base de datos están en el mismo servidor.


## 4. **Instalar PHP y extensiones comunes** 

Ubuntu 24.04 incluye PHP 8.3 en repositorios estándar

```bash
sudo apt install php libapache2-mod-php php-mysql php-gd php-mbstring php-xml php-zip php-json php-cli-y
```

**Reinicio Apache para cargar PHP:**
```bash
Sudo systemctl reinicio apache2
```

**Verificar la version de PHP:**
```bash
php -v
```

**Crear un archivo de prueba:**
```bash
"echo<? php phpinfo(); ? >" | sudo tee /var/www/html/info.php
```

Visite `http://localhost/info.php` para ver la informacion de PHP.

> **Medida de seguridad:** Una vez que haya comprobado que funciona, elimine el archivo:
> ```bash
> sudo rm /var/www/html/info.php
> ```

### Verificación final

La pila LAMP ahora deberia estar operativa con:
- **Apache** que sirve paginas web.
- **MySQL** listo para almacenar datos.
- **PHP** scripts de procesamiento.

# Configuración VirtualHost con Apache2
## Introducción 

Un servidor web como Apache2 le permite alojar varios sitios web de forma independiente en la misma máquina. Esta funcionalidad se logra a traves de **VirtualHosts** (hosts virtuales). Cada VirtualHost define un sitio web único con su propio nombre de dominio, directorio raíz y configuración especifica.
