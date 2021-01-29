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

## <a id="differenceBetween"></a> What is Git?

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

## All of this, however, is currently just on your local computer.

### We need to share our versions with others--that's where GitHub and GitLab come in.

---

## <a id="differenceBetween"></a> What is the difference between Git / GitHub / GitLab?

### GitHub and GitLab are basically Google Drive for Git Trees (repos).

### GitHub and GitLab host your Git Tree, allowing others to access it.

### GitHub and GitLab are two different groups, however. So it might be easier to think of one as DropBox and the other as Google Drive.

---

## <a id="lifeCycle"></a> What is the Git Life Cycle?

Working on this part.

---

## <a id="createRepo"></a> Creating GitHub Repos

Working on this part.

---

## <a id="basicCommands"></a> Basic Git Commands

### Checking to see the current status of git

```
git status
```

<img src="./assets/imgs/command_gitStatus.PNG">

Green: Files that have been added

Red: Files that have not been added

---

### Checking to see if you need to git pull / git fetch

```
git remote show origin
```

| **You do not need to pull ("Up to Date")**                      | **You need to pull ("Out of Date")**                              |
| --------------------------------------------------------------- | ----------------------------------------------------------------- |
| <img src="./assets/imgs/command_remoteShowOrigin_upToDate.PNG"> | <img src="./assets/imgs/command_remoteShowOrigin_needToPull.PNG"> |

---

## <a id="classGitLab"></a> Pulling From the Class GitLab

Working on this part.

---

## <a id="troubleshooting"></a> Common Git Problems

Working on this part.
