#Vi-vim

###Copy selection to OS X clipboard
For MacVim and Windows Gvim, simply add the following to your ~/.vimrc:

```shell
set clipboard=unnamed
```
Now all operations such as yy, D, and P work with the clipboard. No need to prefix them with "* or "+.

###Update your vim using homebrew
the vim shipped with mac is not latest and is not compiled with clipboard support. So install the latest using homebrew.

