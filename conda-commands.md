# Conda Commands

**Note:** notes



Create Conda environment
```
conda create -n pyone
conda activate pyone
conda deactivate pyone
```

Create an environment with specific python version
```
conda create -y python=3.6 --name py36az_jupyter
conda activate py36az_jupyter
conda deactivate
```

Conda Py27
```
conda create -n py27 -y python=2.7
conda activate py27
conda deactivate
```


How to view all environments
```
conda info --envs

or

conda env list

or

pip -V

```



# Sources :

  * [Conda]([file](https://salishsea-meopar-docs.readthedocs.io/en/latest/work_env/python3_conda_environment.html))
  * [](https://stackoverflow.com/questions/1871549/determine-if-python-is-running-inside-virtualenv)
  * [](https://stackoverflow.com/questions/122327/how-do-i-find-the-location-of-my-python-site-packages-directory)
