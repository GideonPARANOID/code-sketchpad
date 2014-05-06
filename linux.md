# Linux


It's true that the majority of things in other pages quite specifically work on Linux, but some are general/transferrable to other OS'. Note that the majority of this will work on Android devices too.


## Hosts file


The hosts file determines where to look for different URLs, it can be used to manipulate web browsing & trick machines into looking for certain URLs in different places - & so can be used to block tracking & advert services by directing those URLs to `127.0.0.1` (your computer's IP). The hosts file resides as `/etc/hosts` & uses the format:

    <ip> <name>

## Run on startup


This obviously only works with systems using `init.d` as their daemon:

    sudo ln -s <executable filepath> /etc/init.d/<file>
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

    zip <file>.zip <files to zip>
