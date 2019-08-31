# ide50

## Setting up an SSH key between cs50 IDE and Github

### Make sure your user info is configured locally
* `git config --global user.email "you@example.com"`
* `git config --global user.name "Your Name"`

### Generate an SSH key
* `cd ~` makes sure you are in the root directory
* `ls -al ~/.ssh` verifies that there are no files that start with `id_rsa`
* `ssh-keygen -t rsa -b 4096 -C "you@example.com"` generates a new SSH key (press <kbd>ENTER</kbd> to save default file path; press <kbd>ENTER</kbd> again (twice) to leave the passphrase blank)
* `eval "$(ssh-agent -s)"` starts the agent in the background
* `ls -al ~/.ssh` you should now see a file named `id_rsa.pub`
* `cat ~/.ssh/id_rsa.pub` then copy _all_ of the result to your clipboard
* Go to https://github.com/settings/keys > New SSH Key
  * Title: ide50
  * Key: paste your ssh key
* Back in your cs50 IDE, do `sudo nano ~/.ssh/config`
* Paste the following:
```
Host github.com
 Hostname ssh.github.com
 Port 443
```
* <kbd>CTRL</kbd>+<kbd>X</kbd> to exit, then press <kbd>Y</kbd> then <kbd>ENTER</kbd>
* `ssh -T git@github.com`
* Type `yes`, press <kbd>ENTER</kbd>, and you should see *Hi "username"! You've successfully authenticated, but GitHub does not provide shell access.*

Sources:
* https://help.github.com/en/articles/adding-a-new-ssh-key-to-your-github-account
* https://stackoverflow.com/questions/15589682/ssh-connect-to-host-github-com-port-22-connection-timed-out