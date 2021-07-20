# Postgres client

sudo curl https://www.pgadmin.org/static/packages\_pgadmin\_org.pub | sudo apt-key add

sudo sh -c 'echo "deb https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'

sudo apt install pgadmin4-web

# RUNNING

sudo /usr/pgadmin4/bin/setup-web.sh
(use any mail and password)
 
open url
(use same mail and password)
 
click on add server 
 
name your server

ad ip and port in connections tab

add username and password of postgres server

click save to add server

