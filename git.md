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
    git push <remote name> <branch name>

### Using SSH keys

Assuming we have a generated a SSH keychain & we have `xclip` installed. Note that `xclip` needs an X server, so it can just be done with `cat`, but that's a bit less secure.

    git config --global user.name '<name>'
    git config --global user.email '<email>'
    xclip -sel clip < ~/.ssh/id_rsa.pub

Then we need to go to [GitHub](https://github.com/settings/ssh)/[Bitbucket](https://bitbucket.org/account/user/<userid>/ssh-keys/) to add the new SSH key to your account & voila, should work.

## Working with Git

### Revert a file

    git checkout <file>

## Submodules

Submodules are useful for repos which contain repos. 

### Adding submodule

    git submodule add <repo>

### Cloning repo with submodules

    git clone <repo>
    git submodule init
    git submodule update

## Branches

### Delete a remote branch

    git push origin :<branch name>
