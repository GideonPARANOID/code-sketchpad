# PHP

## General things

In a case where the PHP script itself never prints out anything, do not close the PHP in the document - this prevents headers from being sent in any circumstance.


## Useful functions

### JavaScript variable printing

Makes for easier debugging when making quick fixes & printing HTML is too messy.

    function var_dump_js($var) {
       echo '<script type=\'text/javascript\'>console.log(' 
          . json_encode($var) . ');</script>';
    }

### Heredoc

Useful for embedding HTML particularly, as it allows you maintain indentation.

    echo <<< EOD
    <string>
    EOD;

    $var .= <<< EOD
    <string>
    EOD;

Note that there should never be any whitespace after the closing marker.


## PHP CLI

### Test file syntax

    php -l <file>

### Run code from string

    php -r <string>

### Built in server

Requires PHP 5.4. Useful for testing web stuff, whether it's PHP or not, without a full blown server. Starts a web server with the document root as where it's run.

    php -S localhost:<port>
