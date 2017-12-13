# Git-Commands
Collection of git commands for frequent scenarios.

## Some great links:
* Git-Branching-Basic-Branching-and-Merging: https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging
* Git-Branching-Rebasing: https://git-scm.book/en/v2/Git-Branching-Rebasing
* Git-Tools-Stashing-and-Cleaning: https://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning

## Config related commands:
* View user details:

`git config user.name`

`git config user.email`
* View all details:

`git config --list`
* Set details globally:

`git config --global user.name "<user name">`

`git config --global user.email "<email>"`

Not recommended to use global settings, better use project level settings. Helpful if you have multiple accounts.
* Set details at project level:

`git config user.name "<user name">`

`git config user.email "<email>"`

More explanation: http://alvinalexander.com/git/git-show-change-username-email-address

## Remote related commands:
* List all existing remotes:

`git remote -v`

* Add remote:

`git remote add <remote_name> <repository_url>`

`git push -u origin master`

* Update/Change remote url:

`git remote set-url <existing_remote_name> <new_url>`

* Remove remote:

`git remote remove <remote_name>`

More Explanation: http://help.github.com/articles/changing-a-remote-s-url

## Ignore related commads:
* Ignore tracked files:

`git upadte-index --assume-unchanged <file>`

More explanation: http://stackoverflow.com/questions/1274057/how-to-make-git-forget-about-a-file-that-was-tracked-but-is-now-in-gitignore

## Branch related commands:
* View branches:

`git branch`

* Get a remote branch on local and switch to it:

`git fetch && git checkout <branch_name>`

* Cut a new branch from an existing branch and switch to it:

`git checkout -b <new_branch_name> <existing_branch_name>`

* Push changes from local branch to remote branch:

If branch is created locally and it doesn't exist at remote: `git push -u <remote_name> <branch_name>`

Else: `git push <remote_name> <branch_name>`
* Rename branch:

If on the branch that needs to be renamed: `git branch -m <new_name>`

If on different branch: `git branch -m <old_name> <new_name>`

The above is enough if the branch only exists in your local, but if the branch has been pushed to remote, follow these two additional steps:

Delete old_name remote branch and push new_name local branch: `git push origin :<old_name> <new_name>`

Reset the upstream branch for the new-name local branch:
`git checkout <new_name>`

`git push origin -u <new_name>`

More explanation: https://multiplestates.wordpress.com/2015/02/05/rename-a-local-and-remmote-branch-in-git/
* Delete local branch:
`git branch -d <branch_name>`

* Delte local branch forecefully, if you have uncommited/unmerged changes:
`git branch -D <branch_name>`
