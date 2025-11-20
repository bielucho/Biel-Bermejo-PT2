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
Visite `http://localhost` para ver la p\Uffffffffna Apache predeterminada.

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
