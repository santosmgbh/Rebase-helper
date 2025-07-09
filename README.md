## Why use:
This is a utility command to facilitate the commands used when you are working on stacked PRs. 
For example: You have two PRs in Github:

- PR1:
  - master <- branch1
    - commit1
    - commit2
- PR2:
  - branch1 <- branch2
    - commit1
    - commit2
    - commit3
    
Your PR2 contains commits(commit1 and commit2) from PR1, but for the PR2 changes, it's only commit3. In this case, we want to clean the PR2 to have only the commit3. 
Manually we could do:
```
git checkout branch1;
git branch -D branch2;
git checkout -b branch2;
git cherry-pick commit3;
git push origin -f branch2;
```
This script is only to facilitate it.

## This command will:
#### 1. Get the base branch and rebased branch
#### 2. Update the base branch with the remote
#### 3. Remove the rebased branch locally
#### 4. Create a new cleaned rebased branch from the base branch
#### 5. Cherry pick all the commits provided.
#### 6. Force push the rebased branch to remote.

## How to use
- Copy this file to your machine
- I recommend adding to your zsh or any other prompt as a alias:
`alias @grebase="~/code/rebase.sh;"`
- Run the command:
`@grebase`
