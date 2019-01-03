# Git learning stuff

This isn't really a software repo, more of just a way for me to learn more about git and github, It corresponds to a course on Udemy, which you can find [here](https://www.udemy.com/github-ultimate/).

Some things I've gone over:
- git clone
- git commit
- git commit -m
- git add .
- git add -A
- git rm filename
- git add filename
- git status
- git init
- git log
- git show
- git push
- git pull
- git ls-files
- git commit -am "commit message"
	- adding -a will automatically add modified files
- Backing out of a bad change
	- git reset HEAD example.txt
	- git checkout -- example.txt
	- The above two commands will revert example.txt back to the previous commit version as specified in HEAD
- git help 
- git help specific-command (example: git help log)
	- kind of like linux man pages, but for git stuff

- list all global configurations in git
	- git config --global --list
- create an alias, not unlike bash:
	- git config --global alias.hist "log --oneline --graph --decorate --all"
- the equivalent to a history command, shows compact and useful info about the repo's history:
	- git log --oneline --graph --decorate --all
- only get history for a single file
	- git hist -- filename.txt
	- OR:
	- git log --oneline --graph --decorate --all filename.txt
	- not having the additional filename arg will just show the whole repo history, whereas
	- including the filename will mean it'll only show the history for that particular file



