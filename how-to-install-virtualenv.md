# How to install Virtualenv

**Note:** about virtualenv



Install virtualenv
```
pip install virtualenv
```


Create environment
```
virtualenv --python python3 py3
```


Access the created environment
```
source py3/bin/activate
```

How to deactivate
```
deactivate
```

How to freeze your libraries into requirements.txt
```
pip freeze > requirements.txt
```

How to install requirments
```
pip install -r requirements.txt
```