/ [Home](index.md)

# AWS Cloudwatch:
1.1 Launch the EC2 instance\
1.2 Create IAM role with CloudWatchAgentServerPolicy   
1.3 Attach the create IAM role to the EC2 instance  
1.4 SSH into the instance

## Install cloudwatch agent
Ref : https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/download-cloudwatch-agent-commandline.html

2. 
```
   wget https://s3.amazonaws.com/amazoncloudwatch-agent/ubuntu/amd64/latest/amazon-cloudwatch-agent.deb
```


3. 
```
   sudo dpkg -i -E ./amazon-cloudwatch-agent.deb
```

## Install AWS CLI
4. 
```
   "https://awscli.amazonaws.com/awscli-exe-linux-x86_64-2.0.30.zip" -o "awscliv2.zip" 
```
5. 
```
   sudo apt-get install unzip
```
6. 
``` 
   unzip awscliv2.zip 
```
7. 
``` 
   sudo ./aws/install 
```

## Set up AWS CLI
8. 
``` 
sudo aws configure 
```

9.  
``` 
sudo dpkg -i amazon-cloudwatch-agent.deb 
```
10. 
```
 cd /opt/aws/amazon-cloudwatch-agent/etc/
```

## Configure CloudWatch Agent
11. 
``` 
    sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-config-wizard 
```
    
## Cloudwatch Configuration
```
================================================================
= Welcome to the Amazon CloudWatch Agent Configuration Manager =
=                                                              =
= CloudWatch Agent allows you to collect metrics and logs from =
= your host and send them to CloudWatch. Additional CloudWatch =
= charges may apply.                                           =
================================================================
On which OS are you planning to use the agent?
1. linux
2. windows
3. darwin
default choice: [1]:
1
Trying to fetch the default region based on ec2 metadata...
Are you using EC2 or On-Premises hosts?
1. EC2
2. On-Premises
default choice: [1]:
1
Which user are you planning to run the agent?
1. root
2. cwagent
3. others
default choice: [1]:
1
Do you want to turn on StatsD daemon?
1. yes
2. no
default choice: [1]:
2
Do you want to monitor metrics from CollectD? WARNING: CollectD must be installed or the Agent will fail to start
1. yes
2. no
default choice: [1]:
2
Do you want to monitor any host metrics? e.g. CPU, memory, etc.
1. yes
2. no
default choice: [1]:
1
Do you want to monitor cpu metrics per core?
1. yes
2. no
default choice: [1]:
1
Do you want to add ec2 dimensions (ImageId, InstanceId, InstanceType, AutoScalingGroupName) into all of your metrics if the info is available?
1. yes
2. no
default choice: [1]:
1
Do you want to aggregate ec2 dimensions (InstanceId)?
1. yes
2. no
default choice: [1]:
2
Would you like to collect your metrics at high resolution (sub-minute resolution)? This enables sub-minute resolution for all metrics, but you can customize for specific metrics in the output json file.
1. 1s
2. 10s
3. 30s
4. 60s
default choice: [4]:
4
Which default metrics config do you want?
1. Basic
2. Standard
3. Advanced
4. None
default choice: [1]:
1
Current config as follows:
{
	"agent": {
		"metrics_collection_interval": 60,
		"run_as_user": "root"
	},
	"metrics": {
		"append_dimensions": {
			"AutoScalingGroupName": "${aws:AutoScalingGroupName}",
			"ImageId": "${aws:ImageId}",
			"InstanceId": "${aws:InstanceId}",
			"InstanceType": "${aws:InstanceType}"
		},
		"metrics_collected": {
			"disk": {
				"measurement": [
					"used_percent"
				],
				"metrics_collection_interval": 60,
				"resources": [
					"*"
				]
			},
			"mem": {
				"measurement": [
					"mem_used_percent"
				],
				"metrics_collection_interval": 60
			}
		}
	}
}
Are you satisfied with the above config? Note: it can be manually customized after the wizard completes to add additional items.
1. yes
2. no
default choice: [1]:
1
Do you have any existing CloudWatch Log Agent (http://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/AgentReference.html) configuration file to import for migration?
1. yes
2. no
default choice: [2]:
2
Do you want to monitor any log files?
1. yes
2. no
default choice: [1]:
2
Saved config file to /opt/aws/amazon-cloudwatch-agent/bin/config.json successfully.
Current config as follows:
{
	"agent": {
		"metrics_collection_interval": 60,
		"run_as_user": "root"
	},
	"metrics": {
		"append_dimensions": {
			"AutoScalingGroupName": "${aws:AutoScalingGroupName}",
			"ImageId": "${aws:ImageId}",
			"InstanceId": "${aws:InstanceId}",
			"InstanceType": "${aws:InstanceType}"
		},
		"metrics_collected": {
			"disk": {
				"measurement": [
					"used_percent"
				],
				"metrics_collection_interval": 60,
				"resources": [
					"*"
				]
			},
			"mem": {
				"measurement": [
					"mem_used_percent"
				],
				"metrics_collection_interval": 60
			}
		}
	}
}
Please check the above content of the config.
The config file is also located at /opt/aws/amazon-cloudwatch-agent/bin/config.json.
Edit it manually if needed.
Do you want to store the config in the SSM parameter store?
1. yes
2. no
default choice: [1]:
2
Program exits now.
```


## Run CloudWatch Agent
12.
``` 
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a fetch-config -s -m ec2 -c file:/opt/aws/amazon-cloudwatch-agent/bin/config.json -s
```


## Verify Status of CloudWatch Agent

13. 
```
    sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a status
```