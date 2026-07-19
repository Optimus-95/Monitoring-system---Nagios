# Nginx Configuration

## Create Configuration File

```bash
sudo vi /etc/nginx/conf.d/nginx_ws.conf
```
Add Nginx Configuration
### Add below in nginx_ws.conf: ###

        location /nagios {
        alias /opt/nagios/share;
        index index.php index.html;
        server_tokens off;
        #allow all;
 
        auth_basic "Private";
        auth_basic_user_file /etc/nagios/htpasswd.users;
 
        location ~ \.php$ {
            include /etc/nginx/fastcgi_params;
            fastcgi_param SCRIPT_FILENAME $request_filename;
            #fastcgi_param SCRIPT_FILENAME /opt/nagios/share$fastcgi_script_name;
            #fastcgi_param SCRIPT_FILENAME  $fastcgi_script_name;
            #fastcgi_param SCRIPT_FILENAME  $document_root$request_filename;
            fastcgi_param AUTH_USER $remote_user;
            fastcgi_param REMOTE_USER $remote_user;
            fastcgi_pass 127.0.0.1:9000;
        }
        location ~ \.cgi$ {
            root /opt/nagios/sbin;
            rewrite ^/nagios/cgi-bin/(.*)\.cgi /$1.cgi break;
            include /etc/nginx/fastcgi_params;
            fastcgi_param SCRIPT_FILENAME $request_filename;
            fastcgi_param AUTH_USER $remote_user;
            fastcgi_param REMOTE_USER $remote_user;
            fastcgi_pass unix:/var/run/fcgiwrap.socket;
        }
    }


# Reload Nginx
```bash
sudo nginx -s reload
```
