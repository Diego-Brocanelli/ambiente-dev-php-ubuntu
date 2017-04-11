# Configurações para ambiente de desenvolvimento PHP no Ubuntu

> Estes comandos foram validados na distro Ubuntu 14.04 LTS

# Servidor

#### Instalar o [NGINX](https://www.nginx.com/)
```sh
sudo apt-get update
sudo apt-get install nginx
```

> Exemplo de configuração de VHOST

```sh
cd /etc
sudo subl hosts
add o novo host EX teste.app
```

Gist do mestre [Fábio Vedovelli](https://github.com/vedovelli) :) THANKS

```sh
https://gist.github.com/vedovelli/a50fdd9c9b745b61407a
```

> Criando vhost

```sh
cd /etc/nginx/sites-available
sudo subl teste.app.conf
cd ../sites-enabled
sudo ln -s ../sites-available/teste.app.conf
```

#### Instalar o [APACHE](https://www.apache.org/)

```sh
sudo apt-get update
sudo apt-get install apache2
```

> Não necessariamente deve ser instado os dois, escolha um para utilizar.

# Banco de dados

#### Instalar o [MySQL Server](https://www.mysql.com/)

```sh
sudo apt-get install mysql-server
```

> Comando de segurança para mysql

```sh
sudo mysql_secure_installation
```

#### Instalar o [PostgreSQL](https://www.postgresql.org/)
```sh
sudo apt-get update
sudo apt-get install postgresql postgresql-contrib
```
> O procedimento de instalação criou um usuário chamado postgres que é associado com o role padrão do Postgres. Para usar o Postgres, podemos fazer login nessa conta.
> Alterne para a conta postgres no seu servidor digitando:

```sh
sudo -i -u postgres
```

> Acessando um prompt Postgres Sem Alternar Contas

```sh
sudo -u postgres psql
```

# PHP

#### Instalando o PHP 5 
```sh
sudo apt-get install php5-fpm php5-mysql php5-mcrypt
```

> Configura php para rodar legal com nginx

```sh
cd /etc/php5/fpm
php.ini
Editar a linha abaixo inserindo 0
cgi.fix_pathinfo=0
```
#### Instalando o PHP 5.6

```sh
sudo apt-get install python-software-properties 
sudo add-apt-repository ppa:ondrej/php5-5.6 
sudo apt-get update 
sudo apt-get install -y php5
```

#### Instalando o PHP 7.1

```sh
sudo add-apt-repository ppa:ondrej/php
sudo apt-get update 
sudo apt-get install php7.1
```

> Instalando as extensões 

```sh
sudo apt-get install php7.1-mysql php7.1-mcrypt
```

> Os procedimentos de instalação listados acima não trabalham com múltiplas versões do PHP, sendo assim caso execute uma das operações a versão atual será sobrescrita.

# Ferramentas

## Editores de texto

#### Instalar o [sublime text3](http://www.sublimetext.com/3)

```sh
sudo add-apt-repository ppa:webupd8team/sublime-text-3
sudo apt-get update
sudo apt-get install sublime-text-installer
```
#### Instalar o [Atom](https://atom.io/)

Acessa a página de [download](https://atom.io/)


#### Instalar o [Visual Studio Code](https://code.visualstudio.com/)

Acessa a página de [download](https://code.visualstudio.com/).

## Controle de versão

#### Instalar o [GIT](https://git-scm.com/)

```sh
sudo apt-get install git
```

## Gerenciamento de pacotes PHP

#### Instalar o [Composer](https://getcomposer.org/)

```sh
php -r "readfile('https://getcomposer.org/installer');" | php
Com o comando abaixo, basta digitar composer no prompt para acessar
sudo mv composer.phar /usr/bin/composer
```

Vale salientar que hoje em dia temos disponível o [Docker ](https://www.docker.com/) uma excelente ferramenta caso não deseje realizar as instalações diretamente na sua estação de trabalho.

As configurações listadas acima tem o intuído de auxiliar n as configurações básicas necessárias para a criação de um ambiente de desenvolvimento PHP, podendo ocorrer a necessidade de configurações mais específicas  de acordo com cada necessidade.
