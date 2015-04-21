# Android


## SDK


The Android SDK can be found on the [Android developers site](http://developer.android.com/sdk/index.html). The only tools we really need are `fastboot` & `adb` though. It's best to get them from the official SDK for integrity purposes.


## ROMs & recovery

Best place to look for these is the [XDA developers forum](http://forum.xda-developers.com/).

I tend to use [ClockworkMod](http://www.clockworkmod.com/) as a recovery. It's fairly powerful & supports touch which makes life that little bit easier.


## fastboot


`fastboot` is the program used for talking with your device while it's in the bootloader. Personally, I prefer using `adb` for working with Android, but there are times when using `adb` isn't an option, such as if USB/remote debugging is turned off.

### Flashing with fastboot

    flash <partition> <file>


## adb


Android Developer Bridge is powerful, with features such as shell access to the device & the ability to run over a network.

### No permissions

This happens when running with a device for the first time on a computer, due to the device not trusting the computer. Running `sudo adb` should fix this.

### Sending/retrieving files

    adb <push|pull> <file>


## Monkey

Monkey is a really great UI testing tool which just spams loads of events (including system ones) at a device and particular package for testing reasons.

    adb shell monkey -p <package> -v <number of events>

Use the `--throttle <milliseconds>` switch to slow down operation of Monkey to see what's happening.

