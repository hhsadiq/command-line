#One stop shop for my commands

Most commonly used commands.
#mongodb
```shell
./mongodump --host <host>:<port> --username <username> --password <password> --authenticationDatabase <dbCodeFromLiveHost> --db <dbCodeFromLiveHost>
./mongorestore --host <host>:<port> --username <username> --password <password> --authenticationDatabase <dbCodeFromLiveHost> --db <dbCodeFromLiveHost> <dumpFolderPath>
```

###Meteor: Unexpected mongo exit code 100. Restarting.Can't start mongo server

These are the steps that solved my instance of this problem.

`Delete .meteor/local/db/mongod.lock`
`Delete .meteor/local/db/journal/j.*(note: I only moved it just in case! ;D)`
`sudo meteor`
sudo might not be necessary but it was the only way back into the app for me. Hope that saves someone a bit of time getting back up and running.

`https://stackoverflow.com/questions/15610385/meteor-unexpected-mongo-exit-code-100`

###Error with Future.js in Meteor Application
   
It seems to be unhappy about your build folder.

I would stop your app, then just delete the build folder mentioned in the first line of the logged error

`/Users/kishanpatel/Meteor/leaderboard/.meteor/local/build`
and then restart meteor.

It will simply recreate the build folder, probably without the problem you have right now.
`https://stackoverflow.com/questions/30383596/error-with-future-js-in-meteor-application`

# Digital ocean

```shell
ssh -p 1234 user@host
scp -P 22169 -o "PubkeyAuthentication no" ~/local/path/file.zip root@178.62.149.32:/var/www/sites
cd /var/www/html
sudo chown -R www-data:www-data /var/www/example.com/public_html
sudo ln -s /etc/nginx/sites-available/example.com /etc/nginx/sites-enabled/example.com #symlink
sudo rm /etc/nginx/sites-enabled/default
```

#Git

```shell
git init <directory>

git clone <repo>

git config user.name <name>

git add <directory>

git commit -m "message"

git status

git status --ignored #check the ignored files

```

###Remove .idea repo from git

```shell
mv .idea ../.idea_backup
rm .idea # in case you forgot to close your IDE
git add .idea 
git commit -m "Remove .idea from repo"
mv ../.idea_backup .idea
```

#Windows

###Free port 80 for xampp

Your port 80 is being used by the system.

In Windows “World Wide Publishing" Service is using this port and it's process is system which PID is 4 maximum time and stopping this service(“World Wide Publishing") will free the port 80 and you can connect Apache using this port. To stop the service go to the “Task manager –> Services tab”, right click the “World Wide Publishing Service” and stop.
If you don't find there then Then go to "Run > services.msc" and again find there and right click the “World Wide Publishing Service” and stop.Insha Allah that will work.
If you didn't find “World Wide Publishing Service” there then go to "Run>>resmon.exe>> Network Tab>>Listening Ports" and see which process is using port 80 enter image description here
And from "Overview>>CPU" just Right click on that process and click "End Process Tree". If that process is system that might be a critical issue.

Also, try stopping "SQL Server Reporting Services (MSSQLSERVER)", that apparently defaults to 80. I did that and port 80 freed up. PID identified the culprit as "System", but apparently that System can mean multiple things.

World Wide Web Publishing Service under running services.

If port is used by Skype, chnage port of skype from settings

###gitbash windows

```shell
CLIP < filename #copeis the content of file to clipboard
```

###How to add aliases for git bash windows

When you open up your Git Bash, you should be by default in your home directory. Now create the .bashrc file (if on Win7 the file should be named .bash_profile.). If you're not in the home directory change into it with:

```cd ~```

You can create the file with:

```touch .bash_profile```

Then edit it with vim or you could try doing it with some windows editor, but i don't recommend it, because of some text formatting issues.

```vim .bash_profile```

Change to Insert Mode by hitting the i key.

Add your alias:

```alias gs='git status'```

Exit the insert mode with ESC. And save-then-close your file with the following :wqEnter.

Finally source the file our open a new git bash.

```source .bash_profile```

###Configure Applications to Always Run as an Administrator
 
 1. On the Start menu, locate the program that you want to always run as an administrator. 
 2. Right-click the application’s shortcut, and then click Properties. 
 3. In the Properties dialog box, click the Compatibility tab. 
 4. Do one of the following: 
 
 To apply the setting to the currently logged-on user, select the Run This Program As An Administrator check box, and then click OK.
 To apply the setting to all users on the computer and regardless of which shortcut is used to start the application, click Change Setting For All Users to display the Properties dialog box for the application’s .exe file, select the Run This Program As An Administrator check box, and then click OK twice.

###gitbash aliases

```shell
alias art='php artisan'
alias edit='start'
alias vg='cd ~/Homestead && vagrant up && vagrant ssh && cd Code'
alias vgrl='vagrant reload --provision'
alias als='vi ~/.bash_profile'
alias h='cd ~'
alias c='clear'
alias bashrl='source ~/.bash_profile'
alias bashedit='edit ~/.bash_profile'
alias hostsedit='start C:/Windows/System32/drivers/etc/hosts'
alias yamledit='edit ~/.homestead/Homestead.yaml'
alias vgalsedit='edit ~/.homestead/aliases'
alias forgessh='ssh -i "/c/Users/Hassaan/.ssh/filename" forge@IP -vvv'
```

#Chrome
Clear the chrome hosts file cache if changes in hosts file are not detected.

