# Git learning stuff

This isn't really a software repo, more of just a way for me to learn more about git and github, It corresponds to a course on Udemy, which you can find [here](https://www.udemy.com/github-ultimate/).

---

## Git commands I've learned thus far

### git clone example.com/something.git

- Clone a git repo, going from github to your computer. 

### git commit

- commit changes, but your editor will open and you should write a commit message

### git commit -m

- commit with a message specified at the command line, in quotes

### git add .

- add everything in the current directory

### git add -A

- add everything

### git rm filename

- remove a file from the repo (key distinction: deleting file locally is not the same thing)

### git add filename

- add a file to be tracked by the repo

### git status

- shows status of file modifications, new files, deleted files, etc -- stuff before a commit and push

### git init

- creates an empty git repository

### git log

- shows a log

### git show

- shows info

### git push

- pushes your changes to github (or whatever)

### git pull

- gets new changes from the repo

### git ls-files

- like ls but only shows the files tracked by git, not untracked stuff

### git commit -am "commit message"

- adding -a will automatically add modified files

### Backing out of a bad change

- git reset HEAD example.txt
- git checkout -- example.txt
- The above two commands will revert example.txt back to the previous commit version as specified in HEAD

### git help 

- git help specific-command (example: git help log)
- kind of like linux man pages, but for git stuff

### list all global configurations in git

- git config --global --list

### create an alias, not unlike bash:

- git config --global alias.hist "log --oneline --graph --decorate --all"

### the equivalent to a history command, shows compact and useful info about the repo's history:

- git log --oneline --graph --decorate --all

### only get history for a single file

- git hist -- filename.txt
- OR:
- git log --oneline --graph --decorate --all filename.txt
- not having the additional filename arg will just show the whole repo history, whereas
- including the filename will mean it'll only show the history for that particular file

### git mv original-name.txt new-name.txt

- this basically renames a file

### .gitignore file

- A hidden file (because of the dot) that will ignore certain files. 
- One thing per line. You can do something like this:
	- application.log
- And it will ignore files calld application.log
- Or you can use a wildcard, like so:
	- \*.log
- And it will ignore any .log files
- One useful example: getting rid of .ds_store files on mac, or auth tokens
- Put passwords and whatnot into a config file and make sure it's in .gitignore
- Or else people can use tools like GitHarvester to find personal info you accidentally put in a public repo









