# Day 25 – Git Reset vs Revert & Branching Strategies

## Task 1: Git Reset — Hands-On

### 1. Make 3 commits in your practice repo (commit A, B, C)
<img width="1117" height="917" alt="1" src="https://github.com/user-attachments/assets/95f742ac-7ab1-4d9d-9838-d0a4590265a8" />

### 2. Use `git reset --soft` to go back one commit — what happens to the changes?

- Last commit (**filec**) was removed.
- **filec is still staged** (`git add` is not needed).
- You can commit it again immediately.
<img width="1195" height="987" alt="2" src="https://github.com/user-attachments/assets/55c153be-54f8-4f57-a170-296a09473dd7" />

### 3. Re-commit, then use `git reset --mixed` to go back one commit — what happens now?

- Commits after **filea** were removed.
- Files **fileb, filec, and filed** are still there.
- They are **not staged** anymore.
- You need to run `git add` before committing again.
<img width="1295" height="935" alt="3" src="https://github.com/user-attachments/assets/f688f966-0f2c-4867-83d7-3140dcf2253d" />

### 4. Re-commit, then use `git reset --hard` to go back one commit — what happens this time?

- Last commit was removed.
- Changes in that commit were also deleted.
- Working directory became clean.
<img width="1331" height="966" alt="4" src="https://github.com/user-attachments/assets/fece9d27-62c2-4fa9-bcc6-67a4fa65cf0d" />

### 5. Answer in your notes

#### What is the difference between `--soft`, `--mixed`, and `--hard`?

| Command | Commit Removed | File Kept | Staged? |
|---------|----------------|-----------|---------|
| `git reset --soft` | ✅ Yes | ✅ Yes | ✅ Yes |
| `git reset --mixed` | ✅ Yes | ✅ Yes | ❌ No |
| `git reset --hard` | ✅ Yes | ❌ No | ❌ No |

#### Which one is destructive and why?

`git reset --hard` is **destructive** because it deletes both the commit and the file changes from your local machine. If the changes are not backed up, they can be lost.

#### When would you use each one?

### `git reset --soft`

Use when:

- You want to change the last commit.
- You want to recommit the same changes.

### `git reset --mixed`

Use when:

- You want to unstage files.
- You want to edit the changes before committing again.

### `git reset --hard`

Use when:

- You want to completely discard local changes.
- You want to return to a clean state.

---

## Task 2: Git Revert — Hands-On

### 1. Make 3 commits (commit X, Y, Z)

### 2. Revert commit Y (the middle one) — what happens?
- Git created a **new commit** that reversed the changes made in commit **Y**.
- Commit **Y** was **not deleted**.
- The latest commit now undoes the changes from **Y**.
### 3. Check `git log` — is commit Y still in the history?
**Yes.**
Commit **Y** is still present in the Git history, and a new **revert commit** is added after it.
<img width="1042" height="900" alt="5" src="https://github.com/user-attachments/assets/1d73243e-9d6e-42ff-ba05-135dbe0880a4" />


### 4. Answer in your notes

- How is `git revert` different from `git reset`?
- **git reset** removes commits from your branch history.
- **git revert** keeps the history and creates a new commit to undo the changes.
- Why is revert considered **safer** than reset for shared branches?
Because it does **not change Git history**.

Other team members can continue working without any problems because the old commits are still there.
- When would you use revert vs reset?
### Use `git revert` when:

- The commit has already been pushed.
- You are working with a team.
- You want to undo changes without changing history.

### Use `git reset` when:

- The commit has **not** been pushed.
- You want to remove or fix recent commits.
- You are working on your local branch.
---

## Task 3: Reset vs Revert — Summary

Create a comparison in your notes:


| Feature | `git reset` | `git revert` |
|---------|-------------|--------------|
| **What it does** | Moves `HEAD` to an earlier commit and can remove commits. | Creates a new commit that undoes the changes of an earlier commit. |
| **Removes commit from history?** | ✅ Yes | ❌ No |
| **Safe for shared/pushed branches?** | ❌ No | ✅ Yes |
| **When to use** | To fix or remove local commits that haven't been pushed. | To undo changes in commits that have already been pushed or shared with others. |

- **`git reset`** changes Git history, so it is best used on **local commits** that haven't been pushed.
- **`git revert`** keeps Git history unchanged by creating a new commit to undo changes, making it the **safer option for shared repositories**.
---

## Task 4: Branching Strategies

## Task 4: Branching Strategies

### 1. GitFlow

#### How it works

GitFlow uses different branches for different work.

- `main` → Production (live code)
- `develop` → Ongoing development
- `feature` → New features
- `release` → Prepare a new release
- `hotfix` → Fix urgent bugs

#### Diagram

```text
feature
   │
   ▼
develop ─────► release ─────► main
    ▲                           ▲
    └──────── hotfix ───────────┘
```

#### Where it's used

- Large companies
- Projects with planned releases

#### Pros

- Easy to manage releases
- Good for large teams

#### Cons

- More branches to manage
- Can be slow

---

### 2. GitHub Flow

#### How it works

Create a branch from `main`, make changes, create a Pull Request, review, and merge back into `main`.

#### Diagram

```text
main
 │
 ├── feature
 │      │
 │      ▼
 └──── Merge
```

#### Where it's used

- Small teams
- Open-source projects
- Fast deployments

#### Pros

- Simple
- Easy to learn
- Fast development

#### Cons

- Not ideal for planned releases

---

### 3. Trunk-Based Development

#### How it works

Developers work directly on `main` or use very small branches that are merged quickly.

#### Diagram

```text
Dev A ─┐
Dev B ─┼──► main
Dev C ─┘
```

#### Where it's used

- Teams using Continuous Integration (CI)
- Fast-moving projects

#### Pros

- Fast development
- Fewer merge conflicts

#### Cons

- Needs good testing

---

## Answers

### Which strategy would you use for a startup shipping fast?

**GitHub Flow** because it is simple and helps release features quickly.

### Which strategy would you use for a large team with scheduled releases?

**GitFlow** because it keeps development, releases, and bug fixes organized.

### Which one does your favorite open-source project use?

---

## Task 5: Git Commands Reference Update

Update your `git-commands.md` to cover everything from Days 22–25:

- Setup & Config
- Basic Workflow (`add`, `commit`, `status`, `log`, `diff`)
- Branching (`branch`, `checkout`, `switch`)
- Remote (`push`, `pull`, `fetch`, `clone`, `fork`)
- Merging & Rebasing
- Stash & Cherry Pick
- Reset & Revert
