# PracticeTestInaira
## Pre-requisites
1. [For git installation](https://learn.microsoft.com/en-us/devops/develop/git/install-and-set-up-git)
2. [Git bash for microsoft](https://www.gitkraken.com/blog/what-is-git-bash)

## Contents
1. [Git Basic commands](https://github.com/sayandbinaira/PracticeTestInaira/edit/main/README.md#git-basic-commands-1)
2. [Getting Started](https://github.com/sayandbinaira/PracticeTestInaira/edit/main/README.md#tutorial)
3. [Challenges](https://github.com/sayandbinaira/PracticeTestInaira/edit/main/README.md#challenges)
   
## [1] Git Basic commands
1. Configuring git to add name 
```
git config --global user.name <your full name>
```
2. Configuring git to add email 
```
git config --global user.email <your email>
```
3. To check the configuration
```
git config --global --list
```
4. For cloning a remote repo to local
```
git clone <repo link>
```
5. For moving changes from working area to staging area we need to add the recently changed files in working area - 
```
git add <working area file path>
```
6. For committing files use the below command
```
git commit -m "<Your message>"
```
7. For viewing all the branches in local
```
git branch
```
8. For creating new branch
```
git checkout -b <new branch name>
```
9. For changing the branch
```
git checkout <branch name>
```
10. For deleting a branch locally
```
git branch -d <branch name>
```
11. For deleting a branch remotely
```
git push origin --delete <branch name>
```
12. For ammending a commit
```
git commit --amend -m "<Your message>"
```
13. For checking all the commits in a branch
```
git log
```
14. For pushing a commit to remote repo
```
git push origin <branch-name>
```
15. For pulling commits from a branch in remote repo to local repo
```
git pull origin <branch-name>
```
16. Merging a branch to your current branch
```
git merge <branch-name>
```
17. Rebasing a branch to your current branch
```
git rebase <branch-name>
```
18. Interactive rebasing for squashing commits
```
git rebase -i HEAD~n
```
One can choose which commits to be squashed. For more details check the [Interactive Rebasing](https://github.com/sayandbinaira/PracticeTestInaira/edit/main/README.md#25-interactive-rebasing) section in Getting Started.
To rebase till a particular commitId - 
```
git rebase -i <commitId>
```

19. To check which files or their changes are being tracked by git use the below command
```
git status
```
 - File path in red indicates that these files or their changes are not tracked by git (unstaged files)
   
   <img width="431" alt="unstaged" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/8082ac16-e04c-4b7b-b9db-185c890ac0af">

 - File path in green indicates that these files or their changes are tracked by git but not yet commited (staged files)
   
   <img width="332" alt="staged" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/400a8cf8-333b-4aa8-a350-10dcb81e4ed2">

It displays file paths that have differences between the index file and the current HEAD commit.

20. For undoing all the changes made between where HEAD was pointing and the specified commit let's say commitId, and saving all the changes in the staging area perform soft reset
```
git reset --soft <commitId>
```
The changes will still be there in staging area but only commits will be removed till commitId. 
One can also do a soft reset between HEAD and the last nth commit from HEAD using the below command
```
git reset --soft HEAD~n
```
21. For undoing all the changes made between where HEAD was pointing and the specified commit let's say commitId, and preserving changes in the Working Directory, as unstaged changes perform mixed reset
```
git reset --mixed <commitId>
```
The changes will in the working directory and commits will be removed till commitId. this is the default mode of git reset. 
One can also do a mixed reset between HEAD and the last nth commit from HEAD using the below command
```
git reset --mixed HEAD~n
```
22. For undoing all the changes made between where HEAD was pointing and the specified commit let's say commitId and to also discarding all the changes in the staging area perform hard reset
```
git reset --hard <commitId>
```
HEAD will be pointing to commitId.
One can also do a hard reset between HEAD and the last nth commit from HEAD using the below command
```
git reset --hard HEAD~n
```
    

## [2] Getting Started
The aim of this section is to give hands on experience in git. 
### 2.1 Cloning a repository
1. Open git bash or terminal
2. Traverse to the folder, where you want to clone the repository, using cd command
```
cd <folder path>
```
3. Clone this repo using git clone command
```
git clone <repo link>
```
4. Repo link can be found by clicking on code
<img width="313" alt="Screenshot 2024-04-09 123641" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/895e28a3-9b25-4a91-9d0c-f010349715dc">


### 2.2 Commit a change
1. Open the repo in local using any python IDE
2. Open the terminal from IDE
3. Checkout a new branch with your name from main using checkout -b command
```
git checkout -b yourname
```
4. In the file practice.py add a print statement with your name
```
print("First print statement by <yourname>")
```
5. To check which files or their changes are being tracked by git use the below command
```
git status
```
6. For adding practice.py to staged area use the below command
```
git add practice.py
```
This is a pre-requisite step for comitting your changes


7. Commit the changes added in staging area
```
git commit -m "First commit by yourname"
```

### 2.3 Push Pull
1. After the commit for pushing the changes to remote repo use the below command
```
git push origin yourname
```
2. Checkout to main branch using the below command
```
git checkout main
```
3. For pulling the changes from main branch in remote rep to your main branch in local use the below command
```
git pull origin main
```

### 2.4 Merging a branch 
1. Checkout to your branch yourname
2. Create a new branch from your branch <yourname> with name dummyBranch
3. In the file practice.py add a print statement
```
print("New print statemnt in new branch")
```
4. Add the file practice.py to staging area and commit the changes
5. Checkout to your original branch yourname
6. Check all your commits with the below command
```
git log
```
7. Type q to exit the log here
<img width="388" alt="qExit" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/d3956af4-5cbf-47c4-97f5-fb30395a28ee">

8. Merge the branch dummyBranch to yourname using the below command
```
git merge dummyBranch
```
9. Again when you check all the commits, one can see the commit of dummyBranch in branch yourname

### 2.5 Interactive Rebasing 
1. Create three dummy commits in branch yourname
2. Do a git rebase using the below command
```
git rebase -i HEAD~3
```
3. This will open a text editor listing all of the commits that are about to be moved like this below

   <img width="344" alt="rebaseCommits" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/97f9d5c4-8af6-4ae5-a9de-7768011a5b81">

4. Press I to go into insert mode in text editor in terminal
5. Choose which commits to be squashed
   
   <img width="551" alt="rebaseSquashPick" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/7db0ed78-35c9-4151-a0d2-e40485bdf549">

6. Press Ctrl + C and then type the below command to save and quit the text editor in terminal
```
:wq
```
7. One can check the commits now using git log

### 2.6 Raising a Pull Request
1. In the github repo, go to pull requests
<img width="784" alt="PR" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/dc698550-4efc-478d-8116-3d583787855f">

2. Click on new pull request
   
<img width="726" alt="NewPR" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/5ae60847-5719-4f18-8a08-ab0494ab4bf9">

3. Choose the branch that you want to merge in compare and the base branch in which you want to merge. In this case compare branch will be yourname and base branch will be main
<img width="731" alt="CompBaseBranch" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/65e25220-95f2-4ab2-abdc-f9188d1c1eee">

4. Create a pull request by clicking on Create Pull Request. (If there are no diff between two branches then this button will be disabled)
   
<img width="768" alt="CreatePR" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/138f3e85-9ce3-4918-a411-4fb983f017a7">

5. One can add reviewers to the pull requests by clicking on gear icon on right hand side of reviewers

<img width="246" alt="ReviewersPR" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/45fb0816-06fa-43f4-ba5f-77b551ffa8e6">

6. Click on merge pull requests

<img width="500" alt="MergePR" src="https://github.com/sayandbinaira/PracticeTestInaira/assets/137031724/43d708b1-1fc9-4177-9320-e77a4b3f52f4">

7. Now you can delete your branch using the below command
```
git push origin --delete yourname
```
## [3] Challenges
### 3.1 Diverging branches
This arises when a branch say  have diverged from a commit say X in local and remote. It looks something like this:
```
a - b - c - d - e
        \       ^ LOCAL
         -- f 
            ^ REMOTE
```
To know more about this refer the doc [Dealing with diverged git branches](https://jvns.ca/blog/2024/02/01/dealing-with-diverged-git-branches/)
### 3.2 Merge conflict
Conflicts generally arise when two people have changed the same lines in a file, or if one developer deleted a file while another developer was modifying it. In these cases, Git cannot automatically determine what is correct. Conflicts only affect the developer conducting the merge, the rest of the team is unaware of the conflict. To know more about this refer the doc [Git merge conflicts](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts)
## References
1. https://www.atlassian.com/git/tutorials/merging-vs-rebasing
2. https://www.atlassian.com/git/glossary#commands
3. https://confluence.atlassian.com/bitbucketserver/basic-git-commands-776639767.html
4. https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase#:~:text=From%20a%20content%20perspective%2C%20rebasing,them%20to%20the%20specified%20base.
5. https://jvns.ca/blog/2024/02/01/dealing-with-diverged-git-branches/
6. https://git-scm.com/
7. https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration
8. https://git-scm.com/docs/git-config
