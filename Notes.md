### On GitHub, saved changes are called commits :

Core initial Commands

`git init`

`git add filename | git add .`

`git commit  -m "message"`

`git push -u origin main/master`

**To create a main branch:**

`git branch -M main`

To clone a repo from GitHub:

`git clone [url]`

To move/navigate to a branch:

`git checkout -b [branch name]`

`git pull origin main/master`

To add remote repo to local computer:

`git remote add origin [repository url]`

To check the remote version of the repo

`git remote -v`

Troubleshooting commands

___________________________________________________________________________________________

You can always use the reflog as well. git reflog  will display any change which updated the HEAD and checking out the desired reflog entry will set the HEAD back to this commit.

**Every time the HEAD is modified there will be a new entry in the reflog**

`git reflog`

`git checkout HEAD@{...}`

This will get you back to your desired commit

![https://i.stack.imgur.com/atW9w.png](https://i.stack.imgur.com/atW9w.png)

**git reset --hard <commit id>**

Move" your head back to the desired commit.

# This will destroy any local modifications.

# Don't do it if you have uncommitted work you want to keep.

`git reset --hard 0d1d7fc32`
# Alternatively, if there's work to keep:

`git stash`

`git reset --hard 0d1d7fc32`

`git stash pop`

# This saves the modifications, then reapplies that patch after resetting.

# You could get merge conflicts, if you've modified things which were

# changed since the commit you reset to.

## If you want to keep your changes associated with the detached HEAD

1. Run the following command

  `git branch tmp`

- this will save your changes in a new branch called tmp.

2. Run the following command

  `git checkout master`
  
3. If you would like to incorporate the changes you made into **master**, run the following command

 `git merge tmp`

from the **master** branch. You should be on the master branch after running
  
  `git checkout master`

_______________________________________________________________________________________________

**To update the branch:**

`git push --set-upstream origin master`

**To remove remote repository URL when troubleshooting**:

`git remote rm origin`

**When we face the following non-fast-forward issue, type the following rebase command:**

**! [rejected]        master -> master (non-fast-forward)**

`git pull --rebase origin master`

`git pull --rebase origin <name of the branch>`   to avoid non-fast-forward errors.

If there is an merge conflict, we can manually fix them on VS Code and then type following command

`git rebase --continue`

then we add the files and continue with rebase

`git add .`

`git rebase --continue`

If we want to skip this commit, type the following:

`git rebase --skip`

If we want to abort the whole rebase and go to the state before "git rebase"

`git rebase --abort`

Then we perform git push to submit the code

`git push -u origin master`

_______________________________________________________________________________________________

## This is important when git refuses to merge unrelated histories:

`git merge --allow-unrelated-histories branch-name-to-be-merged`

`git pull --allow-unrelated-histories origin master/main`

`git push -u origin master/main`

Alternately, We can solve this same merge conflict problem with following command  and this is the easier way 👇👇👇👇👇

## The “fatal: refusing to merge unrelated histories” Git error can be solved by this command:

`git pull origin master/main --allow-unrelated-histories`

_______________________________________________________________________________________________

# To Create a new repository on the command line:

`echo "# HTML-CSS-Practice" >> README.md`

`git init`

git add README.md

git commit -m "first commit"

git branch -M main

git remote add origin git@github.com:ImtiazVision/HTML-CSS-Practice.git

git push -u origin main

### Push an existing repository from the command line

git remote add origin git@github.com:ImtiazVision/HTML-CSS-Practice.git

git branch -M main

git push -u origin main

**To exist command line on windows**

press Esc

type ":wq" (without quotes)

Press Enter

**Commit messages capture the history of your changes, so other contributors can understand what you’ve done and why. It is basically used to  save your changes to the local repository**. Each commit has an associated commit message, which is a description explaining why a particular change was made.

### You can think of Commits as snapshots or milestones along the timeline of your Git project.

### They are created with the git commit command to capture the state of a project at that point in time.

### You should know that Git Snapshots are always committed to the local repository

### There are two important commit commands:

- **Git commit**
- **Git add**

### Now you’re ready to save a copy of the current state of the project, you make changes with git add. We stage a file for commit using git add command.

### After you’re satisfied with the made snapshot, you commit it to the project history with **git commit**.

- **We stage a file for commit via git add command | git add . will add all files**
- **We commit the file to the project history with git commit command**

### Local repositories reside on the computers of team members.

### If you're the only person working on your project, chances are you'll never need to set up a remote repository.

**We use remote repository to share data with our teammates. A remote repository in Git is a common repository that all team members use to exchange their changes. Every member can access the repository and make changes which everyone can access**. In most cases, such a remote repository is stored on a code hosting service like GitHub or on an internal server.

### Each developer will work in their local repository but eventually, they will push the code into a remote repository. Once the code is in the remote repository, other developers can see and modify that code. Now you have a local repository but want to convert it into a Remote repository. Lets see how.

### **First We need to initialize a repo by following command:**

- **git init**

**After creating a new repository on GitHub, we can follow these steps:**

### **Step 1**:

### After creating a repository on GitHub, you will get a URL for your repository.

### Copy that URL.

### **Step 2**:

### Now to point your local repository to the remote repository, use the following command:

git remote add origin [repository url]

### In order to push all the code from the local repository into the remote repository, use the following command:

git push -u origin master

### This pushes the code from the master branch in the local repository to the master branch in the remote repository.

**Branching**

### What if Rob made some changes in the script and the next day Sam erased those changes to make his new update?

### This is going to be a big cause of anger for Rob when he gets to know.

### How are they gonna solve this problem?

### You must be aware of the word branch or branching.

### Branch in general, means either a large or a small division.

### Branching is the practice of creating copies of programs or objects to work in parallel versions, retaining the original and working on the branch or making different changes to each.

### Suppose you're working on a project.

### You're going to have a bunch of different features or ideas in progress at any given time – some of which are ready to go, and others which are not.

### Branching exists to help you manage this workflow.

### When you create a branch in your project, you're creating an environment where you can try out new ideas.

### Changes you make on a branch don't affect the main branch, so you're free to experiment and commit changes.

### This is also useful when we have multiple people working on a project.

### Each person creates a branch for the feature or bug-fix they are working on and when they are finished they merge it back into the master branch.

### In Git, if you want to make your local repository reflect changes that have been made in a remote (tracked) repository, you should run the pull command.

### ** Pull Request**

### **Pull requests are a mechanism for a developer to notify team members that they have made some changes or completed a feature.**

### Once their feature branch is ready, the developer files a pull request.

### This lets everybody involved know that they need to review the code and merge it into the master branch.

### So, the pull request is more than just a notification.

### It's a kind of discussion room for discussing the changes made.

### If there are any problems with the changes, teammates can post feedback in the pull request and even improve the feature by pushing follow-up commits.

### When you file a pull request, you’re requesting that another developer pulls a branch from your repository into their repository.

### You need to provide 4 pieces of information to file a pull request:

- Source repository
- Source branch
- Destination repository
- Destination branch

**Merging**

### I guess you know combining something to form a single entity is what Merge means.

### In GIT Merging is a way of putting different history back together again.

### The git merge command allows you to take the independent lines of development created by git branch and integrate them into a single branch.

### To be more specific, merging takes the contents of a source branch and integrates them with a target branch.

### The source branch history remains the same.

### Git merge will combine multiple sequences of commits into one unified history.

### In the most frequent use cases, git merge is used to combine two branches.

### Merge takes two commit pointers, usually the branch tips, and will find a common base commit between them.

### Once Git finds a common base commit it will create a new "merge commit" that combines the changes of each queued merge commit sequence.

**Configuring and setting up Git user account**

### Command:

git config –global user.name “[name]”

### This command sets the author name to be used with your commits.

### Command:

git config –global user.email “[email address]”

### This command sets the email address to be used with your commits.

### The git config command is a convenience function that is used to set Git configuration values on a global or local project level.

### Command:

git init [repository name]

### The git init command is used to create a new blank repository.

### It is used to make an existing project as a Git project.

### Command:

git clone [url]

### Git clone is a Git command line utility which is used to target an existing repository and create a clone, or copy of the target repository.

### Command:

git add [file]

### Git add command is used to add all the local changes of your working copy to the staging area so that those changes can be committed to your local repository.

### Command:

git commit -m “[ Type in the commit message]"

### **The "commit" command is used to save your changes to the local repository.**

### You have to explicitly tell Git which changes you want to include in a commit before running the "git commit" command.

### This command records or snapshots the file permanently in the version history.

### Command:

### git reset [file]

### Command:

### git reset [commit]

### Git reset is a powerful command that is used to undo local changes to the state of a Git repo.

### You can reset or undo changes or mistakes made if needed.

### Command:

### git checkout [branch name]

### In Git terms, a "checkout" is the act of switching between different versions of a target entity. This command is used to switch from one branch to another.

### Command:

### git checkout -**b** [branch name]

### This command creates a new branch and also switches to it.
