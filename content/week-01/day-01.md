+++

#### I. Basic Git Commands

title = "Day 01 - 15/09/2026"
weight = 1
+++

## Topics Learned

### Git

#### Common Commands

| Command      | Meaning                                       |
| ------------ | --------------------------------------------- |
| git init     | Create a new Git repository                   |
| git remote   | Manage connections to remote repositories     |
| git clone    | Copy a remote repository to the local machine |
| git fetch    | Download remote changes without merging them  |
| git pull     | Download and merge remote changes             |
| git status   | Show the current repository state             |
| git branch   | List, create, or delete branches              |
| git switch   | Move to another branch                        |
| git checkout | Switch branches or restore files              |
| git add      | Stage changes for the next commit             |

#### Git Command Screenshots

**`git version`** — Check the currently installed Git version.

![git version command](/images/tuan1/day-01/git_version.png)

**`git init`** — Initialize a new local Git repository in the current directory.

![git init command](/images/tuan1/day-01/git_init.png)

**`git remote`** — View and manage connections to remote repositories.

![git remote command](/images/tuan1/day-01/git_remote.png)

**`git clone`** — Copy a remote repository to the local machine.

![git clone command](/images/tuan1/day-01/git_clone.png)

**`git fetch`** — Download changes from the remote without merging them into the current branch.

![git fetch command](/images/tuan1/day-01/git_fetch.png)

**`git pull`** — Fetch and immediately merge remote changes into the current branch.

![git pull command](/images/tuan1/day-01/git_pull.png)

**`git status`** — Show which files are staged, unstaged, or untracked in the working directory.

![git status command](/images/tuan1/day-01/git_status.png)

**`git branch`** — List all local branches; the active branch is highlighted.

![git branch command](/images/tuan1/day-01/git_branch.png)

**`git switch`** — Switch to another branch without affecting uncommitted changes.

![git switch command](/images/tuan1/day-01/git_switch.png)

**`git checkout`** — Switch branches or restore a specific file to a previous state.

![git checkout command](/images/tuan1/day-01/git_checkout.png)

**`git add`** — Stage file changes to include them in the next commit.

![git add command](/images/tuan1/day-01/git_add.png)

**`git commit`** — Save staged changes as a new snapshot in the repository history.

![git commit command](/images/tuan1/day-01/git_commit.png)

**`git commit` + `git log`** — After committing, use `git log` to view the commit history and confirm the new entry.

![git commit and git log commands](/images/tuan1/day-01/git_commit_git_log.png)

**`git commit --amend`** — Modify the most recent commit message or include additional staged changes.

![git commit amend command](/images/tuan1/day-01/git_amend.png)

**`git push`** — Upload local commits to the corresponding branch on the remote repository.

![git push command](/images/tuan1/day-01/git_push.png)

**`git reset`** — Unstage files or move the branch pointer back to a previous commit.

![git reset command](/images/tuan1/day-01/git_reset.png)

**`git stash`** — Temporarily shelve uncommitted changes so the working directory is clean.

![git stash command](/images/tuan1/day-01/git%20stash.png)

**`git stash pop`** — Re-apply the most recently stashed changes and remove them from the stash list.

![git stash pop command](/images/tuan1/day-01/git_stash_pop.png)

**`git merge`** — Combine the history of another branch into the current branch.

![git merge command](/images/tuan1/day-01/git_merge.png)
| git commit | Save staged changes to the repository history |
| git commit --amend | Update the latest commit |
| git push | Upload local commits to a remote repository |
| git reset | Unstage changes or move commit history |
| git rebase | Reapply commits on top of another branch |
| git rebase -i | Edit, squash, or reorder commits interactively |
| git stash | Temporarily save uncommitted work |
| git stash pop | Restore the latest stashed work |
| git merge | Combine changes from another branch |
| git cherry-pick | Apply a specific commit to the current branch |

#### Merge Conflict Handling

| Situation                        | Solution in Code Source Control                                        |
| -------------------------------- | ---------------------------------------------------------------------- |
| Keep changes from both branches  | Open the file, edit the conflict manually, then mark it as resolved    |
| Keep the current branch version  | Use `Accept Current Change` in the conflict editor                   |
| Keep the incoming branch version | Use `Accept Incoming Change` in the conflict editor                  |
| Cancel the merge                 | Open Source Control, use the `...` menu, then choose `Abort Merge` |
| Resolve conflicts manually       | Review the marked conflict blocks and keep the correct final code      |

#### II. Practice Basic Git Workflows

> **Goal:** Branch → Commit → Push → Pull Request → Merge → Conflict Resolution.

---

**Step 1 — Create a new repository named `git-practice`**

Create a new public repository on GitHub named `git-practice`. Skip the README initialization — the file will be added locally.

![Create new repository on GitHub](/images/tuan1/day-01/create_new_repo1.png)

![Repository created successfully](/images/tuan1/day-01/create_new_repo2.png)

---

**Step 2 — Clone the repository to the local machine**

Clone the empty repository, move into the project folder, and verify the remote connection:

```bash
git clone https://github.com/<username>/git-practice.git
cd git-practice
git status
git remote -v
```

![Clone repository and verify remote](/images/tuan1/day-01/git_clone_new_repo.png)

---

**Step 3 — Initialize `README.md`, commit, and push to `main`**

Create `README.md` with a short description, stage it, commit, and push to `main`:

```bash
"# Git Practice" | Out-File README.md

git add README.md
git commit -m "Initial README"
git push -u origin main
```

