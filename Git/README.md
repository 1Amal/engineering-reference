# Git Reference

************Setting up GitHub on a new Linux installation************

Step 1: Adding user name:
git config --global user.name "Amal K"

Confirm that you have set the Git username correctly:
git config user.name

Step 2: Set an email address in Git. You can use your GitHub-provided noreply email address or any email address.
git config --global user.email "email@example.com"
Confirm that you have set the email address correctly in Git:
git config --global user.email

Step 3: Generating a new SSH key https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
ssh-keygen -t ed25519 -C "your_email@example.com"

Step 4: Adding your SSH key to the ssh-agent
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

Step 5: Adding a new SSH key to your GitHub account https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
cat ~/.ssh/id_ed25519.pub
Then select and copy the contents of the id_ed25519.pub file
displayed in the terminal to your clipboard
In the upper-right corner of any page, click your profile photo, then click Settings.
Settings icon in the user bar, In the "Access" section of the sidebar, click SSH and GPG keys.
Click New SSH key or Add SSH key.
These steps should set your new Linux machine with Github

**** Check the fetch and push locations *****
git remote -v

Set an email address in Git. You can use your GitHub-provided noreply email address or any email address.

git config --global user.email "email@example.com"


Update renamed repository address
git remote set-url origin [updated link url https://........git]

