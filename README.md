# Owncloud
## Primer s'ha de descarregar el .zip de Owncloud.
https://download.owncloud.com/server/stable/owncloud-complete-20240724.zip
## Primer s'han de descarregar els requisits previs mitjançant el següent comando en la terminal:
sudo apt install software-properties-common -y
## Instalar les eines que es necessiten per treballar amb els arxius de paquets personals (PPA).
LC_ALL=C.UTF-8 sudo add-apt-repository ppa:ondrej/php -y
## Actualizar els repositoris
sudo apt update
## Instal·lar les llibreries de *PHP de la versió 7.4 amb els tres següents comandos en la terminal:
sudo apt install php7.4 -y

sudo apt install -y php libapache2-mod-php7.4

sudo apt install -y php7.4-fpm php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-gd php7.4-xml php7.4-intl php7.4-mysql php7.4-cli php7.4-ldap php7.4-zip php7.4-curl

## Ara toca observar i triar la versió de PHP
sudo update-alternatives --config php
## Es necessita activar mòduls de apache2 (Servidor web) mitjançant els dos següents comandos en el terminal
sudo a2enmod proxy_fcgi setenvif
sudo a2enconf php7.4-fpm
## S'ha de reiniciar el apache2
sudo service apache2 restart
## Actualizar la maquina
sudo apt update
## Actualizar els programes
sudo apt upgrade
## Instalació de apache2
sudo apt install -y apache2
## Instalar mysql-server (Servidor de base de dades)
sudo apt install -y mysql-server
## Instal·lació de llibreries de php, el llenguatge principal que utilitzen les aplicacions.
sudo apt install -y php libapache2-mod-php

sudo apt install -y php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-mysql php-cli php-ldap php-zip php-curl

## Reiniciar el servidor
sudo systemctl restart apache2
# Accedir a la consola
## Amb el següent comand
sudo mysql
## Crear base de dades
CREATE DATABASE bbdd;
## Crear un usuari i contrasenya
CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
## Donar privilegis
GRANT ALL ON bbdd.* to 'usuario'@'localhost';
## Sortir
exit
## Probar la conexió
mysql -u usuario -p
## Descarregar els fitxers de la aplicació web
sudo cp ~/Baixades/owncloud.zip /var/www/html
## Aneu al directori /var/www/html
cd /var/www/html
## Descomprimir el fitxer descarregat
sudo unzip owncloud.zip
## Copiar els fitxers a la carpeta /var/www/html
sudo cp -R owncloud/. /var/www/html
## Eliminem la carpeta creada quan hem fet l'unzip
sudo rm -rf owncloud/
## Eliminem index.html de l'apache2 amb el següent comand
sudo rm -rf /var/www/html/index.html
## Aplicar els permissos següents
cd /var/www/html
sudo chmod -R 775 .
sudo chown -R usuario:www-data .
Nómes queda anar a la web http://localhost/ 
La informació necesaria és la següent
usuari: usuario
contrasenya: password
base de dades: bbdd
domini: localhost



