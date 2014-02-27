# Vim


[Vim's wiki](http://vim.wikia.com/) is pretty decent.


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

### Input/output

* `:w` - write file.
* `:q` - quit Vim.
* `:<w|q|wq>!` - force action.
* `:e <filename>` - open file.
* `:new <filename>` - new file.

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

### Search/replace

The basic command:

    :<context>/<search>/<replace>/<options>

#### Context

* `s` - only act on the current line.
* `%s` - act on all lines.

#### Options

Combinations of:

* `g` - all occurances in the context (other than just the first).
* `c` - ask for confirmation for each match.
* `I` - case sensitivity.
* `i` - case insenstivity.


### Running programs from inside Vim


    :!<program>


To reference the current page, use `%`, an example being `:!wc -l %` to print the line count of the current document.

### Navigation


* `:<line number>` - go to line.
* `:split` - split the screen horizontally.
* `:vsplit` - split the screen vertically.
* `CTRL` + `w` - tab between screens.
* `:e <filename>` - edit a different file.

