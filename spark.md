# Java Installation

```
sudo apt install openjdk-11-jdk-headless
java --version
javac --version
```

# Java location setup

```
readlink -f $(which java)
```
Save the location
```
gedit ~/.zshrc
export JAVA_HOME=/usr/lib/jvm/java-13-openjdk-amd64
source ~/.zshrc
```
Use the saved location here

# Scala Installation

```
sudo apt-get install scala
scala -version
```

# Spark Installation

```
wget https://downloads.apache.org/spark/spark-3.2.1/spark-3.2.1-bin-hadoop3.2.tgz
```
If this doesn't work, go to [Apache Spark](https://medium.com/r/?url=https%3A%2F%2Fspark.apache.org%2Fdownloads.html) download page and get the latest version
```
tar xvf spark-3.2.1-bin-hadoop3.2.tgz
sudo mv spark-3.2.1-bin-hadoop3.2 /opt/spark
```
Extract and move it to /opt/spark directory

# Configure spark environment

```
gedit ~/.profile
```
Copy and paste the following commands in the gedit window and save the file
```
export SPARK_HOME=/opt/spark
export PATH=$PATH:$SPARK_HOME/bin:$SPARK_HOME/sbin
export PYSPARK_PYTHON=/usr/bin/python3
```
Now use the source command 
```
source ~/.profile
```
Run the spark shell to confirm the installation
```
spark-shell
```

# spylon-kernel setup

```
conda create -n py39spark -y python=3.9
conda activate py39spark
pip install jupyterlab
pip install spylon
pip install spylon-kernel
```

# Hello World

Open jupyter lab
```
jupyter lab
```
Open spylon kernel, type the following in a cell and run it
```
print("Hello World!")
```