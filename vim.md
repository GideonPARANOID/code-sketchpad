# Vim


[Vim's wiki](http://vim.wikia.com/) is pretty decent.


## .vimrc


In concordance with my coding style preferrations & making life a bit easier:

    set expandtab
    set tabstop=3
    set shiftwidth=3
    set autoindent

General look & feel things - background (I prefer dark terminals):

    set background=dark

It's a pain when I get the capitalisation of these wrong, especially when they're not mapped to anything else anyway:

    command WQ wq
    command Q q
    command W w



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

### Selection

* `v` - visual select mode (selects text as you would expect).
* `SHIFT` + `v` - visual select line mode (select text by lines).
* `CTRL` + `v` - visual select block mode (select text in a square/rectangle).
* `gv` - reselect previously selected block.

You can do a number of things with selected text:

### Navigation

* `:<line number>` - go to line.
* `gg` or `1G` - go to top of the file.
* `G` - go to the end of the file.
* `:split` - split the screen horizontally.
* `:vsplit` - split the screen vertically.
* `CTRL` + `w` - tab between screens.
* `/<search term>` - go to results, `n` for next, `N` for previous.

### Running programs from inside Vim


    :!<program>


To reference the current page, use `%`, an example being `:!wc -l %` to print the line count of the current document.

#### Indentation

* `>` - indent.
* `<` - dedent.
* `>..` - indents two times.

### Undo/redo

* `u` - undo.
* `CTRL` + `r` - redo.

### Copy/paste

* `c` - cut text.
* `y` - yank (copy text).
* `d` - delete text.
* `p` - paste over selection.

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

### Global command

A very powerful command with a number of different functions:

    :<g|g!>/<pattern>/<option>

#### Options

* `d` - delete.
* `t` - copy.
* `m` - move.
* `y` - copy.

#### Examples

* `:g/^\s*$/d` - deletes every line of whitespace (matches regex).
* `:g/DEBUG/t$` - copies every line containing 'DEBUG' to the end of the file.
* `:g!/test/m$` - moves every line that doesn't contain 'test' to the end of the file.

