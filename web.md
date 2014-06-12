# Web


## Form design

[PGR](http://en.wikipedia.org/wiki/Post/Redirect/Get) is a useful design pattern for forms which prevents things like resubmission. A way of implementing this is to use JavaScript to send the form data as an AJAX request on submission, get a server side script to process the input, return a relevant [HTTP status code](http://en.wikipedia.org/wiki/List_of_HTTP_status_codes) & finally have the JavaScript interpret that.

### Example

JS:

    $.ajax({
       type : 'POST',
       url : './processing.php',
       data : <form>.serialize(),
       complete : function(xhr) {
          switch (xhr.status) {
    
          }
       }
    });


PHP:

    if (empty($_POST)) {
       http_response_code(400);
    } else {
   
       http_response_code(201);
    }

## Lighttpd


Probably the easiest to configure web server ever.

### Prevent access to hidden stuff

    $HTTP["url"] =~ "\/\..*" {
       url.access-deny = ( "" )
    }


## Log file monitoring


[GoAccess](http://goaccess.prosoftcorp.com/) is a useful traffic monitoring tool, using Apache's logs to give a `top`-like CLI output.

    goaccess -f <log file>
    
       
