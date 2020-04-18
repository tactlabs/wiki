# Docker Postgres Alpine Commands

**Note:** Postgres



Pull Postgres Alpine Image
```
docker pull postgres:11.7-alpine
```






Run the image as container
```
docker run --name pg117alpine -e POSTGRES_PASSWORD=root -p 5432:5432 -d postgres:11.7-alpine
```


To mount/store in your local machine (verified in Mac)
```
docker run --name pg117alpine -e POSTGRES_PASSWORD=root -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data -p 5432:5432 -d postgres:11.7-alpine
```




Get into the container
```
docker exec -it pg117alpine bash
```




Connect to DB
```
psql -U postgres
```


Show databases
```
\l
```





Show roles
```
\du
```





Get current database:
```
select current_database();
```





List tables
```
\dt
```


DB cred:
```
u: postgres
p: root (or empty)
```


### Connect on client like Table Plus:

Run these commands to add entries
```
SELECT CURRENT_DATABASE();

CREATE TABLE ONE (
    NAME INT 
);

INSERT INTO ONE (NAME) VALUES (1);
INSERT INTO ONE (NAME) VALUES (2);

SELECT * FROM ONE;
```




### How to verify from python file?
Just clone this repo and run select.py file
[Simple Read Postgres](https://github.com/rajacsp/simple-read-postgres)


### Credits
* [Credits](https://gist.github.com/rajasgs/95f5987f94e4389ab76262a61b402864)
* [Docker Postgres](https://hackernoon.com/dont-install-postgres-docker-pull-postgres-bee20e200198)
* [Postgres Create Table](http://www.postgresqltutorial.com/postgresql-create-table/)
* [Creating Usertable](https://medium.com/coding-blocks/creating-user-database-and-adding-access-on-postgresql-8bfcd2f4a91e)
* [Connect Docker Container](https://medium.com/@lvthillo/connect-from-local-machine-to-postgresql-docker-container-f785f00461a7)


