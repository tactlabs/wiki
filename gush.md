/ [Home](index.md)

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
chmod u+x gu.sh
```

gu.sh 3.0:
```
git_push_with_chatgpt()
{
  
    git pull

    # sleep 3 seconds
    sleep 2

    git add .

    # path to the file
    file_path="/Users/fpr11/tact/gitmagic/gcommit-chatgpt.txt"

    # using wc command to count number of lines
    number_of_lines=`wc -l < $file_path`

    # echo $((number_of_lines))

    rando_number=`shuf -i 1-$((number_of_lines)) -n 1`

    # echo $rando_number

    line=`sed $((rando_number))!d $file_path`
    # echo $line

    git commit -m "$line: Updates for $(date +%F)"

    git push

}

git_push_with_vanilla()
{
    echo "calling Vanilla"
    
    git add .

    git commit -m "Updates for $(date +%F)"

    git push
}

# Testing
# git_push_with_chatgpt
# git_push_with_vanilla

if [ -n "$1" ] ; then
    git_push_with_vanilla
else
    git_push_with_chatgpt
fi
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

##### Gush Demo
[Gush Demo](https://www.loom.com/share/97a5d65c0d44493e8cf7bfce07f61ed0)

#### Caution:
Remember, gush file helps only on one-way commits like error_logs, daily_logs. When you work on big projects, please try not to use gush file