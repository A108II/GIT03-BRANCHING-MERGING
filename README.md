# Git branching and merging

### Git branching
- Initialize git with `git init`, Create a file, and make 3 commits: 
`git add .`, `git commit -m "<message>"`
- If we found out there is a bug in the website, and at the same we're working on a new feature, we can make a copy of the version history and continue to work on the new feature, at the same time we can work to solve the bug in the main git history, the idea of working on a copied version of the commit history is called branching. This way working on a new feature and fixing bug doesn't clash with each other.  
- To achieve this, we first need to create a branch:
`git branch <name>` => `git branch feature1`
-  Using `git log --all --graph`, we'll see the branch name which is feature1 `(HEAD -> master, feature1)`. This means we're still in the master branch.
- Now, we want to make commits on a copied branch we've created, and add a new feature on it. For this we need to switch into the feature1 branch to achieve this:
`git checkout feature1`, if we use `git log --all --graph` we'll see 
`(HEAD -> feature1, master)`, this means we're currently in the feature1 branch, HEAD is pointing to the feature1 branch. 
- Create a file named `feature1` and commit.
- Now, one of senior devs comes and says that we need to fix a bug for this website, now we need to switch back to the previous branch (master branch). We use this command to switch back to the master branch: `git checkout master`, we can check it whether it worked or not by `git log --all --graph` and we can see that HEAD points to master. 

- Now create a file named `bugFix`, and then commit. If we run this command `git log --all --graph`, we'll see the master and feature1 branches.

### Git merging 

- At the end, we want to merge the changes we've made both in the master branch and in the feature1 branch. Merging helps us to pick the changes, and combine them together. 

- Switch to the feature1 branch: 
`git checkout feature1`, go to `feature1` file and then type `feature done`, pick the changes `git add .`, and commit `git commit -m "Feature done"`

- Now working on a feature is done and we need to merge the feature1 branch and master branch. 

- When we merge branches together, the result will be in the current branch that we're working on. For example here if we merge master and feature1 branch, the merge will happen in the feature1 branch(current branch), and it's going to be another commit on top of the feature1. 

- In a company, teams usually use the master branch as a main or final copy of the code, that's why we need to merge all the changes while we’re in the master branch. and not any other branches. 

- Now we need to switch back to the master branch using this command line: `git checkout master`

- Merge feature1 into the master branch (current branch), `git merge feature1 -m "Merge Feature1"`, the result will be saved on a new commit. `git log --all --graph` to see the result.

- Now the final copy of the code both has the bug fix and new features. 
