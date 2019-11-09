# Ubuntu Web Development Environment

## APT

### Web Development
* [git](https://raw.githubusercontent.com/audio333/references/master/git.md)
* apache2
* php
* [mysql-server](https://raw.githubusercontent.com/audio333/references/master/mysql.md)

   `$ mysql -u root -p`
* phpmyadmin
   > /etc/php/7.2/apache2/php.ini

   > /etc/apache2/apache2.conf
* sublime-text & sublime-merge
   > Visit Sublime Text Official Site
* virtualbox
* [vagrant](https://raw.githubusercontent.com/audio333/references/master/vagrant.md)
   * `$ vagrant up`
   * `$ vagrant ssh`
   * `$ vagrant halt`
   * `$ vagrant provision`
   * `$ vagrant box list`
   * `$ vagrant box add laravel/homestead`
   > homestead.yaml
* filezilla

### Dev Dependencies
* pug-sass

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
* ranger
* tree
* fonts-powerline


### Package Manager
* [nodejs](https://nodejs.org/en/) | [npm](https://raw.githubusercontent.com/audio333/references/master/npm.md)
   > Visit NodeJS Official Website
   > .gitconfig
* composer (php)

   `$ sudo /etc/init.d/apache2 restart`
* pip3 (python)
* curl
* snap

### Customization
* gnome-tweak-tool
* autokey-gtk
* ulauncher

   `$ sudo add-apt-repository ppa:agornostal/ulauncher`

### Utility
* trash-cli
* ppa-purge

   `$ sudo ppa-purge ppa:<package-name>`
* lm-sensors

   `$ sensors`

### Remote
* droidmote
   > /usr/bin/droidmote

### Media Player
* cmus

   * `$ add <path>`
   * `$ clear`
* mpv
* mplayer

### Stream & Downloaders
* youtube-dl

   `$ sudo pip3 install --user youtube-dl --upgrade`
* mps-youtube

   ```shell
   sudo apt install python3-venv python3-pip
   sudo pip3 install --user mpsyoutube
   sudo pip3 install --user -U git+https://github.com/mps-youtube/mps-youtube.git

   sudo pip3 install --user youtube-dl --upgrade
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
* copyq
* tmuxinator
* gnome-shell-extensions


## Ubuntu Software (GUI)
* chrome
* sublime text (outdated)
* synaptic package manager
* visual studio code

## Pre-installed:
* wget
* dpkg
* tar
* gzip
* nautilus


#### ENDED @ zsh_history line 3575