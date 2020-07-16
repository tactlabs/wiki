# Connecting to AWS EC2

**Note :** .pem file is required.Keep the .pem file inside a directory

Change the directory to the location of the private key file.

To ensure that your private key file isn't publicly viewable,use the chmod command

```
chmod 400 my-key-pair.pem
```

Connect to the server over ssh using the .pem file and EC2 instance's public DNS name.

SSH command to connect to the instance
```
ssh -i /path/my-key-pair.pem ec2-user@public_dns_name
```
**Adding a rule for inbound SSH traffic to the instance**

To enable network access to your instance, inbound traffic should be allowed for the instance.

1.Choose the security group

2.Edit the inbound rules to add the rule of type SSH and give the public IP address in the source and save
