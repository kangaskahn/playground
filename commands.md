#Git Test
=========

##Commands
- git init :: creates empty repository it folder

- git status :: See how the repository status has changed

- git add <filename> :: Adds <filename> to the git tracker

	- git add '*.txt' :: adds wildcards of all the same filetype
	- git add * :: adds all the files for committing
	- git add . :: Adds current _directory_ for committing

- git commit -m '<commit message>' :: Commits the changes from staging to the repository

- git log :: "journal" of all the commits

	- git log --pretty=oneline :: Changes view to one line; neater

	- log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short

- git remote add <name> <url of repository> :: Adds remote repository URL for pushes (where <name> = name of the remote)

- git push -u <remote name> <default local branch name> :: Pushes updates (The -u remembers the parameters so next time you run just run :: git push)

	- git push -u origin master (Example code)

- git pull :: Pulls other people's commits and changes from the remote repository

- git diff HEAD :: Tells what is different from our last commit (the HEAD shows the last commit you made)

- git reset <filename> :: Unstage files

- git branch <branch name> :: Creates a new branch (without a branchname will show all branches [I think])

	- git branch -d <branch name> :: deletes a branch (useful for doing clean ups)

- git checkout <branch name> :: Changes branches from one to the other

- git rm :: Removes files from disk and will stage the removal of those files

- git merge <branch name> :: Merges one branch with the other. Make sure you are in the main branch (use git checkout <branch name>)