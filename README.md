# **Basics of Git**

<img src="./assets/imgs/banner.png">

## Ultimately, Mark and Richie reached an agreement: They would code Richie's "Million Dollar Idea" if Richie himself coded it. Mark has agreed to proofread Richie's code throughout the process.

## And you know what that means....

# CODE COLLABORATION!

### **Our team?** Two idiots--Richie Rich and Mark--and their (tax deductable) Keurig Coffee machine.

### **Our task allotments?**

<img src="assets/imgs/whyGit_Assignments.png">

### **Our problem?**

<img src="assets/imgs/whyGit_how.png">

## HOW DOES RICHIE GET THE DATA HE NEEDS FROM MARK???

### And--furthermore--how does Mark correct Richie's code throughout the process?

# The Answer? Git.

### **NOTE:** Normally the solution involves a data pipeline, a data warehouse / lake, and multiple analysts. However, our team is two idiots and their coffee machine so we're simplifying the solution quite a bit.

<img src="assets/imgs/whyGit_normally.png">

---

# What is Git?

### Git is a **version control program**. This is what you have on your computer.

### Git keeps track of changes you make to files within a folder (also called a **directory** or **repository**).

### To make git watch files within a folder, navigate to that folder in Terminal (Mac) / GitBash (Windows):

<img src="assets/imgs/whatIsGit_pathCheck.PNG">

### **MAKE SURE YOUR CURRENT LOCATION (RED) IS THE FILE YOU WANT GIT TO TRACK**

### Then run the command:

```
git init
```

### If you then run the command:

```
ls -a
```

### ...you should see that git created a file to track changes in this folder (and in all the sub-directories\* you create within this folder)

\* Sub-directories are a folder within a folder

<img src="assets/imgs/whatIsGit_gitFile.PNG" >

### This file keeps track of **all changes you commit (give) to it** like this:

<img src="assets/imgs/whatIsGit_tree.png">

### This structure is referred to as a "Tree".

### Git saves all versions of a file together as a **Binary Large OBject (BLOB)**.

\***\*Side Note:** This is why gitHub urls have the word "blob" in them.\*\*

<img src="assets/imgs/whatIsGit_blob.PNG">

## All of this, however, is currently just on your local computer.

### We need to share our versions with others--that's where GitHub and GitLab come in.

---

# What is the difference between Git / GitHub / GitLab?

### GitHub and GitLab are basically Google Drive for Git Trees (repos).

### GitHub and GitLab host your Git Tree, allowing others to access it.

### GitHub and GitLab are two different groups, however. So it might be easier to think of one as DropBox and the other as Google Drive.

---

# Creating a Team Repo

### Only one team member needs to create the Git Repo.

<img src="assets/imgs/lifeCycle_createRepo.png">

### After the Repo has been created, it can be cloned by all team members.

### You'll need to get the url

<img src="assets/imgs/lifeCycle_getURL.png">

### And use this command (replace ??? with the URL you got):

```
git clone ???
```

<img src="assets/imgs/lifeCycle_clone.png">

## _IMPORTANT_ Cloning a repo automatically does git init for you

### You will find the .git file with the folder created by git clone

## Any files you add outside of the folder created by git clone will not be tracked by the .git file

### **Remote Repo** The repo on GitHub. This is where the whole team takes their code from.

**NOTE:** Ideally the code on the GitHub repo should always be working. Team members should not add their code to the Remote Repo until the code works on their computer

### **Local Repo** The copy of the repo that each team member has their computer.

---

# Adding Changes Made on Local Repo to the Remote Repo

## Richie is waiting on Mark's code to start coding! How do we move the files from Mark's **local repo** to the **remote repo**?

### This requires three steps:

<img src="assets/imgs/lifeCycle_localToRemote.png">

### FILE

This is the actual code that Mark wrote.

The .Git file in the million-dollar-idea folder won't track Mark's code unless we tell it to--and this is a two step process.

### STAGED

It's best to think of STAGED as an empty box.

If we want our .Git file to track changes, we need to add it to this box.

We can check which files / changes are in this box by using the git status command:

```
git status
```

<img src="./assets/imgs/command_gitStatus.PNG">

Green: Files that have been added

Red: Files that have not been added

To add files to our box (to stage files) we need to use the git add command:

```
git add ???
```

If we want to add all the red files to our box, we can use the git add command with a '.' instead of a file name:

```
git add .
```

### .GIT

Now that all the files are in our box, we just have to slap some tape on and deliver it to the .git file.

We can do that with the commit -m command.

**NOTE:** If you forget to add -m, git will try to get you to add a message using a code editor.

```
git commit -m "Add Message Here"
```

We add these messages for two reasons:

- So our team can easily see what we added to the code

- So it is easier to remember what version of the code we are on in case we need to revert back to it later.

If you run git status after commiting, you will see all the files have disappeared. This is because you have delivered them to the .git file.

You will also see:

```
git push origin main
```

<img src="assets/imgs/lifeCycle_remoteToLocal.png">

---

# Basic Git Commands

# Checking to see if you need to git pull / git fetch

```
git remote show origin
```

| **You do not need to pull ("Up to Date")**                      | **You need to pull ("Out of Date")**                              |
| --------------------------------------------------------------- | ----------------------------------------------------------------- |
| <img src="./assets/imgs/command_remoteShowOrigin_upToDate.PNG"> | <img src="./assets/imgs/command_remoteShowOrigin_needToPull.PNG"> |

---

# Pulling From the Class GitLab

Working on this part.

---

# Common Git Problems

Working on this part.
