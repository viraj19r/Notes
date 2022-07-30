# Github Cheats

To check the git version

> `git --version`

<br>

Setting a default username and email when saving your work is easy by using the commands below

> ```
> git config --global user.name "FIRST_NAME LAST_NAME"
>
> git config --global user.email "MY_NAME@example.com"
> ```
>
> By default, **`git config`** will write to a local level if no configuration option is passed. Local level configuration is applied to the context repository git config gets invoked in.
> Change it for particular repo/local user instead of global user
> Set your username:
> `git config user.name "FIRST_NAME LAST_NAME"`

The global git config is simply a text file, so it can be edited with whatever text editor you choose. Open, edit global git config, save and close, and the changes will take effect the next time you issue a git command. It’s that easy.
>
> From within the BASH shell or terminal window, you can       invoke the default Git editor through the following command:
>
> `git config --global --edit`  
>  
<br>

Set your email address:

> `git config user.email "MY_NAME@example.com"`

Verify your configuration by displaying your configuration file:

> **`cat .git/config`**

> **`git config user.password "your password"`** (optional)

<br>
<br>

### We can work setup GitHub project in two ways.

<br>

### Case-1 : Create a repository on Github, clone it to our computer and start working on it.(Recommended)

Git cloning(clone the whole remote repo, also creates a folder named same as the repo name)

> **`git clone <repository path>`**

<br>

View changes

> **`git status`**

For Short status we can use below command:

> **`git status -s`**

<br>

#### Add Changes

Add a specific file or folder

> ```
> git add [FILENAME] [FILENAME] [...]
> git commit -a [FILENAME] [...]
> ```
>
> Add everything
> `git add . `

<br>

Add commit:

> `git commit -m "COMMENT TO DESCRIBE THE INTENTION OF THE COMMIT"`

Add and commit in one command:

> `git commit -am “Message”`

<br>

Check the name of origin

> `git remote`

if remote name is origin then push changes to remote using

> `git push origin master`

<br>

### Case 2 : Work on your project locally by creating files in your system then create the repository on GitHub and push it to remote.

Convert a local directory into a repository
**`git init`**

- Check status and then add and commit the changes

- Go to github create new repo and don't initialize with readme file this time and then...

<br>

Add the origin remote repo(when a local repo is already created and clone the same local repo with remote)
This creates a connection between our local repo and the remote repo on Github.

> `git remote add origin <link of repo>`

<br>

Change our main branch name to any another name(by default **master** is main branch) - here in our case change it to **main**

> `git branch -M main`

<br>

Set the master branch to upstream (pushes the repo from local to github/remote)

> ```
> git push -u origin master
> *Default branch is master, if we change the branch name to any other name then we have to use that name here instead of master*
> ```

After executing this command, we can check whether we have successfully added the remote or not by the following command

> `git remote`
>
> **And if it outputs “origin” you’ve added the remote to your project.**

<br>

View your remote repositories

> `git remote -v`

 <br>

#### View differences

In order to compare two branches easily, you have to use the “git diff” command and provide the branch names separated by dots.  
> `git diff [first branch]..[second branch]`  
 
 The git diff command can be passed an explicit file option. When a file path is passed to git diff the diff operation will be scoped to the specified file.

> `git diff HEAD ./path/to/file`  
> 
> Omitting **`HEAD`** in the example above **`git diff ./path/to/file`** has the same effect.
> 

<br>

Revert changes

> `git checkout -- .`

<br>

### Git Ignore and .gitignore  

#### Git Ignore
 While sharing your code with others, there are often files or parts of your project, you do not want to share.  
Examples - log files, temporary files, hidden files, personal files etc.  
Git can specify which files or parts of your project should be ignored by Git using a **`.gitignore`** file.

Git will not track files and folders specified in **`.gitignore`**. However, the **`.gitignore`** file itself is tracked by Git.
>

#### Create .gitignore
> To create a .gitignore file, go to the root of your local   Git, and create it:
>
>`touch .gitignore`  
>
> Now open the file using a text editor and add the folder or the file you want to exclude from tracking and then just close the file.
>
<br><br>


### Github push cheats

To push on a specific branch

> `git push <remote> <name-of-branch>`
>
> **_Note_**: _use remote = origin_

Push all branches

> `git push --all`

Sends the committed changes of master branch to your remote repository

> ```
>  git push [variable name] master
>
>  git push [variable name] [branch]
> ```
>
> <br>
> <br>

## Github branch cheats

Create and switch to newly created branch:

> `git checkout -b <name-of-branch>`

Switch to a branch :

> `git checkout <name of branch>`

Creates branch :

