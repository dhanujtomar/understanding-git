
# Introduction to Git & GitHub


Check Git Version by using `git --version`

## Configure git

Configure username and email by using `git user.name <name>` and `git user.email <email>` respectively.


## Life Cycle of Git

### Modified &#8594; Staging &#8594; Commit

Modified:
- Contains files that are newly added to the folder
- Files that are updated but not staged
- Files can be sent from the modified state to the staged state by using `git add <file_name>` to add a specific file or use `git add .` to add all updated files to the staged state.

Staging:
- Contains files that are newly staged
- Does not add the files that are updated but not explicated staged again
- A file needs to be staged again and again if modified
- Files can be sent from the staged state to the commit stage by using `git commit -m <Message>`

Commit:
- Contains files that are committed

> [!NOTE]
> Useful information that users should know, even when skimming content.
- A file that is modified but not staged can not be directly committed
- If there are two or more files and one is present in the modified state and the other in the staged state on commit only the staged files will be committed and the modified files will stay in the modified

## Git add:
It is used to add a **single file** to the staged state:

`Git add <file_name>`

To add **all files** to the staged state:

`Git add .`

## Git commit:
It is used to commit a file:

`git commit -m "Commit message”`

committing creates Version Control

## Revert changes:
Revert changes made in a particular version

`git revert <version_id OR version_name>`

EX.	`git revert 7435c62`

> [!Note]
> If a version is reverted two/even number of times, you will get back to the original code that was present before reverting



## Reset:
Delete all the commit history to a certain point using `git reset <version_id>`.
This will reset your commit to a previous version but will not change the present file data

> [!Note]
> to change the file data to a previous commit version with reset use the **–-hard flag** `git reset 7435c62 –-hard`.
> This will delete all the existing commits to a certain point and **reset the data in all the files up to this commit**.

## Branching

1. To create a branch `git branch <branch_name>`

1. Switch to the new branch `git checkout <branch_name>`

OR
1. Create and switch to a new branch at the same time `Git checkout -b <branch_name>`

	
> [!TIP]
> View all existing branches `Git branch -a`

## Merge branch:
1. Could you check out the branch in which you want to merge the new branch?
1. Use the merge command

    example: (I'm using two branches 'master' and 'feature')
    ```
    git checkout master
    -- In the master branch
    Git merge feature
    -- Feature branch merged to master branch
    ```

> [!Warning]
> Data insufficient
> 
> Types of Merges:
> -	Fast Forward: Add new file or data directly to new file
> -	Recursive: Add new file or 
> - Conflict:

# GitHub

1. **Create a new repo** inside GitHub

1. Push project branches to repo (use repo URL and the branch you want to push) `git push <url> <branch_name>`

1. (Optional but useful) **Give acronym to URL** for ease(Generally origin is used as acronym) `git remote add <acronym>  <URL>` eg. `git remote add origin https://github.com/dhanujtomar/...`

1.	Now step 2 can be reused as (if url=origin and branch_name = master) `git push origin master`

1.	Check for existing remote acronym `git remote -v`

1.	Push new Branch to repository `git push origin <new_branch>`

This new branch can be agreed upon and requested for merge to the master node in Git Hub.

### Some more commands

Pull request for original branch `git pull origin master`

Clone a repo by using `git clone <url> <branch>`
