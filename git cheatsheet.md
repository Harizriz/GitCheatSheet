# git cheat sheet

## create a git repository

```
git init .
```

`.` means this current directory

## displays the state of the working directory and the staging area

lets you see which changes have been staged, which haven't and which files aren't being tracked by Git. Untracked files and changes to be committed will be detected by the branch master

```
git status
```

## copy of an existing repository at in a new directory or another location

the code below demonstrates how to obtain a local copy of a central repository stored on a server accessible at `example.com`

```
git clone // HTTPS url --example.com--
cd the name of the project
# start working on the project
```

the first command initialises a new Git repository in the `my-project` folder in your local machine. Then change directory into the project and start editing files.

## cloning to a specific folder

```
git clone <repo> <directory>
```

clone the repository located at `<repo>` into the folder called `<directory>` on the local machine

## adds a change in the working directory to the repository

```
git add <file name>
git add index.html
```

stage all changes in `<file name>` for the next commit

```
git add <directory>
git add .
```

stage all changes in `<directory>` for the next commit

```
git add -p
```

choose portions of a file to add to the next commit. use `a` to commmit all changes, `y` to stage the chunk, `n` to ignore the chunk, `s` to split it into smaller chunks, `e` to manually edit the chunk, and `q` to exit

## save your changes to the local repository

commit the staged snapshot by `git status`

```
git commit
```

commit a snapshot of all changes in the working directory

```
git commit -a
```

immediately creates a commit with a passed commit message

```
got commit -m "commit message"
```

`-m` option will forgo *go without (something desirable)* the text editor prompt in-favor of an inline message

## publish new local commits on a remote server

```
git push
```

## download all the changes from Github.com

this command will only work when you are in the directory of your Github repository

```
git pull
```

## delete a local branch

~~~ bash
git branch -d branch_name
git branch -D branch_name
~~~

`-D` parameter or `--delete --force` is a **forced delete** regardless of its `push` or `merge` status

## delete a remote git branch

~~~ bash
git push <remote_name> --delete <branch_name>
~~~

this will delete the specified branch in the remote repo (*GitHub*). `remote_name` is usually *master*

## gitignore

`.gitignore` file must be edited and committed by hand when you have new files that you wish to **ignore**. `.gitignore` files contain patterns that are matched against file names in your repository to determine whether or not they should be ignored.

```
.gitignore
```

before first commit, assuming the `.gitgnore` checkbox wasn't checked.

~~~ bash
nul >> gitignore.txt
~~~

used to hide certain files from git. Add all the file names of your choice. To hide all files of a certain *file extension*, add wildcard `*`. Example, `*.py`

## resetting files

if some files were unintentionally tracked with `git add *`, reset them with

~~~ bash
git reset
git reset <file_name>
~~~

## stashing files before a pull

if you have uncommitted/untracked files and you want to pull/commit other files

~~~ bash
git stash push
~~~

then after that, run

~~~ bash
git stash pop
~~~

to get your files back