> `git branch name`

Show all branches

> `git branch --list`

Merges the specified branch’s history into the current branch

> `git merge [branch name]`

Delete all changes in branch

> `git checkout .`

Switch branch

> `git checkout <branch name>`

Remove selected branch, if it is already merged into any other.
-D instead of -d forces deletion

> `git branch -d [name]`

Delete branch from remote

> `git push origin :branch-name`

To view both remote-tracking branches and local branches, run the command:

> `git branch -a`

To view remote branches only

> `git branch -r`

To rename a branch, run the command

> ```
> git branch -m OLD-BRANCH-NAME NEW-BRANCH-NAME
> ```
>
> **Alternative:**
>
> ```
> git branch --move OLD-BRANCH-NAME NEW-BRANCH-NAME
> ```

Push the newly created branch on github :

> `git push origin [name_of_your_new_branch]`

Make a new branch and then push(first push) it to remote(with tracking):

> `git push -u origin <branch>`
> if we are not sharing the branch with others then we call push all
> `git push --all -u`

Add a new remote for your branch :

> `$ git remote add [name_of_your_remote] [name_of_your_new_branch]`

<br>
<br>
       
## Reset to Head
 Revert the changes(delete or modified) that just made and go back to the files that we had
### Hard reset to head
To hard reset files to HEAD on Git, use the “git reset” command with the “–hard” option and specify the HEAD
>``  git reset --hard HEAD       (going back to HEAD) ``

> ` git reset --hard HEAD^ (going back to the commit before HEAD)`

> `git reset --hard HEAD~2 (going back two commits before HEAD) `

To undo a hard reset on Git, use the “git reset” command with the “–hard” option and specify “HEAD@{1}”

> `git reset --hard HEAD@{1}`

### Soft reset to head

The soft reset won’t alter the working directory and the index. As a consequence, the changes done between the original HEAD and the current HEAD will be staged.

> `git reset --soft HEAD (going back to HEAD)`

> `git reset --soft HEAD^ (going back to the commit before HEAD)`

> `git reset --soft HEAD~2 (going back two commits before HEAD)`

### Restoring Changes
Git restore is used to restore or discard the uncommitted local changes of files.  
Assume that you have done some changes in some files and then if you want to discard those local changes you can safely use git restore.

Another use case is if you want to unstage a file you can use this command. In other words, it is used to undo the effects of **`git add .`**

**Usage**
> `git restore <file_name> `  



[More on head reset](https://devconnected.com/how-to-git-reset-to-head/#:~:text=To%20hard%20reset%20files%20to,option%20and%20specify%20the%20HEAD.&text=The%20purpose%20of%20the%20%E2%80%9Cgit,before%20HEAD%20and%20so%20on)

## Git stash command

Git stash is used in order to save all the changes done to the current working directory and to go back to the last commit done on the branch (also called HEAD).
#### Create a stash
The easiest way to create a git stash is to simply run the **`git stash`** command without any parameters.  
As a consequence, all the changes staged for commit in your current working directory will be saved on the side for later use.
#### Apply Git stashes
Now that you have saved your Git stashes on the side, you might want to “take them out from the stack” and apply them to your current working directory.

>If you don’t specify any arguments to the apply command, the top of the stack will be applied.  
>
> `git stash apply stash@{stash_index}`
> 
> `git stash apply (shortcut for git stash apply stash@{0})`

[More on Stashing](https://devconnected.com/how-to-git-stash-changes/)

- [more commands](https://www.edureka.co/blog/git-commands-with-example/)

When we edit the remote branch and push from local then there is error we can ovecome it by doing

> `git pull`
> <br>The local files will be updated with the changes in the remote or we can use command to forcefully push:  
> ` git push -f origin branch name`
> <br>

> `git pull` is the combination of two git commands -

- > `git fetch`
  > (fetches all the history of changes or tracked branch from remote(github) to local)

- > `git merge` (this will merge the local branch with remote branch)

<br>
<br>

## Other Important Sources

- [Git and Github complete github repo](https://github.com/tiimgreen/github-cheat-sheet)
- [Git cheatsheet pdf external](./Pdfs/Git-Cheat-Sheet.pdf)

- [More on Branches ](https://github.com/Kunena/Kunena-Forum/wiki/Create-a-new-branch-with-git-and-manage-branches)

- [More on Branches from Freecodecamp](https://forum.freecodecamp.org/t/push-a-new-local-branch-to-a-remote-git-repository-and-track-it-too/13222)

- [More on Branches from Medium](https://medium.com/@paulrohan/everday-git-commands-you-will-use-as-a-developer-e84b4a327036)
