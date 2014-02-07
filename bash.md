# Bash

## Shell

### Install font

    mv <font> ~/.fonts
    fc-cache

## .bashrc

### Command prompt
    
    export PS1='[\u@\h]:[\w] '

### Default switches

    alias grep='grep --color=auto'

### Typo correction

    alias cd..='cd ..'
    alias rm -rf /='echo \'Are you sure about that?\''
    
### Adding directories to the $PATH

    export PATH=$PATH:<newdir>

## Messing around

### Find IPs on a LAN

    nmap -sP 192.168.0.0/24 | grep -io '[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}'

