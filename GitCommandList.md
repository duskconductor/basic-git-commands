<img src="./assets/imgs/banner.png">

# Git Command Cheat Sheet

<a href="README.md" target="_blank">Git at Work</a> | **Git Cheatsheet** | <a href="CreatingTeamRepo.md" target="_blank">Git Creating Team Repo</a> | <a href="GitHubAndRecruiters.md" target="_blank">GitHub and Recruiters</a> | <a href="PullingFromClassGitLab.md" target="_blank">Pulling from Class GitLab</a>

---

# General Terminal GitBash Commands

## Useful commands for terminal / gitBash: 

See all files in current folder (ls stands for list):

```
ls
```

See all files--including hidden files like .git--in the current folder:

```
ls -a
```

Change directories/folders (replace ??? with the name of the folder) (cd stands for change directory):

```
cd ???
```

Go back into previous directory/folder:

```
cd ..
```

Open current folder in VSCode (if this doesn't work for you, you'll need to <a href="https://stackoverflow.com/questions/29971053/how-to-open-visual-studio-code-from-the-command-line-on-osx" target="_blank">add the shell command</a>):
```
code .
```

Get the current path (pwd stands for print working directory):

```
pwd
```

Get all previously used commands:
```
history
```

Clear terminal screen:
```
clear
```

**You can always press up arrow on the terminal to retrieve your last command and edit it**

---

# Creating Repo

## If you have a folder with files that you want to add to an empty GitHub repo:

```
git init
```

Replace ??? with the Empty GitHub Repo URL / GitHub Repo URL

```
git remote add origin ???
```

To see if the remote was set up properly you can do:

```
git remote -v
```

You should see origin for both fetch and push.

**Remote is basically just the link to your remote repository (your GitHub repo) and is used when pushing / pulling from your local repository (your computer). You can name it anything but the default / standard is usually 'origin'**

---

## If you want to copy an existing GitHub repo onto your computer

Replace ??? with the Remote Repo URL / GitHub Repo URL

```
git clone ????
```

(This will do `git init` and `git remote add orgin` for you, so you do not have to)

---

---

# Adding Changes from your computer (Local) to GitHub (Remote)


## Adding Changes From Local Repo (Our Computer) to Remote Repo (GitHub)

<img src="./assets/imgs/lifeCycle_localToRemote.png">

### Checking to see which changes need to be moved to staged

```
git status
```

<img src="./assets/imgs/command_gitStatus.PNG">

> **Red** This was changed and needs to be added to staged
>
> **Green** This was changed and HAS BEEN added to staged

### File -> Staged

Replace ???? with a file name (main.py) or .

git add . will add all changes

```
git add ???
```

### Staged -> Local .Git file

Replace ??? with an explanation of your changes.

Remember, recruiters will read your commit messages.

```
git commit -m "???"
```

### Local .Git file -> GitHub (Remote Repo)

```
git push origin main
```

**origin** is the name of the remote (Remote Repo URL)

**main** is the name of the branch

---

---

# Pulling Changes from Remote Repo (GitHub) to our Local Repo (Computer)

## Remote Repo (GitHub) to Local Repo (Our Computer)

<img src="assets/imgs/lifeCycle_remoteToLocal.png">

<img src="assets/imgs/lifeCycle_pullVFetch.png">

---

### Git Fetch, Diff, Merge

**Storing the Current Remote Repo in our Temporary Storage (Not Computer)**

```
git fetch
```

**Checking to see if Merging the Remote Repo with our repo will cause problems**

```
git diff ...origin
```

**Adding the Remote Repo changes to our Local Repo**

```
git merge
```

---

### Git Pull (Git Fetch + Git Merge)

**Adds Remote Repo changes to our Local Repo without checking if it will cause problems**

```
git pull
```

---
---

# Branches

### Seeing which branch I'm on / Seeing all branches on my local repo

The one I'm on will be indicated with a star.

```
git branch
```

### Seeing all the branches on my remote repo (GitHub)

```
git branch -r 
```


### Creating a new branch and switching to it

Replace ??? with the name of the new branch

```
git checkout -b ???
```

### Switching to an existing branch (Works with remote branches)

Replace ??? with the name of the existing branch (**NOTE** This command does not have ```-b```)

```
git checkout ???
```

### Pushing to a branch

Depends on your global git settings. Typically, the first time you push to a branch, you'll need to do (replace ??? with branch name)

```
git push -u origin ???
```

After you've done this command once, however, you can simply do

```
git push origin ???
```

It's also possible to use

```
git push --set-upstream origin ???
```

But this particular command can often be wonky and takes longer to type

**Remember, after you push to a branch, you will need to do the following to add the code to main:**
> - [ ] Make a pull request from your branch to the main branch
> - [ ] Approve the pull request (either you or the person maintaining the main branch (maintainer))
> - [ ] Switch to the main branch on your local
> - [ ] ```git pull origin main``` on your main branch

**Also remember, branches are made to be deleted after merging (They're used to add small features to the main branch)**

---

---

# Possible Error

## Git will not let us pull because we made changes to files

<img src="./assets/imgs/pullError.PNG">

<img src="./assets/imgs/gitStash.png">

### Option 1 - Soft Reset

Soft reset will remove your local files from the commit--BUT NOT FROM YOUR COMPUTER. You'll then be able to pull from your remote.

**Note: ```git reset --hard HEAD~1``` will remove the files from your computer**

```
git reset --soft HEAD~1
```

(HEAD~1 is basically telling git to go back a commit and --soft is telling it "BUT DON'T DELETE THE FILES FROM MY LOCAL")

You'll then be able to ```git pull```.

(If not, try removing the files from staged:

```
git restore --staged ???
```

)

### Option 2 - FORCE PUSH

If there's nothing important on the remote (or if you've copied all the changes from the remote (GitHub) and added them to your local ) **and you're the only person working on this repo** you can go ahead and do a force push.

Force push basically tells git "I DON'T CARE WHAT'S ON THAT REPO, SLAP EVERYTHING FROM MY LOCAL ON THE REMOTE."

```
git push origin ??? --force
```

**Don't be that person who uses ```git push --force``` on a collab project, though. It'll make things harder for the people you're working with and therefore make things harder for you** 

(The reason for this being that the .git file keeps track of change history and you're basically overwriting the change history on the shared main repo. Meaning there will be problems for everyone elses' local git files since they don't have the history you've forced onto the main. Sometimes it's fine; other times it's the git-pocalypse. There's memes-a-plenty about this one.)

<img src="assets/imgs/gitPushForce.png">

### Option 3 - Git Stash

**IMPORTANT - This command will "delete" the files you've stashed until you pull the stash out again**

Saves our changes in a temporary storage outside of our local repo. Allows us to pull.

Replace ??? with a message that will help you find the stash later.

```
git stash save "???"
```

Then we will need to pull.

```
git pull
```

---

---

### Un-Committing staged (Removing something after `git add`-ing it)

Replace ??? with the file

```
git restore --staged ???
```
