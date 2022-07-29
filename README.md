# Git Setup
## What is git?
Git is a version control system, it allows programmers and developers to track code changes. 
Code is saved into git, when it is changed and updated it is saved into git again. As the code evolves developers can look back at all of the changes over time. 
This is useful because it allows us to keep track of what we did and when. This helps track down bugs and allows to go back to previous versions of code if needed. 
Git stores projects in Git Repositories.
## Getting started with git
This tutorial will use the gitbash terminal. This will allow us to interact with git using the
same unix commands that it was designed with. 
[you can download gitbash at this link](https://git-scm.com/downloads)

![image](https://user-images.githubusercontent.com/110176257/181838897-396365da-40e9-44f9-9b3a-7ca41dc37dab.png)


Run the installer and follow its steps.
## GitHub

GitHub is a website that hosts git repositories. GitHub makes it possible to store git repositories on the cloud.
This makes it much easier to share your projects, to work in groups with other people, and allows you to build a portfolio to show to potential employers.
To get started you will need a GitHub account, for this you will only need a valid email address.
You can sign up to GitHub at [this link](https://github.com/signup)

### Repository set-up with HTTPS
Once you've logged into GitHub, you can make your first repository.
- Click on your profile

![image](https://user-images.githubusercontent.com/110176257/181841475-7419e5d0-6e07-48f7-a043-57deca849464.png)

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

### Repository set-up with SSH
#### What is SSH and why is it needed
Using an SSH key means no repetitive authentication is required with email and password, this removes the burden of having to manually authenticate every action you wish to push to the remote server and makes updating a lot more convenient.

#### Setting up SSH key 

- Open gitbash again and type `` cd `` to return to base directory
- Now run ``mkdir .ssh``
- Run ``$ ssh-keygen -t ed25519 -C "your_email@example.com"``

this will prompt you to select directory, using the default .ssh you just created is reccomended.
It will also ask for a password, this is optional and will defeat the convenience gained by using SSH keys. Skip this by leaving the space blank and pressing enter and enter again for confirm password.

![image](https://user-images.githubusercontent.com/110176257/181852378-da853723-81ea-4324-9302-cd4f07a535c5.png)

- you can check if you've created the ssh key properly by running ``cd .ssh``, which will bring you to the ssh directory, and then running the ``ls`` command which will list everything inside the directory. You should see your private key and another one with the same name and .pub at the end, signifying it is the public key.

The next step is to add the key to your GitHub account. Type the following command into the terminal, replacing key ID with the one you've just generated, and it will copy its contents to your clipboard.

``` clip < ~/.ssh/id_ed25519.pub ```

Now you can add this key to your github.

- Go to GitHub > Settings > SHS and GPG keys > New SSH Key > Paste > add a title > click 'Add SSH key'

Now you will have to add your private ssh key to the ssh-agent.
In order to do this you will have to start the ssh-agent, do this by running the command below:

``` eval "$(ssh-agent -s)" ```

Now you can add your private key by running the next command 

```ssh-add ~/.ssh/yourkeyID```
*note: this is the key with no .pub at the end*

### creating a new repository with ssh key

Go to create a repository just like before, but this time make sure you check the ssh setting instead of https located here:

![image](https://user-images.githubusercontent.com/110176257/181857672-77fe5faf-d526-4ad6-89f9-b71f5d16ab64.png)

From here you can follow the given code instructions again, these are shown below as well:

```
echo "# yourreponame" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/maikszusevics/your_repo_name.git
git push --all
```

