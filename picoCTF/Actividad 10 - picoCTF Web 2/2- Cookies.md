## Descripción
Who doesn't love cookies? Try to figure out the best one.

[http://wily-courier.picoctf.net:50684/](http://wily-courier.picoctf.net:50684/)
## Solución
```
┌──(kali㉿kali)-[~]
└─$ curl -S http://wily-courier.picoctf.net:55434/check -h "cookie: name=10"
Unknown category provided, here is a list of all categories:

 auth        Authentication methods
 connection  Manage connections
 curl        The command line tool itself
 deprecated  Legacy
 dns         Names and resolving
 file        FILE protocol
 ftp         FTP protocol
 global      Global options
 http        HTTP and HTTPS protocol
 imap        IMAP protocol
 ldap        LDAP protocol
 output      File system output
 pop3        POP3 protocol
 post        HTTP POST specific
 proxy       Options for proxies
 scp         SCP protocol
 sftp        SFTP protocol
 smtp        SMTP protocol
 ssh         SSH protocol
 telnet      TELNET protocol
 tftp        TFTP protocol
 timeout     Timeouts and delays
 tls         TLS/SSL related
 upload      Upload, sending data
 verbose     Tracing, logging etc
                                                                                                                                                                                                                                                                              
┌──(kali㉿kali)-[~]
└─$ curl -s http://wily-courier.picoctf.net:55434/check -H "Cookie: name=10"
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Cookies</title>


    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css" rel="stylesheet">

    <link href="https://getbootstrap.com/docs/3.3/examples/jumbotron-narrow/jumbotron-narrow.css" rel="stylesheet">

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>

    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
</head>

<body>

    <div class="container">
        <div class="header">
            <nav>
                <ul class="nav nav-pills pull-right">
                    <li role="presentation"><a href="/reset" class="btn btn-link pull-right">Home</a>
                    </li>
                </ul>
            </nav>
            <h3 class="text-muted">Cookies</h3>
        </div>
        
        <!-- Categories: success (green), info (blue), warning (yellow), danger (red) -->
        
        
        <div class="alert alert-success alert-dismissible" role="alert" id="myAlert">
          <button type="button" class="close" data-dismiss="alert" aria-label="Close"><span aria-hidden="true">&times;</span></button>
          <!-- <strong>Title</strong> --> That is a cookie! Not very special though...
            </div>
      
      
      
        <div class="jumbotron">
            <p class="lead"></p>
            <p style="text-align:center; font-size:30px;"><b>I love biscotti cookies!</b></p>
        </div>


        <footer class="footer">
            <p>&copy; PicoCTF</p>
        </footer>

    </div>
    <script>
    $(document).ready(function(){
        $(".close").click(function(){
            $("myAlert").alert("close");
        });
    });
    </script>
</body>

</html>                                                                                                                                                                                                                                                                              
┌──(kali㉿kali)-[~]
└─$ for i in {1 .. 20} do; curl -s http://wily-courier.picoctf.net:55434/check -H "Cookie: name = $i" | grep "I love"; done 
zsh: parse error near `}'
                                                                                                                                                                                                                                                                              
┌──(kali㉿kali)-[~]
└─$ for i in {1..100}; do curl -s http://wily-courier.picoctf.net:55434/check -b "name=$i" | grep pico; done
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>academy{3v3ry1_l0v3s_c00k135_90a3a7cb}
```
```

```

## Notas Adicionales

## Referencias
-- [http://wily-courier.picoctf.net:55434/](http://wily-courier.picoctf.net:55434/)
