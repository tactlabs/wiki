# MySQL

**Note:** TBW



Run MySQL container
```
docker pull mysql

docker run -d --name=mysql1 -e MYSQL_ROOT_PASSWORD=’mypassword’ -v /storage/mysql1/mysql-datadir:/var/lib/mysql mysql

docker run -d --name=mysql2 -e MYSQL_ROOT_PASSWORD=’mypassword’ -v /storage/mysql2/mysql-datadir:/var/lib/mysql mysql
```

# Credits :

  * [Mysql Docker]([file](https://severalnines.com/blog/mysql-docker-building-container-image))
