#Mac specific commands

To run a non-executable sh script, use:

```shell
sh myscript
```
To run a non-executable bash script, use:

```shell
bash myscript
```

Cope file to clipboard

```shell
cat fileNmae | pbcopy
```

Add aliases

```shell
vi ~/.bash_profile

alias vag='cd ~/Homestead; vagrant up; vagrant ssh; cd Code;' #Add this in .bash_profile
```