# Introduction to Git: Your First Repository

## Task 1: Install and Configure Git

1. Verify Git is installed on your machine.
2. Set up your Git identity — name and email.
3. Verify your configuration.
<img width="1175" height="202" alt="1" src="https://github.com/user-attachments/assets/b5ea515d-bf18-425d-bb27-bbbaa2d7bae0" />

---

## Task 2: Create Your Git Project

1. Create a new folder called `devops-git-practice`.
2. Initialize it as a Git repository.
3. Check the status — read and understand what Git is telling you.

 * **On branch master** → Current branch is `master`.
 * **No commits yet** → Repository has no commits.
 * **Nothing to commit** → No tracked changes exist.
  
4. Explore the hidden `.git/` directory — look at what's inside.

 * `HEAD` → Points to the current branch.
 * `config` → Repository configuration.
 * `description` → Repository description.
 * `hooks/` → Git event scripts.
 * `objects/` → Stores Git data.
 * `info/` → Contains additional repository information.
 * `refs/` → Stores branches and tags.
<img width="1382" height="923" alt="2" src="https://github.com/user-attachments/assets/52126cb7-4f60-45ee-aa02-06ee6cf9fece" />

---

## Task 3: Create Your Git Commands Reference

1. Create a file called `git-commands.md` inside the repo.
2. Add the Git commands you've used so far, organized by category.

### Setup & Config

| Command                                            | Purpose                           |
| -------------------------------------------------- | --------------------------------- |
| `git --version`                                    | Check the installed Git version.  |
| `git config --global user.name "Your Name"`        | Configure your Git username.      |
| `git config --global user.email "you@sample.com"` | Configure your Git email address. |

### Basic Workflow

| Command                     | Purpose                          |
| --------------------------- | -------------------------------- |
| `mkdir devops-git-practice` | Create a new directory.          |
| `git init`                  | Initialize a new Git repository. |

### Viewing Changes

| Command      | Purpose                                                                     |
| ------------ | --------------------------------------------------------------------------- |
| `git status` | Display the current repository status, branch, and tracked/untracked files. |
| `git log`    | Show the commit history of the repository.                                  |

<img width="1041" height="571" alt="3" src="https://github.com/user-attachments/assets/5417a9e0-c2c1-4d43-a835-b91bc8694d71" />

---

## Task 4: Stage and Commit

1. Stage your file.
2. Check what's staged.
3. Commit with a meaningful message.
4. View your commit history.
<img width="1090" height="478" alt="4" src="https://github.com/user-attachments/assets/e5067f5b-d2b3-4e5e-ae55-8cae1e545f17" />

---

## Task 5: Make More Changes and Build History

1. Edit `git-commands.md` and add more commands as you discover them.
2. Check what changed since your last commit.
3. Stage and commit again with a different, descriptive message.
4. Repeat this process at least **3 times** so you have multiple commits in your history.
5. View the full history in a compact format.
<img width="1253" height="896" alt="5" src="https://github.com/user-attachments/assets/b0f6a272-df2c-4641-b833-d76b3fa29db4" />

---

## Task 6: Understand the Git Workflow

### 1. What is the difference between `git add` and `git commit`?

* **git add** - Adds your file from the filesystem to the staging area.
* **git commit** - Adds the staged file to Git and saves it as a commit.

### 2. What does the staging area do? Why doesn't Git just commit directly?

* The staging area is used to add files before committing them. If a developer has modified multiple files but wants to commit only specific files, they can stage only those files. This helps avoid committing incomplete or unnecessary changes.

### 3. What information does `git log` show you?

* Commit message
* Author
* Date and time
* Commit ID (40-digit hash)

### 4. What is the `.git/` folder and what happens if you delete it?

* Git tracking and commit history are removed but the project files remain unchanged.

### 5. What is the difference between a working directory, staging area, and repository?

| Area                  | Purpose                                                       |
| --------------------- | ------------------------------------------------------------- |
| **Working Directory** | Where we initially create and modify files.                   |
| **Staging Area**      | The place where files are added before a commit.              |
| **Repository**        | The place where committed files and their history are stored. |