![Stage, commit, and push README.md to main](/images/tuan1/day-01/git_add_commit_push.png)

---

**Step 4 — Create Branch 1: `feature/header`**

Create `feature/header` off `main`, add a new `## Header` section to `README.md`, then push:

```bash
git switch -c feature/header
```

```markdown
## Header

Welcome to Git Practice.
```

```bash
git add README.md
git commit -m "Add header section"
git push -u origin feature/header
```

![Create feature/header and push](/images/tuan1/day-01/create_new_branch.png)

---

**Step 5 — Open Pull Request 1**

On GitHub, open a PR from `feature/header` into `main`. Leave it **open** — merging it now is what will cause the conflict later.

![Pull Request 1 opened](/images/tuan1/day-01/create_pull_request.png)

---

**Step 6 — Create Branch 2: `feature/description`**

> ⚠️ Switch back to `main` first. Branch 2 must branch off `main`, not `feature/header`.

```bash
git switch main
git pull origin main
git switch -c feature/description
```

![Create feature/description from main](/images/tuan1/day-01/create_new_branch_from_main.png)

---

**Step 7 — Edit the same line (intentional conflict setup)**

On `feature/description`, change the description line of `README.md` to something different from what `feature/header` left. Both branches now have diverging edits on the exact same line — this is what causes the conflict.

```
Before: This repository is used to practice basic Git workflows.
After:  This repository demonstrates Git workflows for developers.
```

---

**Step 8 — Commit and push Branch 2**

```bash
git add README.md
git commit -m "Update repository description"
git push -u origin feature/description
```

![Commit and push feature/description](/images/tuan1/day-01/modify_readme_push.png)

---

**Step 9 — Open Pull Request 2**

Open a second PR from `feature/description` into `main`. Both PRs are now pending:

| PR | Branch                  | Target   |
| -- | ----------------------- | -------- |
| #1 | `feature/header`      | `main` |
| #2 | `feature/description` | `main` |

![Pull Request 2 opened](/images/tuan1/day-01/create_pull_request_2.png)

---

**Step 10 — Merge Pull Request 1**

PR #1 has no conflicts — merge it. Once merged, `main` now includes the `## Header` section.

![Merge Pull Request 1](/images/tuan1/day-01/merge_pull_request1.png)

---

**Step 11 — Conflict detected on Pull Request 2**

Because `main` changed after PR #1 was merged, GitHub flags PR #2 with a conflict. The same line was modified differently on each branch.

![Conflict detected on PR 2](/images/tuan1/day-01/conflict_on_pull_request2.png)

---

**Step 12 — Why the conflict happened**

Both branches started from the same base commit on `main` but each modified the same line:

- `feature/header` → kept the original description, added `## Header`
- `feature/description` → rewrote the description line

Git can't pick a winner automatically, so it stops and asks for manual input.

---

**Step 13 — Prepare to resolve locally**

Switch to `feature/description` and pull the latest state of the remote:

```bash
git switch feature/description
git fetch origin
```

---

**Step 14 — Trigger the conflict locally**

Merge `origin/main` into the current branch. Git stops and reports the conflict:

```bash
git merge origin/main
```

```
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
```

![Conflict output in terminal](/images/tuan1/day-01/conflict_content.png)

---

**Step 15 — Inspect the conflict in VS Code**

Open the project in VS Code. Inside `README.md`, Git has inserted conflict markers showing both versions:

```
<<<<<<< HEAD
This repository demonstrates Git workflows for developers.
=======
This repository is used to practice basic Git workflows.

## Header

Welcome to Git Practice.
>>>>>>> origin/main
```

- Everything between `<<<<<<< HEAD` and `=======` is from the current branch.
- Everything between `=======` and `>>>>>>> origin/main` is from `main`.

![Conflict markers in VS Code](/images/tuan1/day-01/conflict_in_VSCode.png)

---

**Step 16 — Resolve the conflict**

Edit the file to produce the correct final content — keeping the new description and the header section from `main`. Delete all three conflict marker lines when done.

```markdown
# Git Practice

This repository demonstrates Git workflows for developers.

## Header

Welcome to Git Practice.
```

VS Code's **Merge Editor** provides a side-by-side view if needed:

![Merge Editor in VS Code](/images/tuan1/day-01/Resolve_in_merge_editor.png)

---

**Step 17 — Stage, commit, and push**

After saving, stage the resolved file, create the merge commit, and push:

```bash
git add README.md
git commit -m "Resolve merge conflict in README"
git push origin feature/description
```

![Merge commit completed](/images/tuan1/day-01/Complete%20Merge.png)

![Push to remote](/images/tuan1/day-01/push_conflict_resolve.png)

---

**Step 18 — Conflict cleared on GitHub**

PR #2 on GitHub now shows no conflicts and is ready to merge.

![PR 2 conflict resolved](/images/tuan1/day-01/Conflict%20Resolved%20on%20Pull%20Request.png)

---

**Step 19 — Merge Pull Request 2**

Merge PR #2 into `main` on GitHub.

![Pull Request 2 merged](/images/tuan1/day-01/Pull%20Request%202%20Merged.png)

---

**Step 20 — Verify the final state**

Pull the latest `main` and confirm the final content:

```bash
git switch main
git pull origin main
git log --oneline --graph --all
```

```markdown
# Git Practice

This repository demonstrates Git workflows for developers.

## Header

Welcome to Git Practice.
```

![Final repository state](/images/tuan1/day-01/Final%20Repository.png)