```shell
chrome://net-internals/#dns
```

click clear cache

#Mac commands

###Sublime Text

Open files and folders in same window in Sublime Text
In Sublime Text Menu:
Preferences ->  Settings - User
Look for 'open_files_in_new_window'
And change 'true' with 'false'

###Open file in editor
```shell
open -a TextEdit #filename should do the trick.
```

The -a flag specifies any application you want, so it's applicable to any number of situations, including ones where TextEdit isn't the default editor.

Other relevant options

```shell
-t #opens in the default editor (i.e. if you use BBEdit, TextMate, etc.)
-e #will open the file specifically in TextEdit
```

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

###Add a path in $PATH

Add the following line to the end of the file adding whatever additional directory you want in your path:
```shell
export PATH="$HOME/.composer/vendor/bin:$PATH"
```
That example would add ~/.composer/vendor/bin to the PATH. The $PATH part is important as it appends the existing PATH to preserve it in the new value.

###Strange quotes of textedit
while editing bash_profile or path variable always use ' . The default textedit inserts ‘ which will cause errors. Similar is the case of double quotes.
###bash_profile aliases

```shell
alias sudo='sudo '
alias su='su '
alias art='php artisan'
alias edit='open -a PhpStorm'
alias vg='cd ~/Homestead && vagrant up && vagrant ssh && cd Code'
alias vgrl='vagrant reload --provision'
alias als='vi ~/.bash_profile'
alias h='cd ~'
alias bashrl='. ~/.bash_profile'
alias bashedit='edit ~/.bash_profile'
alias hostsedit='sudo vi /etc/hosts'
alias yamledit='edit ~/.homestead/Homestead.yaml'
alias vgalsedit='edit ~/.homestead/aliases'
```

###bash commands history

```shell
edit ~/.bash_history
```

###Generic aliases
```shell
export PATH="$HOME/.composer/vendor/bin:$PATH"
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
alias edit='open -a TextEdit'
```

### ~/.homestead/aliases
```shell
alias ..="cd .."
alias ...="cd ../.."
alias h='cd ~'
alias c='clear'
alias art='php artisan'
alias load=‘composer dump-autoload’
alias artm=‘php artisan make’ 
alias phpspec='vendor/bin/phpspec'
alias phpunit='vendor/bin/phpunit'
alias serve=serve-laravel
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

unzip file.zip -d destination_folder #sudo apt-get install unzip

du -sh #check size of current directory

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
vagrant reload --provision #run this after updating yaml file
vagrant ssh
vagrant halt #This command shuts down the running machine Vagrant is managing
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

###Windows bootloader recovery
I am dual booting with win8 and deleted the partition from it. After restarting I get the grub rescue prompt I tried to run Ubuntu off of a flashdrive and supergrub2 but neither worked and it went right back to rescue grub
That once happened to me. You need to put Windows 8 installation disc in your computer and start it. Then you go to repair system and to more options and select command prompt. Then, type the following commands: .

```
bootrec /WriteMbr
bootrec /Fixboot
bootrec /Fixmbr
```

It will probably say that it couldn't find any windows systems but that's normal - it will be fixed. THIS WILL DELETE GRUB AND INSTALL WINDOWS BOOTLOADER!

#XAMPP
add virtual hosts in xampp apache

hosts

```127.0.0.1 something.com```

virtual hosts file path

C:\xampp\apache\conf\extra\httpd-vhosts.conf

vritual hosts file settings

```shell
<VirtualHost *:80>
    DocumentRoot "C:/xampp/htdocs/something"
    ServerName something.com
</VirtualHost>
```


# server-configurations
A collection of commands which I used to configure server. Just for a backup and common place to look in future.


### Step by step guide for Laravel forge
https://mattstauffer.co/blog/getting-your-first-site-up-and-running-in-laravel-forge

### Step by step guide to install for digital ocean with LEMP stack

Insatll LEMP stack
https://www.digitalocean.com/community/tutorials/how-to-set-up-nginx-virtual-hosts-server-blocks-on-ubuntu-12-04-lts--3
https://www.digitalocean.com/community/tutorials/how-to-host-multiple-websites-securely-with-nginx-and-php-fpm-on-ubuntu-14-04

On mac
```ssh -i "~/.ssh/id_sshex" root@104.236.90.57```
On Windows
```ssh -i "/c/Users/Hassaan/.ssh/id_sshex" root@104.236.90.57```

#Meteor
when we build a slider from data we usually pass the ul/li to js and js code renders it and makes it slider
coming to this page, when page was first time loaded, the data was inserted and then js was called so we got the vendors
when we changed the city from top, the previous data was destroyed by meteor and new data was added (ul/li)
but we were not calling the JS code of sliders that was the reason new data was visible in source code
but was not complied into sliders

#Node-gyp installation

The installation of node-gyp is a bit tricky. Usually we get build node-gyp rebuild errors.
Follow the steps to install it without errors.

<ol>
<li>Install Microsoft Visual Studio C++ 2013 for Windows Desktop (Express version works well)</li>
<li>
Run from windows cmd
```call "C:\Program Files\Microsoft SDKs\Windows\v7.1\bin\Setenv.cmd" /Release /x86```
```call "C:\Program Files\Microsoft SDKs\Windows\v7.1\bin\Setenv.cmd" /Release /x64```
</li>
<li>```npm install --msvs_version=2013```</li>
</ol>