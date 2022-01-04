/ [Home](index.md)

# Jupyter Cheatsheet

**Note:** 

How install Jupyter lab?
```
conda activate <yourenv>
pip install jupyterlab
jupyter lab
```




Change input to Markdown
```
Escape + M
```






Change input to Code
```
Escape + Y
```





Delete current cell
```
D + D
```





How to merge cells?
```
(escape first)
Shift + Down/Up 
and then
Shift + M
```





How to curl?
```
!curl <whatever>
```





How to install pip
```
!pip install pydataset
```






```
%matplotlib inline
```






```
%run ./simple-math.ipynb
```





How to use variable across multiple ipynb files?
```
%store <varname>
%store -r <varname>
```





Show variables in the global scope
```
%who  (will show all variables)
%who str (will show only str types)
%who bool (will show only boolean types)
```



[Credits](https://www.dataquest.io/blog/jupyter-notebook-tips-tricks-shortcuts/)