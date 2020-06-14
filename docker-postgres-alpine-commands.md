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



show size of the database
```
\l+
```



Show roles
```
\du
```



switch database
```
\c db_name
```



show schema table
```
\dt+
```



Get current database:
```
select current_database();

or 

\c

or

SELECT * FROM current_catalog;
```





List tables in the database
```
\dt
```



show table with size
```
\dt+
```



show specific schema tables
```
\dt schema_name.* 
```


specific tble
```
\d table_name
```


Get table details from specific schema:
```
select * from  pg_catalog.pg_tables where schemaname != 'flcity' and schemaname != 'pg_catalog';
```



quit database
```
\q
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

#### Python to connect to DB
```
import psycopg2 

def startpy():

    connection = None

    try:
        connection = psycopg2.connect(user = "postgres",
                                    password = "root",
                                    host = "localhost",
                                    port = "5432",
                                    database = "postgres")

        cursor = connection.cursor()
        
        # Print PostgreSQL Connection properties
        print ( connection.get_dsn_parameters(),"\n")
        
        # Print PostgreSQL version
        cursor.execute("SELECT version();")
        record = cursor.fetchone()
        print("You are connected to - ", record,"\n")
    except (Exception, psycopg2.Error) as error :
        print ("Error while connecting to PostgreSQL", error)
    finally:
        #closing database connection.
            if(connection):
                cursor.close()
                connection.close()
                print("PostgreSQL connection is closed")


if __name__ == '__main__':
    startpy()
```


### How to verify from python file?
Just clone this repo and run select.py file
[Simple Read Postgres](https://github.com/rajacsp/simple-read-postgres)


### Credits
* [Gist GitHub](https://gist.github.com/rajasgs/95f5987f94e4389ab76262a61b402864)
* [Docker Postgres](https://hackernoon.com/dont-install-postgres-docker-pull-postgres-bee20e200198)
* [Postgres Create Table](http://www.postgresqltutorial.com/postgresql-create-table/)
* [Creating Usertable](https://medium.com/coding-blocks/creating-user-database-and-adding-access-on-postgresql-8bfcd2f4a91e)
* [Connect Docker Container](https://medium.com/@lvthillo/connect-from-local-machine-to-postgresql-docker-container-f785f00461a7)


