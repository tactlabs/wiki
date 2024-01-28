/ [Home](index.md)

## Venv


### Setup Python3
```
sudo apt update
sudo apt install python3

Ref:
https://phoenixnap.com/kb/how-to-install-python-3-ubuntu
https://linuxize.com/post/how-to-install-python-on-ubuntu-22-04/
```


### Setup venv
```
python3 -m venv venv3

source venv3/bin/activate

deactivate

Ref:
https://linuxize.com/post/how-to-install-python-on-ubuntu-22-04/
```


### Setup python-venv
```
sudo apt install python3.9-venv
mkdir ~/.venvs
python3.9 -m venv ~/.venvs/venv39

source ~/.venvs/venv39/bin/activate

deactivate

Ref:
https://stackoverflow.com/questions/70422866/how-to-create-a-venv-with-a-different-python-version
```