# Ubuntu Web Development Environment

## APT

### Web Development
* [git](https://raw.githubusercontent.com/audio333/references/master/git.md)
   > .gitconfig
* apache2

   `$ sudo /etc/init.d/apache2 restart`
* php
* [mysql-server](https://raw.githubusercontent.com/audio333/references/master/mysql.md)

   `$ mysql -u root -p`
* phpmyadmin
   > /etc/php/7.2/apache2/php.ini

   > /etc/apache2/apache2.conf
* sublime-text & sublime-merge
   > Visit Sublime Text Official Site
* [wp-cli](https://wp-cli.org/)
   > Visit WP-CLI official website
* filezilla
* mysql-workbench

### Virtual Environment
* virtualbox
* [vagrant](https://raw.githubusercontent.com/audio333/references/master/vagrant.md)
   > Visit Vagrant official site
   * `$ vagrant up`
   * `$ vagrant ssh`
   * `$ vagrant halt`
   * `$ vagrant provision`
   * `$ vagrant box list`
* laravel homestead
   > Visit Laravel Homestead Documentation
   * `$ vagrant box add laravel/homestead`
   > homestead.yaml
* [VVV](https://varyingvagrantvagrants.org/)
   > Visit Varying Vagrant Vagrants official site & github repo
* alecaddd/virtualhost

### NPM Global
> WARNING - do not use sudo!
> Check out https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally , first before installing packages
* parcel-bundler
* laravel-mix
* browser-sync
* pug-sass
* pug-cli

### Wordpress Starter Theme
* sage
* alecaddd/awps
* Anomareh/PHP-Twig.tmbundle
* robbinworks/sage-laravel-mix

### Composer Package
* timber/timber
* roots/sage

### Terminal
* terminator
* [tmux](https://raw.githubusercontent.com/audio333/references/master/tmux.md)
* zsh
   > ~/.zshrc
* oh-my-zsh
   > Visit Github Repo
* [vim](https://raw.githubusercontent.com/audio333/references/master/vim.md)

   `$ vimtutor`
   > ~/.vimrc
* neovim

   `$ nvim`
* file manager
   * ranger
   * fzf
      > Visit Github Repo
   * fasd
   * tree
   * trash-cli
* fonts-powerline

### Package Manager
* [nodejs](https://nodejs.org/en/) | [npm](https://raw.githubusercontent.com/audio333/references/master/npm.md)
   > Visit NodeJS Official Website
* nvm (node version manager)
  
  * `$ use`
  * `$ install --delete-prefix`
  * `$ alias default`
* yarn
* composer (php)
* pip3 (python)
* curl
* snap

### Customization
* gnome-tweak-tool
* ulauncher

   `$ sudo add-apt-repository ppa:agornostal/ulauncher`
* autokey-gtk
* xbindkeys
* copyq
* cmatrix

### Utility
* stow
* rsync
   * `$ sudo rsync -avr <src> <dest>`
   * `$ sudo rsync -aXS --progress --exclude='/*/.gvfs' /home/. /media/home/.`
* ppa-purge

   `$ sudo ppa-purge ppa:<package-name>`
* htop
* lm-sensors

   `$ sensors`
* soundconverter

### Remote
* droidmote
   > /usr/bin/droidmote

### Media Player
* mpv
* mplayer
* sxiv
* cmus

   * `$ add <path>`
   * `$ clear`

### Stream & Downloaders
* youtube-dl

   `$ sudo pip3 install --user youtube-dl --upgrade`
* mps-youtube

   ```shell
   sudo apt install python3-venv python3-pip

   sudo pip3 install --user mpsyoutube
   sudo pip3 install --user -U git+https://github.com/mps-youtube/mps-youtube.git

   sudo pip3 install --user youtube-dl --upgrade

   # issue
   # /usr/local/bin
   # https://github.com/mps-youtube/mps-youtube/issues/641
   ```
* youtube-viewer

   `$ sudo add-apt-repository ppa:nilarimogard/webupd8`

* peerflix
* torrentflix

### Network
* cifs-utils

   `$ sudo mount -t cifs //192.168.254.103/desktop\ files -o username=audio333 /mnt/share`
* net-tools

   `$ ifconfig`

### Removed packages:
* tmuxinator
* gnome-shell-extensions

## Ubuntu Software (UI)
* chrome
* sublime text (outdated)
* synaptic package manager
* visual studio code

## Snap (Package Manager)
* figma-linux
* musescore --edge (guitar pro reader)

## Pre-installed:
* wget
* dpkg
* tar
* gzip
* nautilus
