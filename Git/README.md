# Git Reference 
- Git clone is a command for downloading existing source code from a remote repository (like Github, for example). 
  Git clone basically makes an identical copy of the   latest version of a project in a repository and saves it to your computer.
  There are a couple of ways to download the source code, 
  - https way:
    `git clone git@github.com:1Amal/python-webapp-https-amaldevelops.pythonanywhere.com.git`

  - Clone using SSH 
  `git clone git@github.com:1Amal/python-webapp-https-amaldevelops.pythonanywhere.com.git`


- The Git status command gives us all the necessary information about the current branch. 
`git status`

- We need to use the git add command to include the changes of a file(s) into our next commit. 
To add a single file:
`git add <file>`

- To add everything at once:
`git add -A`

- Git commit is like setting a checkpoint in the development process which you can go back to later if needed.
We also need to write a short message to explain what we have developed or changed in the source code.
`git commit -m "commit message"`

- After committing your changes, the next thing you want to do is send your changes to the remote server. Git push uploads your commits to the remote repository.
`git push <remote> <branch-name>`

- However, if your branch is newly created, then you also need to upload the branch with the following command:
`git push --set-upstream <remote> <name-of-your-branch>`
or
`git push -u origin <branch_name>`

- The git pull command is used to get updates from the remote repo. This command is a combination of git fetch and git merge which means that, when we use git pull, it gets the updates from remote repository (git fetch) and immediately applies the latest changes in your local (git merge).
`git pull <remote>`

- To see our commit history, first we need to use:
`git log -- oneline`

- A safer way that we can undo our commits is by using git revert. We just need to specify the hash code next to our commit that we would like to undo:
 `git revert 3321844`
The Git revert command will undo the given commit, but will create a new commit without deleting the older one:
The advantage of using git revert is that it doesn't touch the commit history. This means that you can still see all of the commits in your history, even the reverted ones. Another safety measure here is that everything happens in our local system unless we push them to the remote repo. That's why git revert is safer to use and is the preferred way to undo our commits.

- Update local copy with the remote copy
`git pull origin main`

- To update the local list of remote branches:
`git remote update origin --prune`

- To show all local and remote branches that (local) Git knows about:
`git branch -a`


- When you've completed development in your branch and everything works fine, the final step is merging the branch with the parent branch (dev or master). This is done with the git merge command. Git merge basically integrates your feature branch with all of its commits back to the dev (or master) branch. It's important to remember that you first need to be on the specific branch that you want to merge with your feature branch. For example, when you want to merge your feature branch into the dev branch. First you should switch to the dev branch:
`git checkout dev`

Before merging, you should update your local dev branch:
`git fetch`

Finally, you can merge your feature branch into dev:
`git merge <branch-name>`

- Check the fetch and push locations 
`git remote -v`

- Set an email address in Git. You can use your GitHub-provided noreply email address or any email address.

`git config --global user.email "email@example.com"`

- Update renamed repository address
`git remote set-url origin [updated link url https://........git]`

###### Setting up GitHub on a new Linux installation

- Step 1: Adding user name:
`git config --global user.name "Amal K"`

Confirm that you have set the Git username correctly:
`git config user.name`

- Step 2: Set an email address in Git. You can use your GitHub-provided noreply email address or any email address.
`git config --global user.email "email@example.com"`
Confirm that you have set the email address correctly in Git:
`git config --global user.email`

- Step 3: Generating a new SSH key https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
`ssh-keygen -t ed25519 -C "your_email@example.com"`

- Step 4: Adding your SSH key to the ssh-agent
`eval "$(ssh-agent -s)"`
`ssh-add ~/.ssh/id_ed25519`

- Step 5: Adding a new SSH key to your GitHub account https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
`cat ~/.ssh/id_ed25519.pub`
Then select and copy the contents of the id_ed25519.pub file displayed in the terminal to your clipboard
In the upper-right corner of any GitHub page, click your profile photo, then click Settings. Settings icon in the user bar, In the "Access" section of the sidebar, click SSH and GPG keys. Click New SSH key or Add SSH key. These steps should set your new Linux machine with Github



