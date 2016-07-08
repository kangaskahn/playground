# Git Playground

## Commands

- `git <command> -h`
    : gives you a brief synopsis of your options using a command

    - `git <command> --help`
        : displays the detailed man page for the command

- `git init` 
    : creates empty repository in folder
    : An empty repo can be initialized in a directory full of files, but it will remain empty until you `git add *` or `git add .` (from the root) first I.E. it will not be tracking your changes.

- `git status`
: see how the repository status has changed

- `git add <filename>`
: adds <filename> to staging area AKA index, to be committed

    - `git add -p *.txt`
        : interactively adds hunks of all tracked and modified `.txt` files – **use this!**
    - `git add '*.txt'`
        : adds all tracked, modified files of the `.txt` filetype
    - `git add sidebar*.php`
        : adds all tracked PHP files whose name begins with "sidebar" and ends with anything
    - `git add *`
        : adds all modified files for committing
    - `git add .`
        : adds current _directory_ for committing.
        : If in the repo root, this is the same as `git add *`.
    - `git add --all <file|directory|glob>`
        : adds all changes, including untracked files and removed files

- `git commit`
    : commits the changes from staging to the repository
    : Opens the default text editor for editing a concise commit message. This is set with the `EDITOR` or `GIT_EDITOR` variable in your `~/.bash_profile`. On Mac this defaults to Vim, I believe.
    : Useful for messages that require a lot of notes. Enter your brief, concise commit message on the first line, then break two lines and begin writing your longer message.

    - `git commit -m '<commit message>'`
        : commits changes but write your concise commit message in quotations after `-m` flag

- `git log`
    : "journal" of all the commits

	- `git log --pretty=oneline`
        : changes view to one line; neater

	- `git log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short`
        : even better than the last one
        : It's a lot easier to set an alias for this in your `~/.gitconfig`.

- `git remote add <name> <url of repository>`
    : adds remote repository URL for pushes (where <name> = what you want to call the remote e.g. "origin" or "github")

    - `git remote -v`
        : prints detailed info on all your remotes

- `git push -u <remote name> <default local branch name>`
    : pushes updates to remote
    : The `-u` remembers the parameters, setting the upstream branch so next time you can just run `git push`.
    : `git push -u origin master` (Example code)

- `git pull`
    : pulls other people's commits and changes from the remote repository
    : It is very important to do this before you push to make sure you're up to date or else you might end up with some nasty merge conflicts.

- `git diff HEAD`
    : tells what is different from the `HEAD` position
    : In most cases, `HEAD` points to the most recent commit on your branch. For example, your `HEAD` will not be at the most recent commit on your master/main branch if you've checked out an experimental or new feature branch.
    : But if you're digging through history, your `HEAD` will be at a position in the past e.g. a detached head.

- `git reset <filename>`
    : unstage files
    : This could be a directory (`.` or `..`), or a glob pattern (`*.txt`) too.

- `git branch <branch name>` or `git checkout -b <branch name>`
    : creates a new branch
    : `git branch` alone will list all local branches
    : There's a lot of things to be said about branches. It's best not to work directly on a master/main branch when there are multiple people contributing – master is meant to be stable and reliable. It is not to be messed with until changes are tested and pull requests / branches are merged.

	- `git branch -d <branch name>`
        : deletes a branch (useful for doing clean ups)

- `git checkout <branch name>`
    : moves the `HEAD` to the specified position, most often a branch
    
    - `git checkout <file name>`
        : reverts all changes to a file – be careful!

    - `git checkout <commit ref>`
        : checks out the specified commit. Use with caution – this will likely put you into detached `HEAD` state. From the git man page:

            > The state you are in while your HEAD is detached is not recorded by any branch (which is natural --- you are not on any branch). What this means is that you can discard your temporary commits and merges by switching back to an existing branch (e.g. git checkout master), and a later git prune or git gc would garbage-collect them. 


- `git rm`
    : removes files from disk and will stage the removal of those files


- `git merge <branch name>`
    : merges the specified branch into the current branch

- `git diff HEAD`
    : displays a diff of your dirty working directory, or between commits if you specify refs

- `git mergetool`
    : will help you out of merge conflicts using the difftool specified in `~/.gitconfig`