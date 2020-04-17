# Git Commands

**Note:** Git commands



Basic flow: (basis status check, add, commit, push)
```
git status
git add .
git commit -m "dc-00: comment"
git push
git diff *_client.html
git checkout -- abc.java
git commit filename
git diff --cached [filename]
git diff HEAD [filename]
```





Configure user details on Git
```
git config --global user.email "abc@gmail.com"
git config --global user.name "Your Name"
```




git cache / github password cache:
```
git config credential.helper store
```




reset a single file:
```
git checkout filename
```
Ref: 
[Revert a single file](http://www.norbauer.com/rails-consulting/notes/git-revert-reset-a-single-file.html)




git commit some files
[Commit only some files](http://stackoverflow.com/questions/7239333/how-do-i-commit-only-some-files)




end git diff
```
type q
```




revert last push
```
git reset --hard <revision_id_of_last_known_good_commit>
git push --force
```
[Rollback last push](http://stackoverflow.com/questions/6655052/is-there-a-way-to-rollback-my-last-push-to-git)




add all except a single file
```
git add .
git reset filename
```




Git logs:
```
git log
```




Git logs with limit
```
git log -n 2
```




Git previous logs one line
```
git log --pretty=oneline
```




Git stats
```
git log --stat
git log --stat -n 2
```




Git log for particular author
```
git log --author="rajacsp" -n 2
```




Git log graph
```
git log --graph --decorate --oneline
```
Ref:
* [View commit history](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)
* [Inspecting a repository](https://www.atlassian.com/git/tutorials/inspecting-a-repository)
* [Git status](https://git-scm.com/docs/git-status)




Revert all uncommitted changes including new files
Revert changes to modified files
```
git reset --hard
```




Remove all untracked files and directories. (`-f` is `force`, `-d` is `remove directories`)
```
git clean -fd
```




Undo a last add before commit
```
git reset
```




Revert a single file
```
git checkout filename
```
[Revert reset a single file](http://www.norbauer.com/rails-consulting/notes/git-revert-reset-a-single-file.html)




Git add all but ignore one file
```
git add -u
git reset -- filename.txt
```




revert one uncommitted file git
```
git checkout abc.php
```
[Revert a single file](http://www.norbauer.com/rails-consulting/notes/git-revert-reset-a-single-file.html)	




clone
```
git clone https://github.com/rajacsp/drivercheck
```




ignore class files git
```
/*.class in gitignore
```
[Ignore files in Git](http://stackoverflow.com/questions/4308610/how-to-ignore-certain-files-in-git)



Short log
```
git shortlog -s 
```
will get all users' commit by count




Total commits count in Head, Branch and All
```
git rev-list --count HEAD
	- will get the total commits in head
git rev-list --all --count
	- will get the total commits in all
git rev-list --count origin/K-develop
```
[Get Git commit count](https://stackoverflow.com/questions/677436/how-do-i-get-the-git-commit-count)




Caching your GitHub password in Git:
[Cache Password](https://help.github.com/articles/caching-your-github-password-in-git/)



Take branch
```
git checkout -b branch_name
```
[Create a new branch](https://github.com/Kunena/Kunena-Forum/wiki/Create-a-new-branch-with-git-and-manage-branches)




Clone the right branch
```
git clone abc.git branch abc_branch
```




Merge branch with Master (puhsing branch's code into master): verified on Feb 10, 2017
```
go inside master folder:
git pull origin master
git merge branch_name
git push origin master
```




if conflict occurs, fix them using method below:
```
 <<<<<<< HEAD - old code start
 =======      - old code end 
 >>>>>>> plainreport - new code end
```
	How to fix Git merge conflicts:
	[Fix Git Merge](https://www.youtube.com/watch?v=g8BRcB9NLp4)




```
git checkout master
git pull origin master
git merge branch_name
git push origin master
```
[Merge](http://stackoverflow.com/questions/5601931/best-and-safest-way-to-merge-a-git-branch-into-master)




```
git pull origin K-develop
git merge origin/K-develop
git push
```




Find Git Version in cmd
```
git --version
git version 2.16.2.windows.1
```
if you get "command not found", it simply means that you haven't installed
[Git Version](http://superuser.com/questions/347728/terminal-command-to-find-what-version-of-git-i-have-installed)



Pull Request:
[pull-request](https://help.github.com/articles/about-pull-requests/


```
Git Cherry pick

git cherry-pick <commit-id>
```
* [Cherry pick](https://mirrors.edge.kernel.org/pub/software/scm/git/docs/git-cherry-pick.html)
* [Merge](https://stackoverflow.com/questions/881092/how-to-merge-a-specific-commit-in-git)
* [Pull Alll commit](https://stackoverflow.com/questions/880957/pull-all-commits-from-a-branch-push-specified-commits-to-another/881014#881014)
* [pull reqeust](http://markosullivan.ca/how-to-handle-a-pull-request-from-github/)




Rewrite old history in GIT
```
java -jar c:/bfg/bfg-1.13.0.jar --delete-file *.mp3 pythonsamples.git
java -jar c:/bfg/bfg-1.13.0.jar --strip-blobs-bigger-than 30M pythonsamples.git
cd pythonsamples.git
git reflog expire --expire=now --all && git gc --prune=now --aggressive
```
[Bfg cleaner](https://rtyley.github.io/bfg-repo-cleaner/#usage)




Rename previous commit
```
git commit --amend -m "TACT-436: Script alignment made"
```




change commit message after git push
```
git commit --amend -m "Message"
git push --force-with-lease
```
[Change git commit](https://stackoverflow.com/questions/8981194/changing-git-commit-message-after-push-given-that-no-one-pulled-from-remote)


OR


```
git rebase -i eb5661a8e4de761d2af79c5ecbdbc875c34481fa
```
[Edit commit message](https://superuser.com/questions/751699/is-there-a-way-to-edit-a-commit-message-in-github/751909)



Stash existing changes
```
git stash     (will stash your existing changes)
git pull      (pull all of your new changes from central repository)
git stash apply (bring back your old changes on top of new code)
```
[Stashing](https://git-scm.com/book/en/v1/Git-Tools-Stashing)





View stash files
```
git stash show
```
* [Preview Stash content](https://stackoverflow.com/questions/3573623/is-it-possible-to-preview-stash-contents-in-git)

* [Git credentials](https://stackoverflow.com/questions/11693074/git-credential-cache-is-not-a-git-command)




Delete a branch
```
git push -d <remote_name> <branch_name>
git branch -d <branch_name>

delete multiple branches:
git push -d <remote_name> <branch_name_1> <branch_name_2>
```
* [Delete Git branch](https://stackoverflow.com/questions/2003505/how-do-i-delete-a-git-branch-both-locally-and-remotely)
* [Delete multiple branch](https://stackoverflow.com/questions/3670355/can-you-delete-multiple-branches-in-one-command-with-git)



Git Tutorial:
[Git Fetch](https://www.atlassian.com/git/tutorials/syncing/git-fetch)

git cheat sheet:
[Git Cheat sheet](https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf)

git commands:
[Git commands](https://www.siteground.com/tutorials/git/commands.htm)

[Setting up a repo](https://www.atlassian.com/git/tutorials/setting-up-a-repository)

more:
[Saving changes](https://www.atlassian.com/git/tutorials/saving-changes)


Copy Repository with history:
[Copying a full git repo](https://developer.atlassian.com/blog/2016/01/totw-copying-a-full-git-repo/)


```
git status -uno
```


