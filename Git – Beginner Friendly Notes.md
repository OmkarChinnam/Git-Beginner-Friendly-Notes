# Git – Beginner Friendly Notes

These notes are created based on my personal understanding after completing a Git course. The goal of this document is to help beginners understand **Git concepts clearly and practically**, without unnecessary complexity.

---

## Git and Version Control – Basics

### What is Git?

**Git** is a **Distributed Version Control System (DVCS)** used to track changes in files over time. It helps developers manage different versions of an application or software efficiently.

---

### What is Version Control?

**Version Control** is the practice of saving and tracking changes made to files so that we can:

* Maintain previous versions of an application
* Restore older versions if the latest changes fail
* Understand what changed, when, and by whom

Before modern version control systems, developers used **archives and patches** (such as `.zip` files) to store older versions. This approach was error-prone and difficult to manage, especially for collaboration.

---

### Types of Version Control Systems

Version control systems are classified into **three main types**:

1. Local Version Control System
2. Centralized Version Control System
3. Distributed Version Control System

---

### 1. Local Version Control System

A **Local Version Control System** stores different versions of a project **only on the developer’s local machine**, usually by maintaining multiple folders or file copies.

**Advantages:**

* Simple and easy to use
* No internet connection required

**Disadvantages:**

* High risk of data loss if the system crashes
* No collaboration support
* Cannot share files easily when working remotely

---

### 2. Centralized Version Control System (CVCS)

A **Centralized Version Control System** stores the complete project and its history on a **single central server**, which developers access remotely.

**Examples:** SVN, Perforce

**Advantages:**

* Enables collaboration across different locations
* Centralized control of the project

**Disadvantages:**

* Single point of failure
* If the server goes down, collaboration stops
* Users do not have the full project history locally

---

### 3. Distributed Version Control System (DVCS)

A **Distributed Version Control System** overcomes the limitations of local and centralized systems. In DVCS, **every developer has a complete copy of the repository**, including the full commit history.

**Example:** Git

**Advantages:**

* Works offline
* No single point of failure
* Faster operations
* Powerful branching and merging

---

### Git Usage

Git is **not limited to programming languages**. It can track changes in **any type of file**. Developers commonly use Git to manage application source code, collaborate with teams, and maintain stable versions of software.

---

## What is Version Control?

**Version Control** is the process of tracking changes made to files over time so that we can:

* View change history
* Compare versions
* Restore previous versions if something breaks
* Collaborate with others safely

---

## Types of Version Control Systems

### 1. Local Version Control System

Local VCS means maintaining multiple versions of a project on your **own system**, usually by creating copies of folders.

**Pros:**

* Simple to use
* No internet required

**Cons:**

* Risk of data loss if the system crashes
* No collaboration support

---

### 2. Centralized Version Control System (CVCS)

A centralized server stores the complete version history, and developers connect to it remotely.

**Examples:** SVN, Perforce

**Pros:**

* Easy collaboration
* Central control

**Cons:**

* Single point of failure (server downtime affects all users)

---

### 3. Distributed Version Control System (DVCS)

In DVCS, every developer has a **full copy of the repository**, including the entire history.

**Example:** Git

**Pros:**

* Works offline
* No single point of failure
* Fast branching and merging

---

## What is Git?

Git is a **Distributed Version Control System** used to track changes in any type of file — not just source code. Developers commonly use Git to manage application versions and collaborate efficiently.

---

## Git Workflow

Git works with three main areas:

1. **Working Directory** – Where files are edited
2. **Staging Area (Index)** – Where changes are prepared for commit
3. **Repository (.git)** – Where committed changes are permanently stored

📷 **Diagram Reference:**

```
images/git-working-staging-repo.png
```

This diagram visually explains how files move from the working directory to staging and finally into the repository.

---

## Important Git Commands

### Repository Setup

```bash
git init        # Initialize a local repository
git status      # Show file status
```

---

### Staging & Commit

```bash
git add file_name    # Add file to staging area
git add .            # Add all files to staging
git commit -m "msg"  # Commit staged changes
git commit -a -m "msg"  # Skip staging for tracked files
```

---

### Viewing Changes & History

```bash
git log                  # Commit history
git log --oneline        # Compact history
git log --graph          # Visual commit tree
git diff                 # Working directory vs staging
git diff --staged        # Staging vs last commit
```

---

### Removing Files

```bash
git rm --cached file_name  # Remove from staging only
```

---

## Branching in Git

Branches allow you to work on features independently without affecting the main codebase.

```bash
git branch                 # List branches
git branch branch_name     # Create branch
git checkout branch_name  # Switch branch
git checkout -b name      # Create & switch
git switch -c name        # Create & switch (modern)
git switch -              # Switch to previous branch
git branch -d name        # Delete branch
```

---

## Merging vs Rebasing

📷 **Diagram Reference:**

```
images/git-branch-graph.png
```

This diagram shows how merge creates a merge commit, while rebase creates a clean linear history.

### Merge

* Preserves full history
* Creates a merge commit
* Safe for shared branches

```bash
git merge branch_name
```

### Rebase

* Creates clean linear history
* Rewrites commit history
* Avoid rebasing public branches

```bash
git rebase branch_name
```

---

## Remote Repositories

Remote repositories are hosted platforms used for collaboration.

**Popular platforms:**

* GitHub
* GitLab
* Bitbucket

```bash
git remote -v                 # View remotes
git pull origin branch_name   # Fetch & merge
git push origin branch_name   # Push changes
```

---

## Tags in Git

Tags are used to mark specific points in history (usually releases).

```bash
git tag                      # List tags
git tag -a v1.0 -m "msg"     # Create annotated tag
git show v1.0                # View tag details
git push origin v1.0         # Push tag
```

---

## Git Stash

Git stash temporarily saves uncommitted changes so you can switch branches safely.

```bash
git stash           # Save changes
git stash list      # View stashes
git stash apply     # Apply stash
git stash pop       # Apply & remove stash
git stash drop      # Delete stash
```

---

## Checkout & History Navigation

```bash
git checkout commit_id     # Go to a specific commit
git checkout -b new_branch # Create branch from commit
```

---

## Forking (GitHub)

Forking creates a personal copy of someone else’s repository.

**Common use case:**

* Contributing to open-source projects

Workflow:

1. Fork repository
2. Clone fork locally
3. Make changes
4. Create Pull Request

---

## .gitignore

`.gitignore` tells Git which files or folders should not be tracked.

Example:

```text
node_modules/
target/
*.log
```

---

## Key Concepts

* **HEAD** – Pointer to the current branch or commit
* **Detached HEAD** – When checking out a commit directly
* **Pull Request** – Request to merge changes (GitHub feature)

---

## One-Page Git Cheat Sheet

### Setup

```bash
git init
git clone repo_url
```

### Daily Workflow

```bash
git status
git add .
git commit -m "message"
```

### History & Comparison

```bash
git log --oneline --graph
git diff
git diff --staged
```

### Branching

```bash
git branch
git switch -c branch_name
git merge branch_name
git rebase branch_name
```

### Remote Operations

```bash
git pull origin branch
git push origin branch
```

### Stash & Tags

```bash
git stash
git stash pop
git tag -a v1.0 -m "release"
```

### Undo & Recovery

```bash
git checkout commit_id
git reset --hard HEAD~1
```

---

## Final Notes

These notes are intentionally written in **simple language** for beginners. If this helps you, feel free to share or contribute.

Happy Learning 🚀
