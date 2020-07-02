# How to set evironment variable in Ubuntu

**Note:** You need an environment variable, right?



Settting environment variable
```
echo "export RJ_ENV='this_is_my_env_variable'" > rj.env

source ./rj.env

python
	> import os;os.environ.get('RJ_ENV')
```

##### Ref :

  * [Askubuntu - How do I set environment variable](https://askubuntu.com/questions/730/how-do-i-set-environment-variables)
  * [Environment Variables](https://help.ubuntu.com/community/EnvironmentVariables)

