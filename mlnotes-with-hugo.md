# MLNotes with Hugo

**Note:** Create your ML Notes with Hugo Server



How to install Hugo in Ubuntu?
```
First uninstall hugo (if you have installed previously)
sudo apt-get remove hugo
sudo apt-get purge hugo

Install hugo
wget https://github.com/gohugoio/hugo/releases/download/v0.50/hugo_extended_0.50_Linux-64bit.deb && sudo apt install ./hugo_extended_0.50_Linux-64bit.deb

check version
hugo version

  	You should see something like this
	  Hugo Static Site Generator v0.55.2/extended darwin/amd64 BuildDate: unknown

Ref:
https://github.com/gohugoio/hugo/releases/tag/v0.50
https://gohugo.io/getting-started/installing/
```


How to install hugo in mac?
```
brew install hugo

check version:
hugo version

  	You should see something like this
	  Hugo Static Site Generator v0.55.2/extended darwin/amd64 BuildDate: unknown
```



Pre req:
```
pip install runipy
pip install jupyterlab
pip install jupyter
```

How to start?
```
runipy make.ipynb
hugo server -D
hugo
```

### Ref :

  * []()
