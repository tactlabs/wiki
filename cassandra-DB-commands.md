/ [Home](index.md)

# How to setup Cassandra with Docker 

### Why use Apache Cassandra ? 
Apache Cassandra is an open source, distributed, wide-column store, NoSQL database which delivers always-on availability 

#### Prerequisites 

Having Docker installed on your machine is necessary to try out provisioning Cassandra container.

```
sudo apt install docker.io
sudo apt install docker-compose
```
#### Docker version 

```
docker -v
docker-compose -v
```

```
docker run \
    --name cassandra \
    -p 7000:7000 \
    -p 9042:9042 \
    -v clocal:/bitnami \
    -d bitnami/cassandra:latest
```

```
docker logs -f cassandra
```

```
docker stop cassandra
```

```
docker rm cassandra
```

```
docker-compose config --services
```

```
docker exec -it cassandratest-cassandra-1 bash
```

```
ls -ltrs
```

```
/opt/bitnami/cassandra/bin/cqlsh -u cassandra -p cassandra
```

```
CREATE KEYSPACE IF NOT EXISTS meme
  WITH REPLICATION = {
   'class' : 'SimpleStrategy',
   'replication_factor' : 1
  };
  
  DESCRIBE keyspaces;

use meme;
```

```
DROP TABLE IF EXISTS meme.meme_name;
```

```
CREATE TABLE meme.meme_name (
  id int PRIMARY KEY,
  movie text,
  dialogue text,
 
);
```

```
INSERT INTO meme.meme_name (id, movie, dialogue) VALUES(1, 'Winner', 'Athu pona maasam ,naan sonnathu entha maasam.');
INSERT INTO meme.meme_name (id, movie, dialogue) VALUES(2, 'Thailainagaram', 'Yey.Enna vechu comedy geemedy oonum pannaliye!');
INSERT INTO meme.meme_name (id, movie, dialogue) VALUES(3, 'Friends', 'Anniyae pudunga vaenam');
```

```
SELECT * from meme.meme_name;
```


