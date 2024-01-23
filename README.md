# Git Hub

## Working with command line

**pwd** - print working directory

**cd** - change directory

**~** home directory (_cd ~_)

**..** - parent directory (_cd.._)

**.** - current directory

**ls** - list directory contents

**ls** - l.d.c. with flag output the 'all' explended list

**touch** - make new file

**mkdir** - make new directory

**mkdir -p** - with flag, creat directory structure

for example:
```java
mkdir -p dir1/dir2/dir3

mkdir ~/my-git-dir // make dir. in home dir.

touch ../../file.txt // make file in two directory up
```

**cd** - 'coupy' (_cp what.copy where/copy/to_)

```java
cp todo.txt /c/Users/Sultan/Documents/Git-study
```

**mv** - 'move', the syntax is the same as 'cp'

**cat** - concatenate and print (объединить и распечатать)

**rm** - 'remove'

**rmdir** - 'remove directory'

**rm -r** - with flag 'recursive', deleted everything in the folder and the folder

<!-- **rm -rf** - with flag 'recursice force', deleted everything with '.git' file -->

**&&** - 'two ampersands', allow multiple commands to be executed in turn

```java
mkdir dir1 && cd dir1 && touch index.html
```
## Commands for working with Git

**git config --global** - 'git configuration' with key word 'global', allow to change name and email in Git
```java
git config --global user.name "name"

git config --global user.email "email@mail.com"
``````
- Git stores all global settings in the '.gitconfig' file in your home directory

```java
cat ~/.gitconfig
```

**git config --list** - with flag 'list' the command line will show the current setting values

**git init** - 'initialize' make a new repository in current directory

(It is not recomended to create a Git repos. inside another Git repos. )

**rm -rf** - with flag 'recursice force', deleted everything with '.git' file, 

**rm -rf .git** - or only '.git' file

**git status** - show repsitory status

**git add** - add a file to the repository for tracking and saving

```java
git add file.txt
```
**git add --all** - with flag 'all' allows to add all the files

(_git add ._ - alternative)

**git  commit -m** - 'commit'(зафиксировать), flag '-m' (message)

```java
    git commit -m 'First commit'
```

- first, the 'git add' command tells Git which files to save and what version they are. The 'git commit' command is used to do the saving 
itself.

**git log** - 'log' (journal) view commit history (press 'q' for leave if have a lot of commits)

## Command for Git Hub

What is **SSH** - (Secure Shell Protocol) when computers communicate on a network, they follow network protocols, the rules for exchanging data between computers.

One of the pupular SSH, allows you to exchange data with a remote computer. The data is encrypted, this provides security.

There are two keys:

- private key
- public key

```java
cd ~/.ssh // directory with 'ssh' keys
```

#### SSH key generation

**1.** _
```java
ssh-keygen -t ed25519 -C "emailInGitHub@mail.com"
// or if another protocol: ssh-keygen -t rsa -b 4096 -C "emailInGitHub@mail.com"
```
**2.** Specify the location where the key is stored.

**3.** Enter the key word.

**4.** Cheking for a key in the '.ssh' directory.

**5.** Start agent:
```java
eval "$(ssh-agent -s)"
//or if another shell: eval (ssh-agent -c)
```
__

**6.** Add a private key to the agent:

```java
ssh-add -K ~/.ssh/id_ed25519
```

#### Binding SSH key to GitHub

**1.** Copy a public key:

macOS: 
```java
pbcopy < ~/.ssh/id_ed25519.pub
// pbcopy - copy all content in the file
```

Windows:
```java
clip < ~/.ssh/id_ed25519.pub
```

- you can olso open content in the file with command 'cat' and copy

**2.** Add new SSh key to GitHub

_Setting/SSH and GPG keys/New SSH key

**3.** Check the key in console:

```java
ssh -T git@github.com
// The first time if asks for authorization, have to enter 'yes'
```

#### Linking local and remote repository

**1.** Linking remote repository to local repository

**git remote add** - remote (удалённый), add (добавить)

```java
git remote add origin git@github.com/repository_name/repository_URL
// two parameters must be passed to the command
// 'remote repository name' and 'URL'
// 'origin' as name (источник)
```

**git remote -v** - linking check

**git push -u origin main** - submit a repository
_'-u' used only first time_

- if the names of the main branches are different, you need to change the local name

**git branch -m master/main** - changing the local repository name

**git clone** - download the project from remote repository

```java
git clone https://github_repository_adres 'download/directory/adres'
```

#### If token expired

- when trying to make a 'git pull' it gives an error:

```java
remote: Invalid username or password
fatal: Authentication failed for 'https://github.com/Shenbasy/first-profect.git
```

- if the token has expired, a 'git pull' should be made with the following addition:

```java
git pull https://username:token@github.com/Shenbasy/first-project.git
```

- where 'username' is your user name, and 'token' is your generated access token