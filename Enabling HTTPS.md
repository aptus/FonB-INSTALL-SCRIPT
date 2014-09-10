Enabling HTTPS
==================

FonB can run in secure HTTP environment with minor changes to the system where FonB is installed. You will have to follow the following steps to make this happen:

1. Create /etc/httpd/conf.d/fonb.conf
Create a new file using vi /etc/httpd/conf.d/fonb.conf, go to insert mode by pressing ‘a’ and then put the following in there:

```
<Directory "/var/www/html">
    RewriteEngine On
    RewriteRule    ^fonb$	 /fonb/    [R=302]
    RewriteRule    ^fonb/(.*)$  http://%{HTTP_HOST}:8080/$1  [P]
    ErrorDocument 503 /503.html
</Directory>
```

Press Esc and then :wq to save and exit.

2. Restart Apache Service
Restart Apache service using:

service httpd restart

3. Restart FonB Service
Restart FonB Service using:

service phoneb restart

4. Navigate to FonB
Please note that you will have to navigate to FonB Web Interface using:

https://YOUR_FONB_IP_WITHOUT_PORT/fonb

Notice that we didn’t use Port here anymore. It’s deliberate as you don’t need to use the port.
