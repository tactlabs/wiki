# Influx DB Commands

**Note:** Got some measurements for us?


Basic commands
```
docker run -p 8086:8086 \
      -v influxdb:/var/lib/influxdb \
      influxdb
	  
docker run -p 8086:8086 -v influxdb:/var/lib/influxdb influxdb
	  
curl -G http://localhost:8086/query --data-urlencode "q=CREATE DATABASE rjdb"

curl -G http://localhost:8086/query --data-urlencode "q=CREATE DATABASE rjdb"

curl -i -XPOST 'http://localhost:8086/write?db=mydb' --data-binary 'cpu_load_short,host=server01,region=us-west value=0.64 1434055562000000000'
```

commands:
```
create database kaipulla
show databases
use kaipulla
SHOW MEASUREMENTS
INSERT cpu, host = serverA value=10
select * from cpu
```

### Ref :

  * [InfluxDB](https://hub.docker.com/_/influxdb/)
  * [Writing and Querying in InfluxDB](https://pythontic.com/database/influxdb/writing_and_querying)

