# Linux


It's true that the majority of things in other pages quite specifically work on Linux, but some are general/transferrable to other OS'. Note that the majority of this will work on Android devices too.


## Hosts file


The hosts file determines where to look for different URLs, it can be used to manipulate web browsing & trick machines into looking for certain URLs in different places - & so can be used to block tracking & advert services by directing those URLs to `127.0.0.1` (your computer's IP). The hosts file resides as `/etc/hosts` & uses the format:

    <ip> <name>

## Run on startup


This obviously only works with systems using `init.d` as their daemon:

    sudo ln -s <program path> /etc/init.d/<file>
    sudo update-rc.d <file> defaults     


## Cron


`crontab` is a tool for scheduling tasks, its name is derived from the Greek for time, *chronos*, & the *tab* for table.

* `sudo crontab -l` - view what crontabs are currently running on the system for your user.
* `sudo crontab -e` - edit the list of tasks.

### Format

The format of the `cronjobs` file is a bit odd, but fairly easy once you get your head around it:

    <minute> <hour> <day of month> <month> <day of week> <job>

### Examples

The following command is run every 10 minutes of 1am on Friday:
    
    */10 1 * * 5 /home/user/script.sh

The following command is run at quarter to and past every between 9am & 6pm every working weekday:

    15,45 9-18 * * 0-5 /home/user/script.sh


## Firewall


It's sensible to have a firewall. The easiest I've found to use is `ufw` (aptly, uncomplicated firewall). It's pretty easy to configure:

    sudo ufw <allow|deny> <port>
    sudo service ufw restart


## User administration

* `chsh -s <shell> <user>` - change the login shell for a user.


## Miscellaneous

### Zipping files

    zip [-r] <file>.zip <files to zip>

Don't assume recursion

### Find

    find [options] -exec <command> \{\} \;

Executes a command on the files found. `{}` represents a file found & the command must end with `;`, both of these must be escaped though.

### Installing fonts

Move the font to a sensible location where it won't get in the way & then regenerate the font cache.

    mv <font> ~/.fonts
    fc-cache

### Make directory structure (makes any missing parents)

    mkdir -p <directory>

### Find IPs on a LAN

    nmap -sP 192.168.0.0/24 | grep -io '[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}'
    
### Query nameserver

    nslookup <ip>

### SSH keys

First, we need to generate a keychain. We can apply a password to it if we like.

    ssh-keygen

To then create a key for a specific connection, we need to do the following.

    ssh-copy-id <user>@<host>

### Transferring files

The `-r` flag can be used to send file structures.

    scp <local file> <user>@<host>:<remote path>
    scp <user>@<host>:<remote file> <local path>

### Copying output to file

    <program> | tee [-a] <file>

Useful for watching output & keeping a copy. The `a` switch denotes appending to the file passed.


