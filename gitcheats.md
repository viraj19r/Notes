# Github Cheats

To check the git version

>`git --version`

<br>

Run the following commands with your information to set a default username and email when you’re going to save your work
>```
>git config --global user.name "FIRST_NAME LAST_NAME"
>git config --global user.email "MY_NAME@example.com"
>```

Change it for particular repo/local user instead of global user
Set your username:
>` git config user.name "FIRST_NAME LAST_NAME" `

Set your email address:
>` git config user.email "MY_NAME@example.com" `

Verify your configuration by displaying your configuration file:
>` cat .git/config `

>` git config user.password "your password" ` (optional)

<br>
<br>

### We’ll work with GitHub projects in two ways.

<br>

### Case-1 : Create a repository on Github, clone it to our computer and start working on it.(Recommended)

Git cloning(clone the whole remote repo, also creates a folder named same as the repo name)
>`` git clone <repository path> ``

<br>

View changes
>`` git status ``
Short status
>`git status -s` 

<br>

#### Add Changes
Add a specific file or folder
>`` git add [FILENAME] [FILENAME] [...] ``
>`git commit -a [FILENAME] [...]`

Add everything
>`git add . `

<br>

Add commit
>`` git commit -m "COMMENT TO DESCRIBE THE INTENTION OF THE COMMIT" ``
 
Add and commit in one command
>`` git commit -am “Message” ``

<br>

Check the name of origin
>`git remote`

if remote name is origin then push changes to remote using
>`git push origin master`


<br>


### Case 2 : Work on your project locally by creating files in our system then create the repository on GitHub and push it to remote.

Convert a local directory into a repository
 `` git init ``
 
- Check status and then add and commit the changes

- Go to github create new repo and don't initialize with readme file this time and then...

<br>

Add the origin remote repo(when a local repo is already created and clone the same local repo with remote)
This creates a connection between our local repo and the remote repo on Github.
>`` git remote add origin <link of repo> ``

<br>

change our main branch name to any another name(by default **master** is main branch) - here in our case change it to **main**
>`git branch -M main`

<br>

Set the master branch to upstream(pushes the repo from local to github/remote)
>`` git push -u origin master `` Default branch is master, if we change the branch name to any other name then we have to use that name here instead of master


After executing this command, we can check whether we have successfully added the remote or not by the following command
>`git remote`
And if it outputs “origin” you’ve added the remote to your project.

<br>

View your remote repositories
>`` git remote -v ``
 
 <br>

View differences
>`` git diff [first branch] [second branch] ``

<br>

Revert changes
>`` git checkout -- . ``

<br>



### Github push cheats
To push on a specific branch
>`` git push <remote> <name-of-branch> `` (use remote = origin)

Push all branches
>`` git push --all ``

Sends the committed changes of master branch to your remote repository
>`` git push [variable name] master ``
>`` git push [variable name] [branch] ``

<br>
<br>

## Github branch cheats

Create and switch to newly created branch:
>`` git checkout -b <name-of-branch> ``

Switch to a branch :
>`` git checkout <name of branch> ``

Creates branch :
>`` git branch name ``

Show all branches
>`` git branch --list ``

Merges the specified branch’s history into the current branch
>`` git merge [branch name] ``

Delete all changes in branch
>`` git checkout . ``

Switch branch
>`` git checkout <branch name> ``

Remove selected branch, if it is already merged into any other.
-D instead of -d forces deletion
>`` git branch -d [name] ``

Delete branch from remote
>`` git push origin :branch-name ``

To view both remote-tracking branches and local branches, run the command:
>`` git branch -a ``

To view remote branches only
>`git branch -r`

To rename a branch, run the command
>`` git branch -m OLD-BRANCH-NAME NEW-BRANCH-NAME ``
 Alternative:
>`` git branch --move OLD-BRANCH-NAME NEW-BRANCH-NAME ``

Push the newly created branch on github :
>`` git push origin [name_of_your_new_branch] ``

Make a new branch and then push(first push) it to remote(with tracking):
>`` git push -u origin <branch> ``
if we are not sharing the branch with others then we call push all
>`git push --all -u`

Add a new remote for your branch :
>`` $ git remote add [name_of_your_remote] [name_of_your_new_branch] ``

<br>
<br>
       
### Reset to Head
 revert the changes(delete or modified) that just made and go back to the files that we had
#### Hard reset to head
To hard reset files to HEAD on Git, use the “git reset” command with the “–hard” option and specify the HEAD
>``  git reset --hard HEAD       (going back to HEAD) ``

>``  git reset --hard HEAD^      (going back to the commit before HEAD) ``

>`` git reset --hard HEAD~2     (going back two commits before HEAD)  ``


To undo a hard reset on Git, use the “git reset” command with the “–hard” option and specify “HEAD@{1}”
>`` git reset --hard HEAD@{1} ``

### Soft reset to head
The soft reset won’t alter the working directory and the index. As a consequence, the changes done between the original HEAD and the current HEAD will be staged.
>`` git reset --soft HEAD       (going back to HEAD) ``

>`` git reset --soft HEAD^      (going back to the commit before HEAD) ``

>`` git reset --soft HEAD~2     (going back two commits before HEAD) ``

[More on head reset](https://devconnected.com/how-to-git-reset-to-head/#:~:text=To%20hard%20reset%20files%20to,option%20and%20specify%20the%20HEAD.&text=The%20purpose%20of%20the%20%E2%80%9Cgit,before%20HEAD%20and%20so%20on).)

## Git stash command
[Stash command](https://devconnected.com/how-to-git-stash-changes/)

* [more commands](https://www.edureka.co/blog/git-commands-with-example/)
 
When we edit the remote branch and push from local then there is error we can ovecome it by doing

>`` git pull `` = it will update the local with the changes in the remote or we can forcefully push as ``` git push -f origin branch name```

>`git pull` is the combination of two git commands - 
- >`git fetch`(fetches all the history of changes or tracked branch from remote(github) to local)
- >`git merge`(this will merge the local branch with remote branch)



<br>
<br>



## Other Important Sources
- [Git and Github complete github repo](https://github.com/tiimgreen/github-cheat-sheet)
- [Git cheatsheet pdf external](./Pdfs/Git-Cheat-Sheet.pdf)

- [more on branches ](https://github.com/Kunena/Kunena-Forum/wiki/Create-a-new-branch-with-git-and-manage-branches)

- [more on branches from freecodecamp](https://forum.freecodecamp.org/t/push-a-new-local-branch-to-a-remote-git-repository-and-track-it-too/13222)

- [more on branches from medium](https://medium.com/@paulrohan/everday-git-commands-you-will-use-as-a-developer-e84b4a327036)