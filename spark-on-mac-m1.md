### Java Installation
```
brew tap adoptopenjdk/openjdk
brew cask install adoptopenjdk11
brew install --cask adoptopenjdk11

verify:
java --version
javac --version
```

### JAVA_HOME setup
```
gedit ~/.zshrc
export JAVA_HOME=`/usr/libexec/java_home`
source ~/.zshrc
```


### Scala Installation
```
brew upgrade
brew install scala@2.13

verify:
scala -version
scalac -version
```


### SCALA_HOME setup
```
export SCALA_HOME="/opt/homebrew/opt/scala/idea"

verify:
echo $SCALA_HOME
```

### Spark Installation
```
brew install apache-spark

verify:
spark-shell


```


### SPARK_HOME setup
```
export SPARK_HOME="/opt/homebrew/Cellar/apache-spark/3.2.1/libexec"
export PYTHONPATH="$PYTHONPATH:$SPARK_HOME/python:$SPARK_HOME/python/lib"
export PATH="$PATH:$SPARK_HOME/bin"

verify:
echo $SPARK_HOME
```


# spylon-kernel setup
```
conda create -n py39spark -y python=3.9
conda activate py39spark
pip install jupyterlab
pip install spylon
pip install spylon-kernel
```

# Simple Spark with Scala on Spylon
```
jupyter lab

Open spylon kernel, type the following in a cell and run it

print("Hello World!")
```


Ref:
- [Installing Scala on Mac](https://www.freecodecamp.org/news/installing-scala-and-apache-spark-on-mac-os-837ae57d283f/)