# MongoDB Installation

**Note:** notes



MongoDB - Mac
```
brew tap mongodb/brew
brew install mongodb-community@4.2
```

set db path for mongodb:
```
sudo vi ~/.bash_profile

  then add these two lines

  # MongoDB Aliases
  alias mongod="mongod --config /usr/local/etc/mongod.conf --fork"

  then
  source ~/.bash_profile
```
[ref](https://stackoverflow.com/questions/28771558/set-dbpath-in-mongodb-homebrew-installed-mac-os)


mongodb conf:
```
/usr/local/etc/mongod.conf
```

How to verify Mongodb?

option 1:
```
ps aux | grep -v grep | grep mongod

  you will see something like this
  rajacsp          54519   0.3  0.3  5528896  22424   ??  S     2:42am   0:02.42 mongod --config /usr/local/etc/mongod.conf --fork
```


option1:
```
ps -ef | grep mongod | grep -v grep | wc -l | tr -d ' '
  you will 1 or 0
  1 - running
  0 - not running
```
[ref](https://stackoverflow.com/questions/31561098/how-to-check-if-mongo-db-is-running-on-mac)

option 2:
just type mongo and you will see like this:
```
mongo
MongoDB shell version v4.2.6
connecting to: mongodb://127.0.0.1:27017/?compressors=disabled&gssapiServiceName=mongodb
Implicit session: session { "id" : UUID("976f8c25-df92-4c1a-bd0a-d62179530291") }
MongoDB server version: 4.2.6
Welcome to the MongoDB shell.
For interactive help, type "help".
For more comprehensive documentation, see
	http://docs.mongodb.org/
Questions? Try the support group
	http://groups.google.com/group/mongodb-user
Server has startup warnings:
2020-04-26T02:42:55.735-0400 I  CONTROL  [initandlisten]
2020-04-26T02:42:55.737-0400 I  CONTROL  [initandlisten] ** WARNING: Access control is not enabled for the database.
2020-04-26T02:42:55.742-0400 I  CONTROL  [initandlisten] **          Read and write access to data and configuration is unrestricted.
2020-04-26T02:42:55.744-0400 I  CONTROL  [initandlisten]
2020-04-26T02:42:55.746-0400 I  CONTROL  [initandlisten]
2020-04-26T02:42:55.747-0400 I  CONTROL  [initandlisten] ** WARNING: soft rlimits too low. Number of files is 256, should be at least 1000
---
Enable MongoDB's free cloud-based monitoring service, which will then receive and display
metrics about your deployment (disk utilization, CPU, operation statistics, etc).

The monitoring data will be available on a MongoDB website with a unique URL accessible to you
and anyone you share the URL with. MongoDB may use this information to make product
improvements and to suggest MongoDB products and deployment options to you.

To enable free monitoring, run the following command: db.enableFreeMonitoring()
To permanently disable this reminder, run the following command: db.disableFreeMonitoring()
```

[ref](https://stackoverflow.com/questions/31561098/how-to-check-if-mongo-db-is-running-on-mac)

# Ref :

  * [Ref](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/)
