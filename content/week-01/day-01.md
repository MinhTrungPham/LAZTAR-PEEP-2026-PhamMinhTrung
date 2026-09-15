+++
title = "Day 01 - 15/09/2026"
weight = 1
+++

## Topics Learned

### Git

#### Common Commands

| Command            | Meaning                                        |
| ------------------ | ---------------------------------------------- |
| git init           | Create a new Git repository                    |
| git remote         | Manage connections to remote repositories      |
| git clone          | Copy a remote repository to the local machine  |
| git fetch          | Download remote changes without merging them   |
| git pull           | Download and merge remote changes              |
| git status         | Show the current repository state              |
| git branch         | List, create, or delete branches               |
| git switch         | Move to another branch                         |
| git checkout       | Switch branches or restore files               |
| git add            | Stage changes for the next commit              |
| git commit         | Save staged changes to the repository history  |
| git commit --amend | Update the latest commit                       |
| git push           | Upload local commits to a remote repository    |
| git reset          | Unstage changes or move commit history         |
| git rebase         | Reapply commits on top of another branch       |
| git rebase -i      | Edit, squash, or reorder commits interactively |
| git stash          | Temporarily save uncommitted work              |
| git stash pop      | Restore the latest stashed work                |
| git merge          | Combine changes from another branch            |
| git cherry-pick    | Apply a specific commit to the current branch  |

#### Merge Conflict Handling

| Situation                        | Solution in Code Source Control                                     |
| -------------------------------- | ------------------------------------------------------------------- |
| Keep changes from both branches  | Open the file, edit the conflict manually, then mark it as resolved |
| Keep the current branch version  | Use `Accept Current Change` in the conflict editor                  |
| Keep the incoming branch version | Use `Accept Incoming Change` in the conflict editor                 |
| Cancel the merge                 | Open Source Control, use the `...` menu, then choose `Abort Merge`  |
| Resolve conflicts manually       | Review the marked conflict blocks and keep the correct final code   |

### Demo GitHub

#### I. Practice basic Git workflows: create a branch → commit → create a Pull Request → merge, and handle a simple conflict.

1. Create a new repository named `git-practice`
   ![alt text](/images/tuan1/day-01/image.png)
   ![alt text](/images/tuan1/day-01/image-1.png)
2. Clone the empty repository to your local machine
   ![alt text](/images/tuan1/day-01/image-2.png)
3. Create the `README.md` file on `main`, then commit and push it to `main`
   ![alt text](/images/tuan1/day-01/image-3.png)
4. Create two new branches from `main`, make changes to `README.md`, commit, push, and create pull requests
   ![alt text](/images/tuan1/day-01/image-4.png)
   ![alt text](/images/tuan1/day-01/image-5.png)
   ![alt text](/images/tuan1/day-01/image-6.png)
   ![alt text](/images/tuan1/day-01/image-7.png)
5. Create and resolve a conflict
   ![alt text](/images/tuan1/day-01/image-8.png)
   ![alt text](/images/tuan1/day-01/image-9.png)
   ![alt text](/images/tuan1/day-01/image-10.png)
