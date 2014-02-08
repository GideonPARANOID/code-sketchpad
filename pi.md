# Rasberry Pi

As I'm most familiar with Debian-based distros, I usually have my Raspberry Pi set up with [Raspbian](http://www.raspbian.org/).

## Ad-hoc Pi

Occasionally being without a switch or a screen makes accessing a Raspberry Pi tricky, but not impossible. 

No guarantees this'll work - I'm not a network guy. However, this is what worked when I tried. Advice from [this guide](http://pihw.wordpress.com/guides/direct-network-connection/in-a-nut-shell-direct-network-connection/).

* Append the string to the end of the line on the SD card (this can also be done via another computer with an SD card reader.

    sudo cp /boot/cmdline.txt /boot/cmdline.txt.backup
    sudo echo -n ' ip=192.168.0.2' >> /boot/cmdline.txt
    sudo reboot
    
* Disable all networking on your computer other than the ethernet cable between it & your Pi. 
* Set up a new wired network on your computer with the IPv4 method set to manual. Add a record to the addresses with an IP like `192.168.0.3` (the netmask & gateway aren't important).
* SSH to your Pi on the address you gave it in `/boot/cmdline.txt`!
