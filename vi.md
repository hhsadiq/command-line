#Vi-vim

###Vim: copy selection to OS X clipboard
For MacVim and Windows Gvim, simply add the following to your ~/.vimrc:

```shell
set clipboard=unnamed
```
Now all operations such as yy, D, and P work with the clipboard. No need to prefix them with "* or "+.