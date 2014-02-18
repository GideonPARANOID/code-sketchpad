# Vim


## .vimrc


In concordance with my coding style preferrations:

    set expandtab
    set tabstop=3
    set shiftwidth=3
    set background=dark


## Keyboard shortcuts


### Basic stuff

* `ESC` - exit current mode.
* `i` - insert mode, normal typing.

### Writing files

* `:w` - write file.
* `:q` - quit Vim.
* `:<w|q|wq>!` - force action.

### Copy/paste

* `v` - visual select mode (selects text as you would expect).
* `SHIFT` + `v` - visual select line mode (select text by lines).
* `CTRL` + `v` - visual select block mode (select text in a square/rectangle).
* `c` - cut text.
* `y` - yank (copy text).
* `d` - delete text.
* `p` - paste over selection.

### Undo/redo

* `u` - undo.
* `CTRL` + `r` - redo.
