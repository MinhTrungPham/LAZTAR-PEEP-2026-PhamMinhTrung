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

---

#### I. Practice basic Git Workflows

> **Goal:** Create a branch → Commit → Open a Pull Request → Merge, and handle a simple conflict.

---

**Step 1 — Create a new repository named `git-practice`**

Create the repository on GitHub with default settings.

![Create new repository on GitHub](/images/tuan1/day-01/image.png)
![Repository created successfully](/images/tuan1/day-01/image-1.png)

---

**Step 2 — Clone the repository to your local machine**

Use `git clone` to download the empty repository locally.

![Clone repository to local](/images/tuan1/day-01/image-2.png)

---

**Step 3 — Create `README.md` on `main`, commit and push**

Initialize the project with a `README.md`, then commit and push it to the `main` branch.

![Create README.md, commit and push to main](/images/tuan1/day-01/image-3.png)

---

**Step 4 — Create two branches, make changes, push, and open Pull Requests**

Create two separate branches from `main`, each with changes to `README.md`. Push both branches and open Pull Requests for each.

![Create branch and make changes](/images/tuan1/day-01/image-4.png)
![Push branch and open Pull Request (branch 1)](/images/tuan1/day-01/image-5.png)
![Push branch and open Pull Request (branch 2)](/images/tuan1/day-01/image-6.png)
![Pull Requests listed on GitHub](/images/tuan1/day-01/image-7.png)

---

**Step 5 — Create and resolve a merge conflict**

When both branches modify the same lines, a conflict occurs on merge. Resolve it manually and complete the merge.

![Merge conflict detected](/images/tuan1/day-01/image-8.png)
![Resolving the conflict in the editor](/images/tuan1/day-01/image-9.png)
![Conflict resolved, merge completed](/images/tuan1/day-01/image-10.png)
