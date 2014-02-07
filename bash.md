# Bash


## Shell


### Installing fonts

Move the font to a sensible location where it won't get in the way & then regenerate the font cache.

    mv <font> ~/.fonts
    fc-cache

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
    


