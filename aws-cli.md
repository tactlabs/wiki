/ [Home](index.md)

# AWS ClI commands 

### AWS CLI installation:


#### TLDR; version - Ubuntu
```
cd /tmp

curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip

sudo ./aws/install 
aws --version
```



#### TLDR; version - MacOS
```
sudo curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
sudo installer -pkg AWSCLIV2.pkg -target /

which aws
    You will see like this:
        /usr/local/bin/aws

aws --version
    You will see like this:
        aws-cli/2.9.8 Python/3.9.11 Darwin/21.6.0 exe/x86_64 prompt/off

if any issues, check log here:
/var/log/install.log


ref:
https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
```


``` 
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
```

### Unzipping the package:

```
unzip awscliv2.zip
```

### Checking the version:

```
sudo ./aws/install 

aws --version

``` 

### configure 

```
aws configure

```


### Expected output:

```
AWS Access Key ID []: <Paste access key>
AWS Secret Access Key []:<Paste Secret key>
Default region name []: <Enter the region>
Default output format []:json

```

