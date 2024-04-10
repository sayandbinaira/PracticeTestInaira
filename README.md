# PracticeTestInaira
## Pre-requisites
1. [For git installation](https://learn.microsoft.com/en-us/devops/develop/git/install-and-set-up-git)
2. [Git bash for microsoft](https://www.gitkraken.com/blog/what-is-git-bash)

## Tutorial
The aim of this section is to give hands on experience in git. 
### Cloning a repository
1. Open git bash or terminal
2. Traverse to the folder, where you want to clone the repository, using cd command
```
cd <folder path>
```
3. Clone this repo using git clone command
```
git clone <repo link>
```
4. Repo link can be found here
<img width="313" alt="Screenshot 2024-04-09 123641" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/895e28a3-9b25-4a91-9d0c-f010349715dc">

### Branch operations
1. For viewing all the branches in local
```
git branch
```
2. For creating new branch
```
git checkout -b <new branch name>
```
3. For changing the branch
```
git checkout <branch name>
```
4. For deleting a branch locally
```
git branch -d <branch name>
```
5. For deleting a branch remotely
```
git push origin --delete <branch name>
```

### Commit a change
1. Open the repo in local using any python IDE
2. Open the terminal from IDE
3. Checkout a new branch with your name from main using checkout -b command
```
git checkout -b <yourname>
```
4. In the file practice.py add a print statement with your name
```
print("First print statement")
```
5. To check which files or their changes are being tracked by git use the below command
```
git status
```
 - File path in red indicates that these files or their changes are not tracked by git (unstaged files)
   <img width="431" alt="unstaged" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/8082ac16-e04c-4b7b-b9db-185c890ac0af">

 - File path in green indicates that these files or their changes are tracked by git but not yet commited (staged files)
   <img width="332" alt="staged" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/400a8cf8-333b-4aa8-a350-10dcb81e4ed2">

It displays file paths that have differences between the index file and the current HEAD commit.

6. For adding practice.py to staged area use the below command
```
git add <unstaged file path>
```
In our example -  
```
git add practice.py
```
This is a pre-requisite step for comitting your changes


7. For committing files use the below command
```
git commit -m "<Your message>"
```
In our example - 
```
git commit -m "First commit by yourname"
```

### Push Pull
1. After the commit for pushing the changes to remote repo use the below command
```
git push origin <yourname>
```
2. Checkout to main branch using the below command
```
git checkout main
```
3. For pulling the changes from remote branch to your main branch in local use the below command
```
git pull origin main
```

### Merging a branch and committing it
1. Checkout to your branch <yourname>
2. Create a new branch from your branch <yourname> with name dummyBranch
3. In the file practice.py add a print statement
```
print("New print statemnt in new branch")
```
4. Add the file practice.py to staging area and commit the changes
5. Checkout to your original branch <yourname>
6. Check all your commits with the below command
```
git log
```
7. Type q to exit the log here
<img width="388" alt="qExit" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/d3956af4-5cbf-47c4-97f5-fb30395a28ee">

9. Merge the branch dummyBranch to <yourname> using the below command
```
git merge dummyBranch
```
10. Again when you check all the commits, one can see the commit of dummyBranch in branch <yourname>


   
