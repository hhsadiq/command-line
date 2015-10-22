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

