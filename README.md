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

# Configuració de la cloud
(https://github.com/AdriFroste/Owncloud/blob/main/.md)
