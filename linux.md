# Linux


It's true that the majority of things in other pages quite specifically work on Linux, but some are general/transferrable to other OS'. Note that the majority of this will work on Android devices too.


## Hosts file


The hosts file determines where to look for different URLs, it can be used to manipulate web browsing & trick machines into looking for certain URLs in different places - & so can be used to block tracking & advert services by directing those URLs to `127.0.0.1` (your computer's IP). The hosts file resides as `/etc/hosts` & uses the format:

    <ip> <name>
    
