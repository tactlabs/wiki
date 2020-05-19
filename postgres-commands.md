# Tempalte

**Note:** tbw



How to connect localhost DB?
```
psql -U postgres -h localhost -p 5432 <db_name>
```


How to connect to remote DB from command?
```
psql -U postgres -h <remote_db_end_point> -p 5432 <remote_db_name>
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

#### Ref :

  * []()
