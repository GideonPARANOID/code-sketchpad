# Web


## Lighttpd


Probably the easiest to configure web server ever.

### Prevent access to hidden stuff

    $HTTP["url"] =~ "\/\..*" {
       url.access-deny = ( "" )
    }


## Log file monitoring


[GoAccess](http://goaccess.prosoftcorp.com/) is a useful traffic monitoring tool, using Apache's logs to give a `top`-like CLI output.

    goaccess -f <log file>
    
       
