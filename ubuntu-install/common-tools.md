## Steps to setup ubuntu system for software developer:

sudo apt-get update
sudo apt-get upgrade

## Ubuntu 16.04 Developer Tools Installation

First things first !
```bash
sudo apt update
sudo apt upgrade

sudo apt-get install build-essential git
sudo apt-get install gfortran

sudo apt-get install python-dev python-pip python-virtualenv python-numpy python-matplotlib


x-11 windows

$ sudo apt-get -y install libx11-dev



> export PATH="`pwd`/cmake-3.4.1-Linux-x86_64/bin:$PATH" # save it in .bashrc if needed
> which cmake
/.../cmake-3.4.1-Linux-x86_64/bin/cmake
> which cmake-gui
/.../cmake-3.4.1-Linux-x86_64/bin/cmake-gui


echo "export PATH=$HOME/.cmake-3.15.1/bin:$PATH" >> ~/.bashrc



### Parallel Processing with OpenMPI

```bash
#install pre-requisites
sudo apt-get install libibnetdisc-dev
# download codebase
wget https://download.open-mpi.org/release/open-mpi/v4.0/openmpi-4.0.1.tar.gz
# extract
tar -xzvf openmpi-4.0.1.tar.gz
# configure and build
./configure --prefix="$HOME/.openmpi"
make -j4
sudo make install
echo "export PATH=$PATH:$HOME/.openmpi/bin" >> ~/.bashrc
echo "export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$HOME/.openmpi/lib/" >> ~/.bashrc
```


### Editor
install vim
```bash
sudo apt install vim
```
Install Atom Editor [download](https://github.com/atom/atom/releases/download/v1.23.3/atom-amd64.deb)
```bash
sudo dpkg -i atom-amd64.dev
```
Install Visual Studio Code [download](https://code.visualstudio.com/docs/?dv=linux64_deb)
```bash
sudo dpkg -i code_<version>.deb
```


### Ubuntu Customization (Theme and Icons)
Install Gnome Tweak Tool
```bash
sudo apt install gnome-tweak-tool



# Create Theme and Icon directory
mkdir ~/.icons ~/.themes
```
Download Themes and Icons, Place it under respective directory and open tweak tool select your themes



Suggested Themes and 
1. [Flatabulous](https://github.com/anmoljagetia/Flatabulous)
2. [Paper-Theme](https://github.com/snwh/paper-gtk-theme)
3. [Paper-Icon-Theme](https://github.com/snwh/paper-icon-theme)




### Install ZSH
```bash
sudo apt install zsh
curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh
chsh -s `which zsh`
```


### Web Development in PHP with Apache2 Web Server
```bash
#Install apache2 and php
sudo apt install apache2 apache2-utils libapache2-mod-php
sudo apt install php php-dev php-mcrypt php-mysql php-mbstring php-dom
# Enable mod_rewrite for apache2
sudo a2enmod rewrite
```
Configure index.php for priorities add index.php `sudo nano /etc/apache2/mods-available/dir.conf`
```
<IfModule mod_dir.c>
	DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>
```
Configure Mod Rewrite `sudo nano /etc/apache2/sites-available/000-default.conf`
```
<VirtualHost *:80>
	ServerAdmin webmaster@localhost
	DocumentRoot /var/www/html

    <Directory /var/www/html>
        Options FollowSymLinks MultiViews Indexes
        AllowOverride All
        Order allow,deny
        allow from all
    </Directory>

	ErrorLog ${APACHE_LOG_DIR}/error.log
	CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
Reload Apache `sudo service apache2 restart`



### Java Development
```bash
# install jdk
sudo apt install openjdk-8-jdk
# install maven
sudo apt install maven
```
Install eclipse [dowload](http://www.eclipse.org/downloads/download.php?file=/technology/epp/downloads/release/oxygen/2/eclipse-java-oxygen-2-linux-gtk-x86_64.tar.gz)

### Ruby Development

```bash
# install pre requisites
sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev

# clone rbenv
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
git clone https://github.com/rbenv/rbenv-gem-rehash.git ~/.rbenv/plugins/rbenv-gem-rehash

# add configuration to bashrc
echo "export PATH=$PATH:$HOME/.rbenv/bin:$HOME/.rbenv/shims" >> ~/.bashrc
echo "eval $(rbenv init -)" >> ~/.bashrc
echo "export PATH=$HOME/.rbenv/plugins/ruby-build/bin:$PATH" >> ~/.bashrc
# install and set specific ruby version
rbenv install 2.3.0
rbenv global 2.3.0
# install some gems
gem install bundler jekyll mysql2 rails jekyll-pagedown
```



### Database
```bash
# install nosql database
sudo apt install mongodb-server
# install sqlite3 for smaller db
sudo apt install libsqlite3-dev sqlite3
# mysql community version installation
sudo apt install mysql-server libmysqlclient-dev
```



### NodeJs Development
```bash
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
sudo npm install -g grunt-cli yarn @angular/cli
```



### ASP.NET Development
```bash
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
echo "deb http://download.mono-project.com/repo/debian wheezy main" | sudo tee /etc/apt/sources.list.d/mono-xamarin.list
sudo apt update

# install mono libraries
sudo apt install mono-devel mono-complete referenceassemblies-pcl ca-certificates-mono mono-xsp4
# install mono ide
sudo apt install monodevelop-nunit monodevelop-versioncontrol monodevelop-database
```



### CLoud Storage (Dropbox)
```bash
cd ~ && wget -O - "https://www.dropbox.com/download?plat=lnx.x86_64" | tar xzf -
# to start dropbox
sh ~/.dropbox-dist/dropboxd
```








