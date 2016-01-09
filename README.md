# Lista de comandos

Configuração inicial do ambiente de desenvolvimento PHP.
Estes comando foram validados na distro Ubuntu 14.04 LTS

#### Instalar NGINX
```sh
sudo apt-get update
sudo apt-get install nginx
```

#### Instalar MySQL Server

```sh
sudo apt-get install mysql-server
```

> comando de segurança para mysql

```sh
sudo mysql_secure_installation
```

#### Instalar sublime text3

```sh
sudo add-apt-repository ppa:webupd8team/sublime-text-3
sudo apt-get update
sudo apt-get install sublime-text-installer
```

#### Instalar php5-fpm

```sh
sudo apt-get install php5-fpm php5-mysql php5-mcrypt
```

> configura php para rodar legal com nginx

```sh
cd /etc/php5/fpm
php.ini
editar a linha abaixo inserindo 0
cgi.fix_pathinfo=0
```

> Caso não instale a versão 5,6

```sh
sudo apt-get install python-software-properties 
sudo add-apt-repository ppa:ondrej/php5-5.6 
sudo apt-get update 
sudo apt-get install -y php5
```

#### Instalar GIT

```sh
sudo apt-get install git
```

#### Intalar composer

```sh
php -r "readfile('https://getcomposer.org/installer');" | php
Com o comando abaixo, basta digitar composer no prompt para acessar
sudo mv composer.phar /usr/bin/composer
```

#### VHOST

```sh
cd /etc
sudo subl hosts
add o novo host EX teste.app
```

#### Exemplo de vhost

Gist do mestre [Fábio Vedovelli](https://github.com/vedovelli) :) THANKS
```sh
https://gist.github.com/vedovelli/a50fdd9c9b745b61407a
```

#### Criando vhost

```sh
 cd /etc/nginx/sites-available
sudo subl teste.app.conf
cd ../sites-enabled
sudo ln -s ../sites-available/teste.app.conf
```