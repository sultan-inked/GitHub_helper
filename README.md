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

_mkdir -p dir1/dir2/dir3_

_mkdir ~/my-git-dir_ - make dir. in home dir.

_touch ../../file.txt_ - make file in two directory up

**cd** - 'coupy' (_cp what.copy where/copy/to_)

_cp todo.txt /c/Users/Sultan/Documents/Git-study_

**mv** - 'move', the syntax is the same as 'cp'

**cat** - concatenate and print (объединить и распечатать)

**rm** - 'remove'

**rmdir** - 'remove directory'

**rm -r** - with flag 'recursive', deleted everything in the folder and the folder

<!-- **rm -rf** - with flag 'recursice force', deleted everything with '.git' file -->

**&&** - 'two ampersands', allow multiple commands to be executed in turn

_mkdir dir1 && cd dir1 && touch index.html_

## Commands for working with Git

**git config --global** - 'git configuration' with key word 'global', allow to change name and email in Git

_git config --global user.name "name"_

_git config --global user.email "email@mail.com"

- Git stores all global settings in the '.gitconfig' file in your home directory

_cat ~/.gitconfig

**git config --list** - with flag 'list' the command line will show the current setting values

**git init** - 'initialize' make a new repository in current directory

(It is not recomended to create a Git repos. inside another Git repos. )

**rm -rf** - with flag 'recursice force', deleted everything with '.git' file, 

**rm -rf .git** - or only '.git' file

**git status** - show repsitory status

**git add** - add a file to the repository for tracking and saving

_git add file.txt_

**git add --all** - with flag 'all' allows to add all the files

(_git add ._ - alternative)

**git  commit -m** - 'commit'(зафиксировать), flag '-m' (message)

_git commit -m 'First commit'_

- first, the 'git add' command tells Git which files to save and what version they are. The 'git commit' command is used to do the saving 
itself.

**git log** - 'log' (journal) view commit history (press 'q' for leave if have a lot of commits)