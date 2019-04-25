# Introduction to Git with Bitbucket

### Branching
- Create a branch:
```bash
git branch branchname
```
- Go to new branch:
```bash
git checkout branchname
```

### Fast-forward branching
- go checkout master branch
- Then merge other branch into master
```bash
git merge branchname
```

### Deleting branches
- Use the following to delete branches
```bash
git branch -d branchname
```
- When you delete future-plans, you can still access the branch from master using a commit id.


# Git_Tutorial
### Adding file to new and existing repos
- `git add .` recursively adds all the files in a given foler
- `git init` can be used to initialize the git repo in a folder

### Forking
- First go to the repo you'd like to fork
- select fork and go to the new page, to clone the forked repo 

### Pulling before Pushing
- always make sure to pull the code from the master before pushing the changes up 

### Combining Git Add and git commit
- use the following git command to combine both the add and commit commands
- `-am` means that you commit add and include a message 
```bash
git commit -am "Commit comment"
```

### See status of git files
- use the following command to see a list of files which are being currently tracked by git
```
git ls-files
```

### Recursively add files nested in folders
- use the following command
```
git add .
```

### Backing out Changes
- use `git reset HEAD <file>...` to unstage files you just recently added

### Discard changes in a working directory
- This will remove the changes you placed in your local working directory
```
git checkout -- <file>...
```

### Changing file names
- You can use the following command in order to change the name of a given file
```
git mv oldfilename newfilename
```
- If you do not include `git` infront of `mv` then git will view this action as two steps. 1) deleting the original file 2) creating a new file 
- So in order to fix this, you need to `git add -A` all the changes

### Moving files
- Use the following command to move files
```
git mv filenametomove foldernametomoveto/
```

### Restaging deleted files
- use `git checkout -- filename` whenever you have deleted a file that you want to bring back to your local repo, once it has been tracked by git 

### History
- use `git log` to get a history of git commits
- use `git log --abbrev-commit` to see shortened SHA1 commit tags
- use `git log --oneline --graph --decorate` to see oneline of each of the commits 
- `--graph` will show the layers, while `--decorate` will show colored changes
- use `git log --since="3 days ago"` to see commits from the last 3 days
- use `git log --follow filename` to see log history
- use `git show SHA1Code` to see commit details on a specific commit

### Git Alias
- Here we can create short-cuts for specific git commands
- The following bash commands below allow us to save the long hist command into the the empty git hist command
```
git config --global alias.hist "log --all --graph --decorate --oneline"
```
- You can use the following command to see you current git configuration
```
 nano ~/.gitconfig
```

### GitIgnore
- There are several ways to ignore files in a given repo:
1) Add the file name to the `.gitignore` file
2) Add a `*` + `.filetype` to exclude all files with a given filetype
3) Add the `foldername` + `/`