# Git (with GitHub)

## Setting up

### Using SSH keys

Assuming we have a SSH keychain & `xclip` installed.

    git config --global user.name '<name>'
    git config --global user.email '<email>'
    xclip -sel clip < ~/.ssh/id_rsa.pub

Then we need to go to [GitHub](https://github.com/settings/ssh) to add the new SSH key to your account & voila, should work.

## Working with Git

### Revert a file

    git checkout <file>

