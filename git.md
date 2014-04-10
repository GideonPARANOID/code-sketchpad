# Git (with GitHub)

## Setting up

### Starting a new repo

    git init
    touch README.md
    git add README.md
    git commit -m 'intial'

Now we need to make a repo on GitHub, (note, if this is already done, pull from `origin master` before you push).

    git remote add origin <github url>
    git push origin master


### Using SSH keys

Assuming we have a SSH keychain & `xclip` installed.

    git config --global user.name '<name>'
    git config --global user.email '<email>'
    xclip -sel clip < ~/.ssh/id_rsa.pub

Then we need to go to [GitHub](https://github.com/settings/ssh) to add the new SSH key to your account & voila, should work.

## Working with Git

### Revert a file

    git checkout <file>

