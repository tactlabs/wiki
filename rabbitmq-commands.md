/ [Home](index.md)

# RabbitMQ

**Note:** notes


#### How to install RabbitMQ Docker
```
docker run -d -p 15672:15672 --hostname my-rabbit --name some-rabbit rabbitmq:3
docker exec some-rabbit rabbitmq-plugins enable rabbitmq_management

Check localhost
http://localhost:15672/
guest/guest
```

##### Source:
[RabbitMQ Contaier Port Issue](https://github.com/docker-library/rabbitmq/issues/45)


#### How to install on Mac?
```
brew update
brew install rabbitmq
export PATH=$PATH:/usr/local/opt/rabbitmq/sbin

rabbitmq-server
```

[Install Homebrew](https://www.rabbitmq.com/install-homebrew.html)
[How to Install RabbitMQ on Mac](https://www.dyclassroom.com/howto-mac/how-to-install-rabbitmq-on-mac-using-homebrew)
