# GIT

## Git Config

### Global

```
$ git config --global user.name "Your Name"
$ git config --global user.email yourid@company.com
```

~/.gitconfig
```
[user]
	name = Your Name
	email = yourid@company.com
```

### Local

```
$ git config user.name "Your Name"
$ git config user.email yourid@gmail.com
```

{project}/.git/config
```
[user]
	name = Your Name
	email = yourid@gmail.com
```

## Multiple Accounts for GitHub.com

### 1. Generating a new SSH key and adding it to the ssh-agent

https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/

```
$ ssh-keygen -t rsa -b 4096 -C "yourid@gmail.com"
$ Enter a file in which to save the key (/Users/you/.ssh/id_rsa): /Users/you/.ssh/id_rsa_devnoh

$ ssh-keygen -t rsa -b 4096 -C "yourid@company.com"
$ Enter a file in which to save the key (/Users/you/.ssh/id_rsa): /Users/you/.ssh/id_rsa_company

$ ssh-add ~/.ssh/id_rsa_devnoh
$ ssh-add ~/.ssh/id_rsa_company
```

### 2. ~/.ssh/config
```
# Default GitHub
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa

# GitHub-Personal
Host github-devnoh
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_devnoh

# GitHub-Company
Host github-company
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_company
```

### 3. Git Config

```
$ git clone git@github-devnoh:devnoh/apptest.git
$ git config user.name "Your Name"
$ git config user.email "yourid@gmail.com"
```

```
$ git clone git@github-company:sehwannoh/codestyle.git
$ git config user.name "Your Name"
$ git config user.email "yourid@company.com"
```


## Adding an existing project to GitHub using the command line

Create a new repository on GitHub, and then change the current working directory to your local project.

```
$ echo "# devnoh.github.io" >> README.md
$ git init
$ git config user.name "Your Name"
$ git config user.email yourid@gmail.com
$ git add .
$ git commit -m "Initial commit"
$ git remote add origin git@github-devnoh:devnoh/devnoh.github.io.git
$ git remote -v
$ git push -u origin master
```

## Rename Branch

```
$ git branch -m old_branch new_branch         # Rename branch locally
$ git push origin :old_branch                 # Delete the old branch
$ git push --set-upstream origin new_branch   # Push the new branch, set local branch to track the new remote
```

## Delete Branch

Remote:

```
$ git push -d origin <branch_name>
$ git branch -d <branch_name>
```

Local:

```
$ git branch -d branch_name
$ git branch -D branch_name
```

## Mirror a Git Repository

https://help.github.com/articles/duplicating-a-repository/

* GitHub to Bitbiucket
```
$ git clone --mirror https://github.com/devnoh/devnoh.github.io.git
$ cd devnoh.github.io.git
$ git remote set-url --push origin git@devnoh-Bitbucket:devnoh/devnoh.github.io.git
$ git push --mirror
```

* Bitbucket to Github
```
$ git clone --mirror https://devnoh@bitbucket.org/devnoh/devnoh-awsmon.git
$ cd devnoh-awsmon.git
$ git remote set-url --push origin git@github-devnoh:devnoh/devnoh-awsmon.git
$ git push --mirror
```

To update your mirror, fetch updates and push.

```
$ git fetch -p origin
$ git push --mirror
```


