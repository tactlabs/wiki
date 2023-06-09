/ [Home](index.md)

# MySQL Workbench 

## MySQL Workbench Installation in MacOS

- Install MySQL server using MySQL website or brew
```
brew install mysql
``` 

- Install MySQL Workbench on macOS from [MySQL website](https://dev.mysql.com/downloads/workbench/)

- Go to terminal and start MySQL server services using brew
```
brew services start mysql
```

- Set a root username and password for MySQL server

- Type this command in terminal
```
mysql -u root -p
```
and enter password to check if MySQL server connection is working or not

- Go to MySQL Workbench in MySQL Connections click + icon to add a new connection

- You can name your connection

- Click Test Connection if asked enter your MySQL server root password then it will show status whether connection is successful or not
then click ok

- In home page click to your new Connection to view MySQL database in Workbench


## MySQL Workbench Installation in Linux

- To install it, update the package
```
sudo apt update
```

- Then install the mysql-server package:
```
sudo apt install mysql-server
```

- Ensure that the server is running using the systemctl start command

```
sudo systemctl start mysql.service
```

- Set a root username and password for MySQL server

- Type this command in terminal
```
mysql -u root -p
```
and enter password to check if MySQL server connection is working or not

- Go to MySQL Workbench in MySQL Connections click + icon to add a new connection

- You can name your connection

- Click Test Connection if asked enter your MySQL server root password then it will show status whether connection is successful or not
then click ok

- In home page click to your new Connection to view MySQL database in Workbench

[Ref](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04)
