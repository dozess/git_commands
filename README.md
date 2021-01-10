# Github infrastructure setup
## Local repository setup

Initialisation of git in the local development or deployment copy:<br />
`git init`

it will create `.git/` subfolder with version data base

ading content to the git `git add .`

check status `git status` : prints status of the local git, changed files , neww files etc.

after changing filess : `git add .`, `git commit -m "commit message"`

special file `.gitignore` containing list of ignored files and directories one per line. Filess listed in `.gitignore` will not be aded to git with `git add .`  

Also for first time use on machine you need to st up your user

  `git config --global user.email "you@example.com"`
  
  `git config --global user.name "Your Name"`

----
## Setting remote repository in GitHub

Create new repository in GitHub 
setting up ssh keypair authentification is comfortable option to work on linux machines commandprompt

to generate keypair on your linux machine generaite caypair:

`ssh-keygen -t ed25519 -C "your_email@example.com"`

then on github on your repository settings chose 

> Deploy keys

and add new key.

on linux machine enter command `cat ~/.ssh/'your key name'.pub`

and copy all file content to the github key, and name it

first time conecting to the repository from your local git server will exchange keys and will ask you to trust it. 


## linking local git to GitHub

on the local git repositori create link to remote git 

`git remote add origin 'repository url'` 

'origin' is name of remote repository it can be any name, but the common, agreed-upon convention is to call a repository's main remote connection "origin" 

You can include the branch to track when setting up remotes, to keep things working as you might expect:

git remote add --track master origin user@somesite.com:group/project.git   # git

git remote add --track master origin user@172.16.1.100:group/project.git   # git w/IP

git remote add --track master origin http://github.com/group/project.git   # http

git remote add --track master origin http://172.16.1.100/group/project.git # http w/IP

git remote add --track master origin /Volumes/Git/group/project/           # local

git remote add --track master origin G:/group/project/                     # local, Win


