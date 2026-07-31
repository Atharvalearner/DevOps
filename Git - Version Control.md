***# Git:***

a distributed version control system (DVCS) used to track changes in source code, manage versions, and enable multiple developers to collaborate on the same project efficiently.



Every developer has: Complete repository, Complete history, Can commit offline



With Git:

* Every change is tracked.
* Multiple developers work independently.
* Branches isolate new features.
* Previous versions can be restored.
* Conflicts can be resolved.





| ---------------------- | ------------------------------------------- |

| Git                    | GitHub                                      |

| ---------------------- | ------------------------------------------- |

| Version Control System | Cloud hosting platform for Git repositories |

| Installed locally      | Hosted online                               |

| Tracks code changes    | Stores and shares repositories              |

| Works without internet | Usually requires internet                   |

| ---------------------- | ------------------------------------------- |



***# Git Architecture:***

Current Local Working Directory

&#x20;       │

git add

&#x20;       ▼

Staging Area (Index)

&#x20;       │

git commit

&#x20;       ▼

Local Repository (.git)

&#x20;       │

git push

&#x20;       ▼

Remote Repository (GitHub/GitLab)





***# Commands:***

1. **Branching:**

***Create Branch:*** git branch BRANCH-NAME

***List Branches:*** git branch

***List Remote branches:*** git branch -r

***List All branches:*** git branch -a



***Switch Branch:*** git checkout BRANCH-NAME

***Modern Switch command:*** git switch BRANCH-NAME



***Create and Switch Together:***

git checkout -b BRANCH-NAME

or

git switch -c BRANCH-NAME



**2. Merging:**

Suppose you're on main.

git checkout main



***Merge another branch to current/main branch:*** git merge feature-login

The changes from feature-login become part of main.



**3. Delete Branch**

***After merging:*** git branch -d feature-login

***Force delete:*** git branch -D feature-login

***Delete remote branch:*** git push origin --delete feature-login



**4. Undo Commands**

***Restore Unstaged Changes:*** git restore fileName



***Unstage File:*** git restore --staged file.txt



***Revert Commit:*** git revert <commit-id>



**5. Stash:** Temporarily save uncommitted work.

git stash



***View stashes:*** git stash list

***Restore:*** git stash pop





***# git fetch:***

Downloads the latest changes from the remote repository.

Does not merge them into your current branch.

Safely updates your remote-tracking branches (such as origin/main)



***# git pull:***

Downloads the latest changes and immediately integrates them into your current branch.

By default, it performs: git fetch and git merge



***# git merge and git rebase:***

git merge combines two branches by creating a merge commit while preserving the original branch history. 

git rebase moves or reapplies commits onto another branch to create a cleaner, linear history, but it rewrites commit history and should be used carefully on shared branches.



***# git reset:***

Moves the branch pointer to an earlier commit.

1. **git reset --soft HEAD\~1**

Removes the last commit but keeps changes staged.



2\. **git reset --mixed HEAD\~1**

Removes the last commit and unstages the changes (this is the default mode).



3\. **git reset --hard HEAD\~1**

Removes the last commit and discards the associated working directory changes.

Use with caution because discarded changes cannot be recovered easily.



***# git revert:***

safely undoes the changes introduced by a commit by creating a new commit, making it the preferred option for shared repositories because it preserves history.

