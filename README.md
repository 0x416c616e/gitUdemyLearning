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
- You can choose to ignore things based on wildcards, but then make a single exception. * - wildcard, ! = exception. Combinations of these can be useful instead of doing lots of things manually.

### diff

- Usage: do git hist first to see a list of commits
- Then do something like git diff c119f76 (or whatever the commit is) to see the difference between the current commit and that one
- I've installed p4merge and changed my git global config stuff so that p4merge is the default diff and merge tool

### HEAD

- Special pointer to the current commit

### difftool

- Kind of like the diff command, but uses the configured diff tool (in my case, p4merge)
- Example usage:
- git difftool db7e30f HEAD

### git diff (with no commits to compare)

- Shows the difference between the working directory vs. HEAD
- In other words, the differences you haven't committed yet vs. the last commit

### git difftool (with no commits to compare)

- Just like git diff (see above), but it will use your configured default diff tool (such as p4merge)
- dff tools are very important
- Anything that can be passed to the diff command can also be passed to the difftool command
- diff is short for difference


### BRANCHING

- Super important in git
- A branch is just a timeline of commits.
	- Branches names are labels
	- Deletion only gets rid of labels, not commits
- Default branch is master branch, but in the future I will want to use a feature branch
- After you complete a feature, you merge it back into the maaster branch

### MERGING

- Types of merges:
1. Fast-forward merge
	- Simplest case
	- It's like it was never branched to begin with
	- It can be disabled
	- Applies commits to the parent branch
2. Automatic merge
	- Non-conflicting merge detected (merge conflicts are bad)
	- Preserves both timelines
	- A new merge commit shows the merging of the two branches
3. Manual merge
	- When git can't do it automatically
	- Merge conflicts must be fixed before you can proceed
	- Merge conflicts
	- Changes are saved in the merge commit (but only once all conflicts are solved)

### Fixing commit message typos in a previously-pushed commit

- I've made a typo in a commit message that I wanted to change, so even though these commands haven't been covered in the course just yet, I looked up a guide online and this is what I did:
	1. git rebase -i HEAD~1
	2. git commit --amend
	3. git rebase --continue
	4. git push origin master --force

### SPECIAL MARKERS

- Kind of like pointers or environment variables
- HEAD
	- Points to the last commit of the current branch
	- You can move the HEAD (but that's more complicated)

## Branching and merging

Need to put more info here about commands

## .gitkeep

Unofficial but useful.

## Pull requests

This is more about GitHub than git, but oh well.

## Code review

Add more info here.

## Issues

Add more info here

## Releases

Not finished.

## Command line vs. GUI/web

## Committing, branching, and merging best practices

