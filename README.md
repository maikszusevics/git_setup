# Git Setup
## What is git?
Git is a version control system, it allows programmers and developers to track code changes. 
Code is saved into git, when it is changed and updated it is saved into git again. As the code evolves developers can look back at all of the changes over time. 
This is useful because it allows us to keep track of what we did and when. This helps track down bugs and allows to go back to previous versions of code if needed. 
Git stores projects in Git Repositories.
## Getting started with git
This tutorial will use the gitbash terminal. This will allow us to interact with git using the
same unix commands that it was made designed for. 
[you can download gitbash at this link](https://git-scm.com/downloads)

Run the installer and follow its steps.
### GitHub

GitHub is a website that hosts git repositories. GitHub makes it possible to store git repositories on the cloud.
This makes it much easier to share your projects, to work in groups with other people, and allows you to build a portfolio to show to potential employers.
To get started you will need a GitHub account, for this you will only need a valid email address.
You can sign up to GitHub at [this link](https://github.com/signup)

### Repository set-up with HTTPS
Once you've logged into GitHub, you can make your first repository.
- Click on your profile
- Next to "repositories" on the banner
- Create new repository by clicking "new"
- Name your repository 
- "create repository"

Github will now give you some commands to follow to finish creating your repository.
In order to do this successfully, you will have to add your name and email in Git Bash.

- Run Git Bash as administrator
- Execute the following commands
```
git config --global user.name "Your name here"
git config --global user.email "your_email@example.com"
```
- now you can follow the commands from GitHub, for a HTTP setup these are:
```
echo "# demotest" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/(your_username)/(your_repo_name).git
git push -u origin main
```
once you've run these commands, refresh the github page and you should see your new repository is ready

