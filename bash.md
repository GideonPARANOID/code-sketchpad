# Bash


## Shell

### Keyboard shortcuts

A fairly exhaustive list can be found on the [Bash Wikipedia page](http://en.wikipedia.org/wiki/Bash_(Unix_shell)). These are the ones I use though.

* `CTRL`+`c` - send a `SIGINT` signal, killing any running task.
* `CTRL`+`d` - send an `EOF` marker, closing the current shell.
* `CTRL`+`z` - send a `SIGSTP` signal, suspending the current task. The last suspended job can be resumed with `fg` to run in the foreground or `bg` for the background. Suspended tasks can be found with `jobs` & killed with `kill %<job ID>`.
* `CTRL`+`s` - stop printing to the terminal, though the program will run in the background.
* `CTRL`+`q` - resume terminal printing.

### Installing fonts

Move the font to a sensible location where it won't get in the way & then regenerate the font cache.

    mv <font> ~/.fonts
    fc-cache

### SSH keys

First, we need to generate a keychain. We can apply a password to it if we like.

    ssh-keygen
    
To then create a key for a specific connection, we need to do the following.

    ssh-copy-id <user>@<server>


## .bashrc


### Command prompt
    
    export PS1='[\u@\h]:[\w] '

### Default switches

    alias grep='grep --color=auto'

### Typo correction

    alias cd..='cd ..'
    
### Adding directories to a $PATH

    export PATH=$PATH:<newdir>


## Scripting

Bash scripting can be a bit confusing, due to its unusual control structures, but I find it really rewarding. Perhaps because it feels like if you can understand something someone else can't, you feel a bit smug.

The reference/guide I've found so far is found on [The Linux Documentation Project](http://tldp.org/LDP/Bash-Beginners-Guide/html/).

## Messing around

### Find IPs on a LAN

    nmap -sP 192.168.0.0/24 | grep -io '[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}'
    


