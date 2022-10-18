## Git and Github
### This is Docker Assignments 

### Task 1
- Demonstrate minimum 15 basic Git command with explanation and screenshot.
```git
1. Execute below Tasks 
- Create Repo on GitHub
- Add Assignment1.md file
- Run below Git commands 

```
#### GIT Commands

> 1. Create empty Git repo in Industry_Ready_projects directory
```
git init
```

> 2. Define the author name to trach who done the changes for all commits by the this user.
```
git config --global user.name "Shivam Jha"*
```

> 3. Define the author email to be used for all commits by the current user
```
git config --global user.email "shivamjhads@gmail.com"
```

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_02.png)


> 4. List to check which files are staged, unstaged, and untracked.
```
git status
```

> 5. Stage all changes for the commit
```
git add .
```

> 6. Commit the staged file
```
git commit -m "Ceate folder and file" 
```

> 7. Push to main branch to remote server, with necessary commits. 
```
git push -u origin main 
```

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_01.png)


> 8. Show commit logs. 
```
git log
```

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_03.png)


> 9. git log patch command displays the files that have been modified and also shows the location of the added, removed, and updated lines.
```
 git log -p 
```

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_04.png)

> 10. `(HEAD -> main, origin/main)` This is the haed of all the changes we have made
```
git log
```

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_11.png)


> 11. This list all of the branches in repo and also this command is to add a <branch> argument to create a new branch with the name <Feature-1>.
```
git branch
```
```
git branch Feature-1
```

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_05.png)

> 12. Create and check out a new branch named <branch>. Drop the -b flag to checkout an existing branch to Feature-2.
```
git checkout -b Feature-2
```
```
git checkout Feature-2
```

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_08.png)


> 13. Show unstaged changes between index and working directory. 
```
git diff
```

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_06.png)
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_07.png)

> 14. If we run the git log command and we want to look at the differences between our current file and one of the vesrions let suppose `commit 4156ca5fe2ebc69acb07f14aacc4eb4840fbbb13` This will tell is all the diffrences between this versio a nd current version of the file
```
git diff 4156ca5
```

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_09.png)
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_10.png)

> 15. What if we make a misatake/changes which we don't want to do or accidentaly added or removed something from file.
* Reset staging area to match most recent commit,but leave the working directory unchanged.
* Reset staging area and working directory to match most recent commit and overwrites all changes in the working directory.
* Reset the staging area to match, but leave the working directory alone.
* Same as previous, but resets both the staging area & working directory to match. Deletes uncommitted changes, and all commits after <commit>.
```
git diff --staged
git reset Git_GitHub/Assignment-1.md
```
```
git revert
```

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_12.png)

> 16. What if we commited the wrong changes  ?
* `git revert` as a tool for undoing committed changes, while `git reset HEAD` is for undoing uncommitted changes.

[detailed_explaination](https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting#:~:text=You%20can%20also%20think%20of,lost%20during%20the%20revert%20operation)

> 17. git merge `Feature-1` or git merge `Feature-2` This will merge `Feature-1` or `Feature-2` into the current `main` branch
```
git merge `Feature-1`

git merge `Feature-2`
```

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_14.png)


> 18. GIT PUSH
* `git push <remote> --all`  Push all of your local branches to the specified remote.
* `git push <remote> --force` don't run `--force` command if not sure this will force the git to push even if it results in a non-fast-forward merge. 
```
git push -u origin --all
```

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_15.png)


> 19. GIT PULL - Fetch the remote’s copy of current branch and rebases it into the local copy. Uses git rebase instead of merge to integrate the branches.
```
git pull --rebase origin main
```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_16.png)

### Task 2 
- Consider that your want to start an open-source project in your organization. Perform all the standard operation to create a repository with minimal permision for all the users. It should contain.
1. Proper open source structure 
2. Proper Readme
3. Add 2 collaborator 
4. Host GitHub Pages using settings (Designed to host your personal, organization, or project pages from a GitHub repository)

#### Solution
> 1. Setting Up An Open Source Project
```
https://github.com/jhashivam/Industry_Ready_projects/tree/main/OpenSourceProjectRepo

```

> 2. Proper Readme
```
https://github.com/jhashivam/Industry_Ready_projects/blob/main/OpenSourceProjectRepo/README.md
```

> 3. Add 2 collaborator 


![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_17.png)



> 4. Host GitHub Pages using settings (Designed to host your personal, organization, or project pages from a GitHub repository)
```
    https://github.com/jhashivam/shivamjha.github.io

```
### Task 3 
1. Create a Issue in your github repository.

```
https://github.com/jhashivam/Industry_Ready_projects/issues/1
```

2. Raise a pull request.
```

```
3. Merge A pull request.
4. Reject a pull request with proper comments.
5. Add a Dependabot alerts in your github.(for above cases)
6. Stash changes
7. Create a release your package
8. Setup a Projects Board for your project.