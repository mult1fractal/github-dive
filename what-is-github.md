GitHub flow is a lightweight, branch-based workflow that supports teams and projects where deployments are made regularly. This guide explains how and why GitHub flow works

# Github tutorial
GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

This tutorial teaches you GitHub essentials like repositories, branches, commits, and Pull Requests. You’ll create your own Hello World repository and learn GitHub’s Pull Request workflow, a popular way to create and review code.


**Repository:** A directory or storage space where your projects can live. Sometimes GitHub users shorten this to “repo.” It can be local to a folder on your computer, or it can be a storage space on GitHub or another online host. You can keep code files, text files, image files, you name it, inside a repository.

**Version Control:** Basically, the purpose Git was designed to serve. When you have a Microsoft Word file, you either overwrite every saved file with a new save, or you save multiple versions. With Git, you don’t have to. It keeps “snapshots” of every point in time in the project’s history, so you can never lose or overwrite it.

**Commit:** This is the command that gives Git its power. When you commit, you are taking a “snapshot” of your repository at that point in time, giving you a checkpoint to which you can reevaluate or restore your project to any previous state.

**Branch:** How do multiple people work on a project at the same time without Git getting them confused? Usually, they “branch off” of the main project with their own versions full of changes they themselves have made. After they’re done, it’s time to “merge” that branch back with the “master,” the main directory of the project.

## Create a New repo

what is a repository
* organize a single project
* can contain folders and files, images, videos, spreadsheets, and data sets – anything your project needs.
* including a README, or a file with information about your project

## Create a Branch


* Branching is the way to work on different versions of a repository at one time
* By default your repository has one branch named `main` which is considered to be the definitive branch.
* We use branches to experiment and make edits before committing them to `main`.

* When you create a branch off the `main` branch, you’re making a copy, or snapshot, of main as it was at that point in time. 
* If someone else made changes to the main branch while you were working on your branch, you could pull in those updates.


The main branch
A new branch called feature (because we’re doing ‘feature work’ on this branch)
The journey that feature takes before it’s merged into main
a branch

Have you ever saved different versions of a file? Something like:

story.txt
story-joe-edit.txt
story-joe-edit-reviewed.txt


### Create a new branch







workflow
your local repository consists of three "trees" maintained by git. the first one is your Working Directory which holds the actual files. the second one is the Index which acts as a staging area and finally the HEAD which points to the last commit you've made.

update & merge
to update your local repository to the newest commit, execute
git pull
in your working directory to fetch and merge remote changes.
to merge another branch into your active branch (e.g. master), use
git merge <branch>
in both cases git tries to auto-merge changes. Unfortunately, this is not always possible and results in conflicts. You are responsible to merge those conflicts manually by editing the files shown by git. After changing, you need to mark them as merged with
git add <filename>
before merging changes, you can also preview them by using
git diff <source_branch> <target_branch>


tagging
it's recommended to create tags for software releases. this is a known concept, which also exists in SVN. You can create a new tag named 1.0.0 by executing
git tag 1.0.0 1b2e1d63ff
the 1b2e1d63ff stands for the first 10 characters of the commit id you want to reference with your tag. You can get the commit id by looking at the...

replace local changes
In case you did something wrong, which for sure never happens ;), you can replace local changes using the command
git checkout -- <filename>
this replaces the changes in your working tree with the last content in HEAD. Changes already added to the index, as well as new files, will be kept.

If you instead want to drop all your local changes and commits, fetch the latest history from the server and point your local master branch at it like this
git fetch origin
git reset --hard origin/master





## git commit
n Git, commit is the term used for saving changes.
Git does not add changes to a commit automatically. You need to indicate which file and changes need to be saved before running the Git commit command.
The commit command does not save changes in remote servers, only in the local repository of Git.


Staging in Git refers to a phase which includes all the changes you want to include in the next commit. Here are the steps leading to staging:

You make changes to a file in the working directory.
You use the Git add command to move those changes from the working directory to the staging area.
Git does not save changes yet. You need to run the Git commit command to move changes from the staging area to the local repository.
Additionally, you may use git status command to check the status of the files and the staging area. If changes are not staged for commit, they won't be saved.

Staging Changes
The Git add command moves changes to the staging area.

Here is a basic example of using add:

git add <file>

Git moves all changes of <file> in the staging area to wait for the next commit.

This example adds the entire <directory> to the staging area:

git add <directory>

During the Git add session, you can pick the changes you would like to commit. Before that, you need to start an interactive session:

git add -p

Use y to stage a specific portion.
Use n to ignore a specific portion.
Use s to divide the portion into smaller parts.
Use e to edit the portion manually.
Use q to exit the interactive session.
Committing Changes
Git commit command takes a snapshot representing the staged changes.

git commit

After running the Git commit command, you need to type in the description of the commit in the text editor.

This Git commit example shows how you set the description with the commit function:

git commit -m "<message>"

The following example shows how to save a snapshot of changes done in the whole working directory. This code only works for tracked files.

git commit -a

Pushing Changes to Remote Servers
Git push command moves the changes from the local repository to a remote server.

This example creates a local branch in the remote repository, including all specified commits and objects:

git push <name of remote server> <branch name>

The following example pushes changes even if it does not end in a non-fast-forward merge. Beginners should not use this option:

git push --force

This example adds all local branches to the indicated remote repository:

git push --all

The following example pushes all local tags to the remote:

git push --tags

Note: the Git push command makes sure that you share your changes with remote colleagues.


### git commands

git init: Initializes a new Git repository. Until you run this command inside a repository or directory, it’s just a regular folder. Only after you input this does it accept further Git commands.

git config: Short for “configure,” this is most useful when you’re setting up Git for the first time.

git help: Forgot a command? Type this into the command line to bring up the 21 most common git commands. You can also be more specific and type “git help init” or another term to figure out how to use and configure a specific git command.

git status: Check the status of your repository. See which files are inside it, which changes still need to be committed, and which branch of the repository you’re currently working on.

git add: This does not add new files to your repository. Instead, it brings new files to Git’s attention. After you add files, they’re included in Git’s “snapshots” of the repository.

git commit: Git’s most important command. After you make any sort of change, you input this in order to take a “snapshot” of the repository. Usually it goes git commit -m “Message here.” The -m indicates that the following section of the command should be read as a message.

git branch: Working with multiple collaborators and want to make changes on your own? This command will let you build a new branch, or timeline of commits, of changes and file additions that are completely your own. Your title goes after the command. If you wanted a new branch called “cats,” you’d type git branch cats.

git checkout: Literally allows you to “check out” a repository that you are not currently inside. This is a navigational command that lets you move to the repository you want to check. You can use this command as git checkout master to look at the master branch, or git checkout cats to look at another branch.

git merge: When you’re done working on a branch, you can merge your changes back to the master branch, which is visible to all collaborators. git merge cats would take all the changes you made to the “cats” branch and add them to the master.

git push: If you’re working on your local computer, and want your commits to be visible online on GitHub as well, you “push” the changes up to GitHub with this command.

git pull: If you’re working on your local computer and want the most up-to-date version of your repository to work with, you “pull” the changes down from GitHub with this command.