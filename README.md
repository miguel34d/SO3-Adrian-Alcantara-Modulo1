SO3 - Adrián Alcántara - Módulo 1
Alumno: Miguel Ramírez Meli (2025-1367)

============================================
Comandos usados practica 1 (Instalacion del Sistema Operativo)
============================================
(WINDOWS)
time /t
date /t
(LINUX-MINT)
# instala las actualizaciones disponibles para los paquetes
Sudo apt update 
# Instala todas las actualizaciones disponibles automáticamente
sudo apt upgrade -y
(WINDOWS)
time /t
date /t
============================================
Comandos usados practica 2 (Configuración de parametros de red)
============================================

(WINDOWS)
time /t
date /t

(LINUX-MINT)
# Mostrar interfaces de red
ifconfig

# Eliminar y agregar IP manualmente
sudo ip addr del 192.168.100.75/24 dev ens33
sudo ip addr add 192.168.100.102/24 dev ens33

# Mostrar rutas
ip route show

# Agregar gateway
sudo ip route add default via 192.168.100.1 dev ens33

# Editar DNS
sudo nano /etc/resolv.conf

# Renovar DHCP
sudo dhclient -r
sudo dhclient

# Mostrar conexiones de NetworkManager
nmcli con show

# Configuración manual de IP 
nmcli connection modify "Conexión cableada 1" ipv4.method manual ipv4.addresses 192.168.100.131/24 ipv4.gateway 192.168.100.1 ipv4.dns 8.8.8.8 ipv4.ignore-auto-dns yes

# Reiniciar la conexión
sudo nmcli connection down "Conexión cableada 1"
sudo nmcli connection up "Conexión cableada 1"

# Probar conectividad
ping 8.8.8.8
ping 8.8.4.4

# Configuración automática DHCP
nmcli connection modify "Conexión cableada 1" ipv4.method auto
sudo nmcli connection down "Conexión cableada 1"
sudo nmcli connection up "Conexión cableada 1"

# Alternativa: Netplan (para algunas versiones de Linux Mint/Ubuntu)
cd /etc/netplan
ls
sudo nano 01-network-manager-all.yaml
sudo netplan apply
ip route
ping 8.8.8.8
ping 8.8.4.4

============================================
Comandos usados practica 3 (Gestion de Usuario y grupos)
============================================
(WINDOWS)
time /t
date /t

(LINUX-MINT)
# Crear usuario
sudo adduser miguel
groups miguel

# Agregar usuario a sudo
sudo usermod -aG sudo miguel
groups miguel

# Crear grupo
sudo addgroup guest
getent group

# Crear otro usuario
sudo adduser julian
sudo usermod -aG guest julian
groups julian

# Eliminar usuario de grupo
sudo gpasswd -d julian guest
groups julian

# Eliminar usuario y grupo
sudo deluser julian
sudo delgroup guest
getent group

(WINDOWS)
time /t
date /t

============================================
Comandos usados practica 4 (Gestion de Permisos de archivos)
============================================

(WINDOWS)
time /t
date /t

(LINUX-MINT)
# Crear carpeta y archivo
mkdir MATERIA
cd MATERIA/
vi estudiante.txt
cat estudiante.txt
ls -l

# Cambiar permisos del archivo
chmod 0 estudiante.txt
ls -l
chmod u+rwx estudiante.txt
ls -l
chmod g+rwx estudiante.txt
ls -l

# Crear segunda carpeta y explorar directorios
cd ..
mkdir MATERIA2
cd MATERIA
clear
ls 
cd - 
cd MATERIA
cd ..
cd MATERIA2
ls
cd ..

# Copiar archivo a otra carpeta
cd MATERIA
cp estudiante.txt /home/miguel-20251367/Escritorio/MATERIA2
ls
cd ..
cd MATERIA2
ls 
ls -l
cd ..

# Eliminar carpetas
rm -r MATERIA
ls
rm -r MATERIA2
ls
(WINDOWS)
time /t
date /t




