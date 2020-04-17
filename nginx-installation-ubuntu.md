# Nginx Installation - Ubuntu

**Note:** nginx is a load balancer


Install Nginx
```
sudo apt-get update
sudo apt-get install nginx
```

Stop Start Restart
```
sudo service nginx stop
sudo service nginx start
sudo service nginx restart
```

Where to check logs
```
/var/log/nginx/error.log
```

Nginx location
```
/usr/share/nginx/html
/usr/share/nginx/html/index.html
```

Ref:
  * [Request Processing - Nginx]([docker-commands.md](http://nginx.org/en/docs/http/request_processing.html))