# HADOOP SETUP

## JDK ver8 installation:
```
sudo apt install openjdk-8-jdk
sudo apt install default-jre default-jdk
```

## verification:
```
java --version
```

## Hadoop installation:
```
wget https://mirrors.estointernet.in/apache/hadoop/common/hadoop-3.3.1/hadoop-3.3.1.tar.gz
tar -zxvf hadoop-3.3.1.tar.gz
```

sudo gedit ~/.zshrc

Add the below code & make sure the path is right:

export JAVA_HOME=/usr/lib/jvm/java-1.11.0-openjdk-amd64
export HADOOP_HOME=/home/vedha/softwares/apache/hadoop-3.3.1
export HADOOP_INSTALL=$HADOOP_HOME
export HADOOP_MAPRED_HOME=$HADOOP_HOME
export HADOOP_COMMON_HOME=$HADOOP_HOME
export HADOOP_HDFS_HOME=$HADOOP_HOME
export YARN_HOME=$HADOOP_HOME
export PATH=$PATH:$HADOOP_HOME/sbin:$HADOOP_HOME/bin
export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native
export HADOOP_OPTS="-Djava.library.path=$HADOOP_HOME/lib"

```
cd hadoop-3.3.1/etc/hadoop/ 
```

Open core-site.xml in gedit and paste the following inside the configuration headers:
```
<property>
    <name>fs.defaultFS</name>
    <value>hdfs://localhost:9000</value>
</property>
```


Open hdfs-site.xml in gedit and paste the following inside the configuration headers:
```
<property>
    <name>dfs.replication</name>
    <value>1</value>
</property>
```

Please make sure you have an existing public SSH key:
```
cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
chmod 0600 ~/.ssh/authorized_keys
```

## Configuring Hadoop:
```
hdfs namenode -format
start-all.sh
```

If connection to port 22 localhost fails, run the following:
```
sudo apt-get remove openssh-client openssh-server
sudo apt-get install openssh-client openssh-server
```
```
cd $HADOOP_HOME/etc/hadoop

gedit hadoop-env.sh 
```

Add this in:
```
export JAVA_HOME=/usr/lib/jvm/java-1.11.0-openjdk-amd64
```

Try:
```
start-all.sh
```

## Verification

```
sudo apt install net-tools
netstat -tulpn | grep LISTEN
```

See if there's a process on port 9000

Then go to:

http://localhost:9870/