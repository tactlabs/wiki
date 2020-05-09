# Gush

**Note:** quick git push for one-way commits


Create a gush file in your desired location and create a file
```
cd /Users/myname/d/gitmagic
touch gu.sh
```


Add these into gu.sh file
```
git add .

git commit -m "Updates for $(date +%F)"

git push
```

Change mod
```
chmode u+x gu.sh
```


Go to bashrc / bash_profile
```
sudo gedit ~/.bash_profile

or

sudo vi ~/.bash_profile

or

sudo vi ~/.bashrc
```


Add this alias in your bash
```
alias gush="/Users/myname/d/gitmagic/gu.sh"
```

```
source ~/.bashrc

or

source ~/.bash_profile
```

Go to your desired repo and type this
```
gush
```

#### Caution:
Remember, gush file helps only on one-way commits like error_logs, daily_logs. When you work on big projects, please try not to use gush file