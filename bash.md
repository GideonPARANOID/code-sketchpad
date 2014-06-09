# Bash


## Interactive shell

### Keyboard shortcuts

A fairly exhaustive list can be found on the [Bash Wikipedia page](http://en.wikipedia.org/wiki/Bash_(Unix_shell)). These are the ones I use though.

* `CTRL` + `c` - send a `SIGINT` signal, killing any running task.
* `CTRL` + `d` - send an `EOF` marker, closing the current shell.
* `CTRL` + `z` - send a `SIGSTP` signal, suspending the current task. The last suspended job can be resumed with `fg` to run in the foreground or `bg` for the background. Suspended tasks can be found with `jobs` & killed with `kill %<job id>`.
* `CTRL` + `s` - stop printing to the terminal, though the program will run in the background.
* `CTRL` + `q` - resume terminal printing.
* `CTRL` + `l` - clear the terminal.

## Moving data around

* `$(<program>)` - capture output of program to variable.
* `<program> &> <file>` - append everything to a file.
* `<program> 2> <file>` - append errors to a file.


## .bashrc


### Command prompt

The colour of the present working directory is dependent on the exit status of the most recently finished task.
    
    export PS1="[\u@\h]:\[\`if [[ \$? = "0" ]]; then echo '\e[32m[\w]\e[0m'; else echo '\e[31m[\w]\e[0m' ; fi\` "

### Default switches

    alias grep='grep --color=auto'
    alias lynx='lynx -accept_all_cookies'

### Typo correction

    alias cd..='cd ..'
    
### Shortcuts

    alias ls='ls --color=auto'
    alias l='ls -lhFg'
    alias lt='ls -lhFg --sort time'
    alias lygo='lynx google.co.uk' 

### Miscellaneous

    export THEANSWERTOTHEULTIMATEQUESTION=42
    
### Adding directories to a $PATH

    export PATH=$PATH:<directory>


## Scripting

Bash scripting can be a bit confusing, due to its unusual control structures, but I find it really rewarding. Perhaps because it feels like if you can understand something someone else can't, you feel a bit smug.

The reference/guide I've found so far is found on [The Linux Documentation Project](http://tldp.org/LDP/Bash-Beginners-Guide/html/).

### Control statements

#### For loop

    for i in <list|generator>; do

    done

#### If

    if [ <test> ]; then

    elif [ <test> ]; then

    fi

#### Switch

    case <variable> in
       <option>)
          ;;
       *)
          ;;
    esac


#### Function

    test() {
         
    }

Functions are called like a program in bash, with arguments afterwards, these can be accessed with `$1` .etc inside the function.


### String stuff

* `${<variable>/<search>/<replace>}` - find & replace in a string.
* `${<variable>//<search>/<replace>}` - find & replace all matches in a string.
* `${<variable>,,}` - converts string to lower case.
* `${<variable>##*/}` - chops string down the last subdirectory.


### Iterating through a file


    while read i; do
       
    done < <file>
