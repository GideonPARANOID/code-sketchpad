# Git (with GitHub/Bitbucket)

* Remember that you always need to be in the git repository to perform any actions on objects. `git add <repository>/<file>` won't work, for example. 

## Setting up

### Starting a new repo

    git init
    touch README.md
    git add README.md
    git commit -m 'intial'

If we're working with GitHub/Bitbucket, we now need to make a repo. Don't choose to initialise the repo with a readme as that can confuse things.

    git remote add <remote name> <remote source>
    git push -u <remote name> <branch name>

### Using SSH keys

Assuming we have a generated a SSH keychain & we have `xclip` installed. Note that `xclip` needs an X server, so it can just be done with `cat`, but that's a bit less secure.

    git config --global user.name '<name>'
    git config --global user.email '<email>'
    xclip -sel clip < ~/.ssh/id_rsa.pub

Then we need to go to [GitHub](https://github.com/settings/ssh)/[Bitbucket](https://bitbucket.org/account/user/<userid>/ssh-keys/) to add the new SSH key to your account & voila, should work.


## Config

### .gitignore

A config file, used for telling git which files to ignore in a repository. It supports wildcards.

### .gitattributes

Another config file, used for telling git some extra rules with various files (including wildcards). For example, the following ensures that bash script files are checked out with UNIX line endings.

    *.sh eol=lf

## Working with git

### Show diff of last commit

    git diff HEAD^ HEAD

### Check if file is tracked

    git ls-files <file>

### Stashing

If there's files you're working on which you don't want to commit with the currently staged files, stash them.

    git stash
    
To see what files are stashed, follow this with `list`, & to stage these stashed files again, use `pop`.

    
### Rebasing

Basically, rebasing is merging multiple commits down into one. It's useful for patches spanning multiple commits.

    git rebase -i 
    
You want to squash then the newer commits down into the original one.

### Ignoring locally deleted files

Sometimes when you're working on a repo, you want to clean up but not remove things from version control. Useful for configuration management repositories where not everything is always relevant.

    git ls-files --deleted -z | git update-index --assume-unchanged -z --stdin


## Submodules

Submodules are useful for repos which contain repos. 

### Adding submodule

    git submodule add <repo>

### Cloning repo with submodules

    git clone <repo>
    git submodule init
    git submodule update

## Branches

### Checking out

    git checkout <branch>

### Delete a remote branch

    git push origin :<branch name>
    
## Going back

If something's gone wrong, it can be useful to go back to a point in the repo. To find a point, use  `git reflog` to find the `HEAD` position, & then `git reset --hard HEAD@{<position>}` to reset things.
