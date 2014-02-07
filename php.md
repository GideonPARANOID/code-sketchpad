# PHP

## JavaScript variable printing

Makes for easier debugging when making quick fixes & printing HTML is too messy.

    function var_dump_js($var) {
       echo '<script type=\'text/javascript\'>console.log(' 
          . json_encode($var) . ');</script>';
    }
