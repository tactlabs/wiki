# Hugo Commands

**Note:** Hugo


Pre req:
```
pip install runipy
```


How to start?
```
runipy make.ipynb
hugo server -D
hugo
```

Code notes
```
1. Run `make.ipynb`
2. Run `hugo` in the `notes` folder
3. Run `git add -A`
4. Run `git commit -m "commit message`
5. Run `git push`

ipython nbconvert --to python make.ipynb
python make
```

```
hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>
```


Hugo Basics
```
hugo new site my-site

hugo new privacy.md
hugo server -w -D
curl -L localhost:1313/privacy/

hugo server -D 
hugo server


public Jupyter with Hugo
https://github.com/knowsuchagency/hugo_jupyter

Hugo and Jupyter
https://www.youtube.com/watch?v=LtdyM4hP85I&feature=youtu.be
```


Hugo Base
```
https://github.com/teamtact/hugobase

published site:
https://teamtact.github.io/hugobase/
```

Hugo - How to start?
```
hugo how to start:
runipy make.ipynb
hugo server -D
	http://localhost:1313/mlnotes/
hugo

Fix the recompilation issue
```

#### Ref :

  * [Hugo getting started](https://gohugo.io/getting-started/quick-start/)
  * [How to push to website in Hugo](https://gohugo.io/hosting-and-deployment/hosting-on-github/)
