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
    command Wq wq
    command Q q
    command W w

The plugin manager [Pathogen](https://github.com/tpope/vim-pathogen).

    execute pathogen#infect()
    syntax on
    filetype plugin indent on


## Plugins


With Pathogen, plugins are dead easy to install. Simply:

    cd ~/.vim/bundle/
    git clone <git repository>

### Personal favourites

* [Pathogen](https://github.com/tpope/vim-pathogen) provides a simple way of installing plugins.
* [delimitMate](http://www.vim.org/scripts/script.php?script_id=2754) provides automatic closure of parentheses, quotes & brackets.


## Control


### Basic stuff

* `ESC` - exit current mode.
* `i` - insert mode, normal typing.

### Input/output

* `:w` - write file.
* `:w <file>` - write file (continues editing original file).
* `:q` - quit Vim.
* `:<w|q|wq>!` - force action.
* `:e <file>` - open file.
* `:new <file>` - new file.

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
* `:spl` - split the screen horizontally.
* `:vspl` - split the screen vertically.
* `CTRL` + `w` - tab between screens.
* `/<search term>` - go to results, `n` for next, `N` for previous.

### Running programs from inside Vim


    :!<program>


To reference the current page, use `%`, an example being `:!wc -l %` to print the line count of the current document.

### Undo/redo

* `u` - undo.
* `CTRL` + `r` - redo.

## Actions

### Copy/paste

* `c` - cut text.
* `y` - yank (copy text).
* `d` - delete text.
* `p` - paste over selection.
* `:set paste` - paste from clipboard cleanly (`:set nopaste` to exit mode).

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
* `:g/<pattern 1>/+1;/<pattern 2>/-1d` - delete everything between two patterns.


### Indentation

* `>` - indent.
* `<` - dedent.

Following either of the above commands with `.`s does the same action again, useful for indenting multiple times.


## Other

* `:%s/<pattern>//gn` - count matches to pattern in a file.
