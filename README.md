#One stop shop for my commands

Every single command which I type in command line, is replicated here. It is one stop shop to keep track of my used commands.

# server-configurations
A collection of commands which I used to configure server. Just for a backup and common place to look in future.

# Step by step guide to install first website on digital ocean with LEMP stack

Insatll LEMP stack
https://www.digitalocean.com/community/tutorials/how-to-set-up-nginx-virtual-hosts-server-blocks-on-ubuntu-12-04-lts--3
https://www.digitalocean.com/community/tutorials/how-to-host-multiple-websites-securely-with-nginx-and-php-fpm-on-ubuntu-14-04


# Digital ocean

```shell
cd /var/www/html
sudo chown -R www-data:www-data /var/www/example.com/public_html
sudo ln -s /etc/nginx/sites-available/example.com /etc/nginx/sites-enabled/example.com #symlink
sudo rm /etc/nginx/sites-enabled/default
```

الحمد للہ۔ آج تقریبا دو ہفتے کی محنت کے بعد میں پہلی ویب سائٹ کو لائیو کرسکا ہو۔

5:59PM 17oct 2015
Digital ocean droplet, from lemp stack to launch of first site.

#Git

```shell
git init <directory>

git clone <repo>

git config user.name <name>

git add <directory>

git commit -m "message"

git status
```

#gitbash windows

```shell
CLIP < filename #copeis the content of file to clipboard
```

#Mac commands

###run .sh file
To run a non-executable sh script, use:

```shell
sh myscript
```
To run a non-executable bash script, use:

```shell
bash myscript
```

###Cope file to clipboard

```shell
cat fileNmae | pbcopy
```

###Add aliases

```shell
vi ~/.bash_profile

alias vag='cd ~/Homestead; vagrant up; vagrant ssh; cd Code;' #Add this in .bash_profile
```

Exit vi mode and reload settings using this command
```shell
. ~/.bash_profile
```

###Alias collection
Aliases in my mac

```shell
alias #listing of defined aliases
unalias ALIAS_NAME #remove already defined alias
alias vagrant='cd ~/Homestead && vagrant up && vagrant ssh && cd Code'
alias als='vi ~/.bash_profile'
alias h='cd ~'
alias rlals='. ~/.bash_profile'
alias art='php artisan'
alias migrate='php artisan migrate'
alias mc='php artisan make:controller'
alias mms='php artisan make:migration:schema'
```

###Install homebrew

run command from http://brew.sh/


#Mysql

```mysql
show tables;
use db_name;
describe table_name;
```

# Generic unix based commands
These commands can be used on any unix based system.

```shell
tar czf home.tar.gz home/ #tar gz compression

tar xf file.tar #extract files

ls -l --block-size=M #listing with file sizes in MB

mv /home/user/oldname /home/user/newname

ssh-keygen -t rsa -f generate_file_name

ls -la #listting with hidden files

ls

ll

```

# Vagrant
```shell
vagrant init #initialize vagrant in new directory
vagrant up
vagrant reload --prvision #run this after updating yaml file
vagrant ssh
php -i | grep php.ini #search file path in system
```
Do not install npm and gulp on vagrant homestead, instead install it on local maching. The installation on vagrant does not work.

#Vi-vim

###Copy selection to OS X clipboard
For MacVim and Windows Gvim, simply add the following to your ~/.vimrc:

```shell
set clipboard=unnamed
```
Now all operations such as yy, D, and P work with the clipboard. No need to prefix them with "* or "+.

###Update your vim using homebrew
the vim shipped with mac is not latest and is not compiled without clipboard support. So install the latest using homebrew.