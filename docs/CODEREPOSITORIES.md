
## Vendors
[Github](https://github.com)
- Tokens - let you setup fine grained permissions on a per repo basis
- Actions - let you setup CI checks 
- Dependabot - check vulnerabilities for a repo
  
Bitbucket \
Singularity - mono repository

## Processes
### GitOps 
- process where OPS approves pull requests and ENG controls environment
- GitOps is a way of managing declarative infrastructure using Git as the single source of truth. With GitOps, infrastructure changes are a core component of the software integration and delivery process, and you can integrate them into the same CI/CD pipeline. 


### GitFlow 
- Build release branches and deploy from them
  
![GitFlow](/images/gitflow.png)

### GitHub Flow
- Merge directly into master
  
![GitHub Flow](/images/githubflow.png)

## Semantic Versioning (semver)
Consider a version format of X.Y.Z (Major.Minor.Patch). Bug fixes not affecting the API increment the patch version, backwards compatible API additions/changes increment the minor version, and backwards incompatible API changes increment the major version.




# Git

## Basics
Repo - a storage of code with metadata on who did what \
Add - staging a file to be added to a commit \
Commit - a snapshot of some work, usually a bunch of added files \
Branch - a fork that is used as a base to add new code \
Merge - merge a set of commits together, when you want to merge back in a branch \
Status - check the status of the current env 

## Configuration
Git comes with a tool called git config that lets you get and set configuration variables that control all aspects of how Git looks and operates. These variables can be stored in three different places: 
- [path]/etc/gitconfig file: Contains values applied to every user on the system and all their repositories. If you pass the option --system to git config, it reads and writes from this file specifically. Because this is a system configuration file, you would need administrative or superuser privilege to make changes to it. 
- ~/.gitconfig or ~/.config/git/config file: Values specific personally to you, the user. You can make Git read and write to this file specifically by passing the --global option, and this affects all of the repositories you work with on your system.
- config file in the Git directory (that is, .git/config) of whatever repository you’re currently using: Specific to that single repository. You can force Git to read from and write to this file with the --local option, but that is in fact the default. Unsurprisingly, you need to be located somewhere in a Git repository for this option to work properly.

```
$ git config --list 
user.name=John Doe 
user.email=johndoe@example.com 
color.status=auto 
color.branch=auto 
color.interactive=auto 
color.diff=auto
```

## Create a new repo
```
mkdir reponame 
git init 
git add file1.txt 
git add file2.txt 
git add LICENSE 
git commit -m 'Initial project version'
```

## Add remote repo via SSH
```
git remote add origin git@github.com:guhan/<reponame>.git 
git push -u origin master`
```

## Get data from your remote projects
The command goes out to that remote project and pulls down all the data from that remote project that you don’t have yet. After you do this, you should have references to all the branches from that remote, which you can merge in or inspect at any time. \

`$ git fetch <remote>`

## Detached HEAD
Checking out a specific commit: If you run the command git checkout <commit-hash>, you will be in a detached HEAD state. This happens because you are not on a named branch, but rather on a specific commit.

Checking out a tag: If you run the command git checkout <tag-name>, you will also be in a detached HEAD state, because tags are also associated with specific commits.

Merging a commit: If you merge a commit directly, such as with the command git merge <commit-hash>, and the merge cannot be resolved automatically, you will be placed in a detached HEAD state until you resolve the conflict.


## Cheatsheet

![1](/images/gitcheatsheet1.png)

![2](/images/gitcheatsheet2.png)



