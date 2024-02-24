/ [Home](index.md)

# AWS Commands

**Note:** aws commands



region and codes
* [AWS Region](https://awsregion.info/)



configure my region?
```
aws configure
```





configure my region?
```
aws configure
	
AWS Access Key ID [****************CQU6]:
AWS Secret Access Key [****************dmOQ]:
Default region name [ap-south-1]:
Default output format [json]:
```





aws config location
```
cat ~/.aws/config
```




Get my CLI version
```
aws --version
aws-cli/2.0.4 Python/3.7.4 Darwin/17.7.0 botocore/2.0.0dev8
aws-cli/1.16.260 Python/2.7.16 Darwin/17.7.0 botocore/1.12.250
```




How to uninstall AWS and install updated version?
```
which aws
    
/usr/local/bin/aws

ls -l /usr/local/bin/aws
```




Uninstall aws
```
sudo rm /usr/local/bin/aws
sudo rm /usr/local/bin/aws_completer
sudo rm -rf /usr/local/aws-cli
```
* [AWS Cli remove](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-mac.html#cliv2-mac-remove)
* [AWS Install Confirm](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-mac.html#cliv2-mac-install-confirm)

    




How to install AWS?
```
curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
sudo installer -pkg AWSCLIV2.pkg -target /

verify
aws-cli/2.0.4 Python/3.7.4 Darwin/17.7.0 botocore/2.0.0dev8
```

*[AWS Cli Remove](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-mac.html#cliv2-mac-remove)





Get My region
```
aws configure get region
```





```
aws ecr get-login --region us-west-2 --no-include-email
```





```
aws ecr get-login --region ca-central-1 --no-include-email
```



Create VPCs
```
aws ec2 create-default-vpc
```



Describe VPCs
```
aws ec2 describe-vpcs
```


Create task-definition:
```
aws ecs register-task-definition --cli-input-json file://task-definition.json
```


Create security Group:
```
aws ec2 authorize-security-group-ingress --group-name circleci-flask-demo-sg --protocol tcp --port 1-65535 --source-group circleci-flask-demo-elb-sg
```



```
aws ecs register-task-definition --cli-input-json file://task-definition.json
```



```
aws ec2 describe-regions
```



```
aws ecs describe-task-definition --task-definition dev-kde20-rabbitmq:2
```
*[Describe Task Definition](https://docs.aws.amazon.com/cli/latest/reference/ecs/describe-task-definition.html)




```
aws ecr describe-repositories
```




```
aws ecr describe-repositories --repository-name 943339394358.dkr.ecr.us-west-2.amazonaws.com/dev/kde2.0-api
```



```
aws ecr describe-images --repository-name amazonlinux
```
* []()
https://docs.aws.amazon.com/AmazonECR/latest/userguide/docker-pull-ecr-image.html


```
aws configure get region
```
*[Find the current region](https://stackoverflow.com/questions/31331788/using-aws-cli-what-is-best-way-to-determine-the-current-region)



Get all ECS clusters
```
aws ecs list-clusters

{
    "clusterArns": [
        "arn:aws:ecs:ap-south-1:943339394358:cluster/reverser1"
    ]
}
```
https://docs.aws.amazon.com/cli/latest/reference/ecs/list-clusters.html


```
aws ecs list-task-definitions

{
    "taskDefinitionArns": []
}
```
https://docs.aws.amazon.com/cli/latest/reference/ecs/list-task-definitions.html



```
aws ecs list-services --cluster MyCluster

aws ecs list-services --cluster reverser1

{
    "serviceArns": [
        "arn:aws:ecs:ap-south-1:943339394358:service/reverser-backend-service1"
    ]
}
```
https://docs.aws.amazon.com/cli/latest/reference/ecs/list-services.html



Delete AWS ECS cluster:
```
aws ecs delete-cluster help

aws ecs delete-cluster --cluster reverser1

{
    "cluster": {
        "clusterArn": "arn:aws:ecs:ap-south-1:NNNN:cluster/reverser1",
        "clusterName": "reverser1",
        "status": "DEPROVISIONING",
        "registeredContainerInstancesCount": 0,
        "runningTasksCount": 0,
        "pendingTasksCount": 0,
        "activeServicesCount": 0,
        "statistics": [],
        "tags": [],
        "settings": [
            {
                "name": "containerInsights",
                "value": "enabled"
            }
        ],
        "capacityProviders": [
            "FARGATE_SPOT",
            "FARGATE"
        ],
        "defaultCapacityProviderStrategy": [],
        "attachments": [],
        "attachmentsStatus": "UPDATE_IN_PROGRESS"
    }
}
```


Delete AWS EKS cluster
```
aws eks delete-cluster --name reverser1
```
https://docs.aws.amazon.com/cli/latest/reference/eks/delete-cluster.html



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```



```

```

#### Ref :

  * [ECR](https://docs.aws.amazon.com/cli/latest/reference/ecr/index.html)
  * [ECR](https://docs.aws.amazon.com/cli/latest/reference/ecs/index.html)
