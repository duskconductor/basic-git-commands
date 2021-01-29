<img src="./assets/imgs/banner.png">

# Git Command Cheat Sheet

<a href="README.md" target="_blank">Git at Work</a> | **Git Cheatsheet** | <a href="CreatingTeamRepo.md" target="_blank">Git Creating Team Repo</a> | <a href="GitHubAndRecruiters.md" target="_blank">GitHub and Recruiters</a> | <a href="GitTroubleShooting.md" target="_blank">Common Git Problems</a> | <a href="PullingFromClassGitLab.md" target="_blank">Pulling from Class GitLab</a>

## Adding a .Git file to a folder (Not needed when clone used)

```
git init
```

## Adding a remote (Remote Repo URL / GitHub Repo URL) to a .Git file (Not needed when clone used)

Replace ??? with the Remote Repo URL / GitHub Repo URL

```
git remote add origin ???
```

---

## Cloning a Repo

Replace ??? with the Remote Repo URL / GitHub Repo URL

```
git clone ????
```

> ## DO NOT DO BOTH GIT INIT AND GIT CLONE
>
> If you have a .Git file inside one folder and another .Git file inside of a folder inside that folder, it will cause problems.

---

---

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

## Git will not let us pull because we made changes to files

<img src="./assets/imgs/pullError.PNG">

<img src="./assets/imgs/gitStash.png">

### Git Stash

Saves our changes in a temporary storage outside of our local repo. Allows us to pull.

Replace ??? with a message that will help you find the stash later.

```
git stash save "???"
```

Then we will need to pull.

```
git pull
```
