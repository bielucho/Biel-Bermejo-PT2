### En esta parte de este repositorio es para hacer la explicacion de la instalación
## 1. Instal·lació de LAMP stack a Ubuntu 24.04 

 # 1. Actualitza el sistema
```bash
sudo apt update && sudo apt upgrade -y
```
# 2. Instal·la Apache
```bash
sudo apt install apache2 -y
```

**Activa i inicia el servei:**
```bash
sudo systemctl enable apache2
sudo systemctl start apache2
```
**Verifica l’estat:**
```bash
sudo systemctl status apache2
```
