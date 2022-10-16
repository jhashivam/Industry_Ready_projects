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
```
git diff --staged
git reset Git_GitHub/Assignment-1.md
```

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Git_GitHub/images/git_12.png)

> 16. What if we commited the wrong changes ?
   we can reset to previous head ex. `git reset HEAD~1 --soft` or `git reset HEAD~1 --mixed` 
  * soft - removes the commit but does not change to what happened in the stagging area. This doestnot change the content of file
    - 
```
git diff --staged
git reset Git_GitHub/Assignment-1.md
```

> 17. git merge `Feature-1` or git merge `Feature-2` This will merge `Feature-1` or `Feature-2` into the current `main` branch
```
git merge `Feature-1`

git merge `Feature-2`
```

> 18. Push to main branch to remote server, with necessary commits. 
```
git push -u origin main 
```

> 19. Push to main branch to remote server, with necessary commits. 
```
git push -u origin main 
```

> 20. Push to main branch to remote server, with necessary commits. 
```
git push -u origin main 
```

> 21. Push to main branch to remote server, with necessary commits. 
```
git push -u origin main 
```

> 22. Push to main branch to remote server, with necessary commits. 
```
git push -u origin main 
```

<<<<<<< HEAD
=======
> 23. Push to main branch to remote server, with necessary commits. 
```
git push -u origin main 
```

>>>>>>> e225021 (commit the changes  to  Assignment)
### Task 2 
- Consider that your want to start an open-source project in your organization. Perform all the standard operation to create a repository with minimal permision for all the users. It should contain.
1. Proper open source structure 
2. Proper Readme
3. Add 2 collaborator 
4. Host GitHub Pages using settings (Designed to host your personal, organization, or project pages from a GitHub repository)

### Task 3 
1. Create a Issue in your github repository.
2. Raise a pull request.
3. Merge A pull request.
4. Reject a pull request with proper comments.
5. Add a Dependabot alerts in your github.(for above cases)
6. Stash changes
7. Create a release your package
8. Setup a Projects Board for your project.