# Web


## Permissions


| Type      | Permissions | chmod | Description                                        |
| :-------- | :---------: | ----: | :------------------------------------------------- |
| Directory | `rwxr-xr-x` |   755 | To enter a folder you need executable              |
| HTML      | `rwxr--r--` |   744 | Only needs to be viewable to the public            |
| CSS       | `rwxr-xr-x` |   744 | Only needs to be read                              |
| PHP       | `rwxr--r--` |   744 | Scripts are executed by the server, not the viewer |


## Lighttpd


Probably the easiest to configure web server ever.


## Log file monitoring


[GoAccess](http://goaccess.prosoftcorp.com/) is a useful traffic monitoring tool, using Apache's logs to give a `top`-like CLI output.

    goaccess -f <log file>
    
       
