# git-basic-commands

**Tell Git who you are**	
Configure the author name and email address to be used with your commits.

Note that Git strips some characters (for example trailing periods) from user.name.
```bash
git config --global user.name "Akshay Sharma"

git config --global user.email akshay@example.com
```
**Create a new local repository**

```bash 	
git init
```

**Check out a repository**

Create a working copy of a local repository:
```bash
git clone /path/to/repository
```
For a remote server, use:	

```bash
git clone username@host:/path/to/repository
```

**Add files**

Add one or more files to staging (index):	
```bash
git add <filename>
```
Add all files to staging area:
```bash
git add *
```

**Commit**

Commit changes to head (but not yet to the remote repository):	
```bash
git commit -m "Commit message"
```
Commit any files you've added with git add, and also commit any files you've changed since then:	
```bash
git commit -a
```

**Push**

Send changes to the master branch of your remote repository:	
```bash
git push origin master
```
**Status**	
List the files you've changed and those you still need to add or commit:	
```bash
git status
```
**Connect to a remote repository**

If you haven't connected your local repository to a remote server, add the server to be able to push to it:

```bash
git remote add origin <server>
```

List all currently configured remote repositories:	
```bash
git remote -v
```

**Branches**

Create a new branch and switch to it:	
```bash
git checkout -b <branchname>
```
Switch from one branch to another:	
```bash
git checkout <branchname>
```
List all the branches in your repo, and also tell you what branch you're currently in:	
```bash
git branch
```
Delete the feature branch:	
```bash
git branch -d <branchname>
```
Delete branch from GitHub
```bash
git push origin <branchname> --delete
```
Push the branch to your remote repository, so others can use it:	
```bash
git push origin <branchname>
```
Push all branches to your remote repository:	
```bash
git push --all origin
```
Delete a branch on your remote repository:	
```bash
git push origin :<branchname>
```
**Update from the remote repository**

 

Fetch and merge changes on the remote server to your working directory:	
```bash
git pull
```
To merge a different branch into your active branch:	
```bash
git merge <branchname>
```
View all the merge conflicts:

View the conflicts against the base file:

Preview changes, before merging:
```bash
git diff


git diff --base <filename>

git diff <sourcebranch> <targetbranch>
```
After you have manually resolved any conflicts, you mark the changed file:	
```bash
git add <filename>
```
**Remotes**

Remotes are useful for tracking repositories which are present on multiple Git
servers(such as Github, Bitbucket, etc.)
You can add multiple remote URLs
```bash
git remote add upstream <url>
```
Similarly, you can remove added remotes, such as:
```bash
git remote remove upstream
```

**Tags**

You can use tagging to mark a significant changeset, such as a release:	
```bash
git tag 1.0.0 <commitID>
```
CommitId is the leading characters of the changeset ID, up to 10, but must be unique. Get the ID using:	
```bash
git log
```
Push all tags to remote repository:	
```bash
git push --tags origin
```

**Undo local changes**

If you mess up, you can replace the changes in your working tree with the last content in head:

Changes already added to the index, as well as new files, will be kept.
```bash
git checkout -- <filename>
```

Instead, to drop all your local changes and commits, fetch the latest history from the server and point your local master branch at it, do this:	
```bash
git fetch origin

git reset --hard origin/master
```
**Search**

Search the working directory for foo():
```bash
git grep "foo()"
```
