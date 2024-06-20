# POP OS
pop os setup for php laravel development

## windows dual boot time wrong
```timedatectl set-local-rtc 1```

## install curl
```sudo apt install curl```

## install git
```
sudo apt install git
git config --global user.name "hesham14yahia"
git config --global user.email "hesham14yahia@gmail.com"
git config --global credential.helper store
git config --global alias.add-commit '!git add -A && git commit'
git config --global alias.uncommit 'reset --soft HEAD^'
git config --global core.filemode false // might need it with pop os
```
## install fonts for better visuals
```
sudo apt install ubuntu-restricted-extras -y
sudo apt install fonts-firacode
git clone https://github.com/powerline/fonts.git // fonts for zsh
mv fonts powerline-fonts
cd powerline-fonts
./install.sh
.\install.ps1
sudo fc-cache -f -v
```
## install zsh
```
sudo apt install zsh -y
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
sh -c "$(curl -fsSL https://raw.github.com/vemonet/biratime/main/install.sh)"
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
nano ~/.zshrc
plugins=(git laravel node npm composer git python zsh-autosuggestions)
"fontFace" : "DejaVu Sans Mono for Powerline"
```
* add arabic lang setting

* install chrome

vscode setting
"editor.fontFamily": "'Noto Mono', 'Courier New', monospace",
"editor.fontFamily": "Ubuntu Mono",
"editor.fontSize": 16,

## install brave
```
sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg arch=amd64] https://brave-browser-apt-release.s3.brave.com/ stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list
sudo apt update
sudo apt install brave-browser
```
*install free download manager

## laptop power tweeks
```
sudo apt install tlp
sudo add-apt-repository -y ppa:linuxuprising/apps
sudo apt update
sudo apt install tlpui
```

## install flameshot
```
sudo apt install flameshot
```
https://flameshot.org/docs/guide/key-bindings/#:~:text=Open%20Settings%20%E2%86%92%20Devices%20%E2%86%92,Flameshot'%20or%20'PrintScreen'.

* install dash to panel
* import setting file

## install php
```
check version "apt-cache policy php"
check link "https://www.tecmint.com/install-php-8-on-ubuntu/"
sudo apt install ca-certificates apt-transport-https software-properties-common
sudo add-apt-repository ppa:ondrej/php
sudo apt update

sudo apt install php7.2-fpm php7.2-curl php7.2-mbstring php7.2-mysql php7.2-xml php7.2-cli php7.2-zip php7.2-bcmath php7.2-gd unzip network-manager libnss3-tools jq xsel

sudo apt install php7.4-fpm php7.4-curl php7.4-mbstring php7.4-mysql php7.4-xml php7.4-cli php7.4-zip php7.4-bcmath php7.4-gd unzip network-manager libnss3-tools jq xsel

sudo apt install php8.0-fpm php8.0-curl php8.0-mbstring php8.0-mysql php8.0-xml php8.0-cli php8.0-zip php8.0-bcmath php8.0-gd unzip network-manager libnss3-tools jq xsel

sudo apt install php8.1-fpm php8.1-curl php8.1-mbstring php8.1-mysql php8.1-xml php8.1-cli php8.1-zip php8.1-bcmath php8.1-gd unzip network-manager libnss3-tools jq xsel

sudo apt install php8.2-fpm php8.2-curl php8.2-mbstring php8.2-mysql php8.2-xml php8.2-cli php8.2-zip php8.2-bcmath php8.2-gd unzip network-manager libnss3-tools jq xsel

sudo apt install php8.3-fpm php8.3-curl php8.3-mbstring php8.3-mysql php8.3-xml php8.3-cli php8.3-zip php8.3-bcmath php8.3-gd unzip network-manager libnss3-tools jq xsel
```
edit php.ini
upload_max_filesize 5000M
post_max_size 5000M
memory_limit 256M
max_execution_time 300
max_input_time 300

## install composer
```
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php composer-setup.php && php -r "unlink('composer-setup.php');"
sudo mv /home/hesham/composer.phar /usr/bin/composer
sudo chmod +x /usr/bin/composer
```

## install valet
```
composer global require cpriego/valet-linux
echo 'export PATH="$PATH:$HOME/.config/composer/vendor/bin"' >> ~/.zprofile
source ~/.zprofile
valet install
cd ~/.valet/Sites
valet park
```

## install mysql sever
```
sudo apt install mysql-server -y
"local" => sudo mysql || "on server" => mysql -u root -p
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
exit;
// sudo service mysql stop
// sudo usermod -d /var/lib/mysql/mysql
// sudo service mysql start
```

* install phpmyadmin

import and export db
import "mysql -u root -p database_name < file.sql"
export "mysql -u root -p database_name > file.sql"
disable foreign key check "sudo mysql -u root -p"
SET GLOBAL FOREIGN_KEY_CHECKS=0;
SET GLOBAL FOREIGN_KEY_CHECKS=1;

## install node/nvm
```
sudo apt update
curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash
source ~/.nvm/nvm.sh
nvm --version
nvm install node
```

## change terminal
```sudo update-alternatives --config x-terminal-emulator```

* install slack

* install zoom

* install onlyoffice

* install postman

## gnome customiztion
* gsettings set org.gnome.shell.extensions.dash-to-dock click-action "minimize" // no need in pop os
* gsettings set org.freedesktop.ibus.panel.emoji hotkey "[]" // pop os ctrl+shift+e issue
* switch alt tab to window switch
* install gnome extensions manager
* gnome extensions
* audio selector
* clipboard indicator
* user themes
* just perfection
* places status indicator
* removable drive indicator
* Date Menu Formatter ( EEE, MMM d ' | ' h : mm aaa ' ')
* Media Controls
* Dash to Dock


## turn off bluetooth on login
```echo "rfkill block bluetooth" >> ~/.zprofile```

## fix external drive unkown error
```sudo ntfsfix /dev/sdb1```

## switch windows with alt + tab
* settings > keyboard > navigation > switch windows
```
gsettings set org.gnome.desktop.wm.keybindings switch-windows "['<Alt>Tab', '<Super>Tab']"
```
