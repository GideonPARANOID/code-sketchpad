# PHP

## Useful functions

### JavaScript variable printing

Makes for easier debugging when making quick fixes & printing HTML is too messy.

    function var_dump_js($var) {
       echo '<script type=\'text/javascript\'>console.log(' 
          . json_encode($var) . ');</script>';
    }
    
## Other stuff

### Built in server

Requires PHP 5.4. Useful for testing web stuff, whether it's PHP or not, without a full blown server. Starts a web server with the document root as where it's run.

    php -S localhost:<port>
