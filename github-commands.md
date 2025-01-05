
# GitHub Commands Cheat Sheet

This document covers commonly used commands for managing GitHub repositories, setting up SSH, and more.

---

## Table of Contents
1. [Setting Up a New Repository](#setting-up-a-new-repository)
2. [Cloning a Repository](#cloning-a-repository)
3. [Using SSH with GitHub](#using-ssh-with-github)
4. [Basic Git Workflow](#basic-git-workflow)
5. [Branching and Merging](#branching-and-merging)
6. [Viewing Repository Status](#viewing-repository-status)
7. [Undoing Changes](#undoing-changes)
8. [Syncing with Remote](#syncing-with-remote)

---

## Setting Up a New Repository

### Create a New Repository on GitHub
1. Go to [GitHub](https://github.com/) and log in.
2. Click the **+** button in the top-right corner and select **New Repository**.
3. Fill in the repository name, description, and settings (e.g., public/private).
4. Click **Create Repository**.

### Initialize a Local Repository
1. Navigate to your project folder:
   ```bash
   cd /path/to/your/project
   ```
2. Initialize a Git repository:
   ```bash
   git init
   ```
3. Add files to the staging area:
   ```bash
   git add .
   ```
4. Commit the changes:
   ```bash
   git commit -m "Initial commit"
   ```
5. Link the local repository to the remote GitHub repository:
   ```bash
   git remote add origin https://github.com/username/repository-name.git
   ```
6. Push the changes to GitHub:
   ```bash
   git push -u origin main
   ```

---

## Cloning a Repository

### Clone Using HTTPS:
```bash
git clone https://github.com/username/repository-name.git
```

### Clone Using SSH:
```bash
git clone git@github.com:username/repository-name.git
```

---

## Using SSH with GitHub

### Generate an SSH Key
1. Check for existing SSH keys:
   ```bash
   ls -al ~/.ssh
   ```
2. Generate a new SSH key (if needed):
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```
   Press Enter to accept the default file location.

3. Set a passphrase (optional but recommended).

### Add SSH Key to GitHub
1. Copy the SSH key to your clipboard:
   ```bash
   pbcopy < ~/.ssh/id_ed25519.pub
   ```
2. Go to GitHub > Settings > SSH and GPG keys > New SSH key.

3. Paste the key and save.

### Test SSH Connection
```bash
ssh -T git@github.com
```
If successful, you'll see: Hi username! You've successfully authenticated...

---

## Basic Git Workflow

### Check Repository Status
```bash
git status
```

### Add Files to Staging Area
```bash
git add <file-name>
```
Add all files:
```bash
git add .
```

### Commit Changes
```bash
git commit -m "Your commit message"
```

### Push Changes to Remote
```bash
git push origin main
```

### Pull Latest Changes
```bash
git pull origin main
```

---

## Branching and Merging

### Create a New Branch
```bash
git branch <branch-name>
```

### Switch to a Branch
```bash
git checkout <branch-name>
```

### Create and Switch to a New Branch
```bash
git checkout -b <branch-name>
```

### Merge a Branch
Switch to the main branch:
```bash
git checkout main
```
Merge the branch:
```bash
git merge <branch-name>
```

### Delete a Branch
```bash
git branch -d <branch-name>
```

---

## Viewing Repository Status

### View Commit History
```bash
git log
```

### View Changes in Files
```bash
git diff
```

### View Remote Repositories
```bash
git remote -v
```

---

## Undoing Changes

### Unstage a File
```bash
git reset <file-name>
```

### Revert to the Last Commit
```bash
git reset --hard HEAD
```

### Amend the Last Commit
```bash
git commit --amend
```

---

## Syncing with Remote

### Fetch Changes from Remote
```bash
git fetch origin
```

### Rebase Local Changes
```bash
git pull --rebase origin main
```

### Force Push (Use with Caution!)
```bash
git push --force origin main
```
