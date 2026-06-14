## Git Branching & Working with GitHub

---

### Task 1: Understanding Branches
Answer these in your `day-23-notes.md`:
1. What is a branch in Git?
 - A branch is basically a feature branch where all your files are present, similar to `main` when you create it from there. You can make your own changes without affecting the original branch.

2. Why do we use branches instead of committing everything to `main`?
 - If we are working on a new feature, we can use a branch because changing code directly in main can affect others and may cause issues, especially if we are working on a production environment.

3. What is `HEAD` in Git?
 - It shows where you are currently in Git and points to the branch or commit you are working on.

4. What happens to your files when you switch branches?
 - Your files get changed according to the branch you switched to.
---

### Task 2: Branching Commands — Hands-On
In your `devops-git-practice` repo, perform the following:
1. List all branches in your repo
2. Create a new branch called `feature-1`
3. Switch to `feature-1`
4. Create a new branch and switch to it in a single command — call it `feature-2`
5. Try using `git switch` to move between branches — how is it different from `git checkout`?
6. Make a commit on `feature-1` that does **not** exist on `main`
7. Switch back to `main` — verify that the commit from `feature-1` is not there
8. Delete a branch you no longer need
9. Add all branching commands to your `git-commands.md`
<img width="1092" height="926" alt="2" src="https://github.com/user-attachments/assets/0d9c0817-8ccf-4d5d-88bb-da0be7ea2f53" />

---

### Task 3: Push to GitHub
1. Create a **new repository** on GitHub (do NOT initialize it with a README)
2. Connect your local `devops-git-practice` repo to the GitHub remote
3. Push your `main` branch to GitHub
4. Push `feature-1` branch to GitHub
5. Verify both branches are visible on GitHub
6. Answer in your notes: What is the difference between `origin` and `upstream`?
- **origin** is your own remote repository where you push your code.
- **upstream** is the original repository from which your repository was forked.
<img width="1290" height="772" alt="3" src="https://github.com/user-attachments/assets/bd7f1609-65e0-421d-aa73-f7e1dc4ae76c" />
<img width="1077" height="690" alt="31" src="https://github.com/user-attachments/assets/5a0b27ee-712a-4bf5-a888-320e425a388f" />
<img width="1417" height="725" alt="32" src="https://github.com/user-attachments/assets/3a2a59b3-a320-4f6c-96b5-3ff74d685f33" />

---

### Task 4: Pull from GitHub
1. Make a change to a file **directly on GitHub** (use the GitHub editor)
2. Pull that change to your local repo
3. Answer in your notes: What is the difference between `git fetch` and `git pull`?
- **git fetch** → Downloads changes from the remote repository.
- **git pull** → Downloads and merges changes into your current branch.
<img width="922" height="467" alt="4" src="https://github.com/user-attachments/assets/7298012e-b6f6-4053-acad-a9783df55288" />
<img width="841" height="722" alt="41" src="https://github.com/user-attachments/assets/e7176918-756c-43cc-8bdf-003a8389bb64" />
<img width="1401" height="780" alt="42" src="https://github.com/user-attachments/assets/15df100b-ae64-4585-8ff0-c381f63a8e26" />

---

### Task 5: Clone vs Fork
1. **Clone** any public repository from GitHub to your local machine
2. **Fork** the same repository on GitHub, then clone your fork
3. Answer in your notes:
   - What is the difference between clone and fork?
    - **Clone** → Copies a remote repository to your local machine.
    - **Fork** → Creates a copy of someone else's repository in your own GitHub account.

   - When would you clone vs fork?
    - **Clone** → When you want to work on a repository locally.
    - **Fork** → When you want to contribute to or modify someone else's repository without affecting the original project. Eg: Forking the **90 Days of DevOps** repository to your own GitHub account for hands-on practice.

   - After forking, how do you keep your fork in sync with the original repo?
    -  using GitHub's **Sync fork** button
---
