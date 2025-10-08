📌 Source Code Management (SCM) & Git Cheatsheet

1️⃣ Source Code Management (SCM)
🔹 Types of SCM:

1. Centralized Version Control System (CVCS):

All code stored on a central server.

Requires network connection to work.

If server crashes → risk of data loss.

Example: Subversion (SVN), Perforce

2. Distributed Version Control System (DVCS):

Each developer has a full copy (clone) of the repository (code + history).

Work can be done offline, later synced.

Safer → No single point of failure.

Example: Git, Mercurial

2️⃣ Importance of SCM in DevOps

Collaboration: Many developers can work together.

Traceability: Every change has history (who/when/what).

Automation: CI/CD pipelines always use latest version.

Rollback: Easily revert to a stable version if deployment fails.

👉 In short: SCM is the backbone of DevOps.

3️⃣ Git Three-Stage Architecture
graph LR
  A[Working Directory] --> B[Staging Area]
  B --> C[Git Repository]


Working Directory: Where you modify files.

Staging Area (Index): Prepares changes before committing.

Repository (.git folder): Stores permanent history (commits).

🔹 Example:

Edit file → (Working Dir)

git add file → (Staging Area)

git commit -m "msg" → (Repository)

4️⃣ Key Git Terms

Repository (Repo): Project + .git history.

Commit: A snapshot (has unique SHA-1 hash).

Tags: Labels for important commits (e.g., v1.0).

Push: Upload commits → remote repo (GitHub/GitLab).

Pull: Download + merge commits → local repo.

5️⃣ Git Branching

Branch = parallel workspace for features/bugfixes.

Default branch → master or main.

Work is isolated until merged.

🔧 Common Branch Commands:
```bash
git branch              # List branches
git branch feature-x    # Create branch
git checkout feature-x  # Switch branch
git merge feature-x     # Merge branch into current
git branch -d feature-x # Delete branch
```


👉 Best practice: Always create a new branch for features/bugs, then merge via Pull Request.

6️⃣ Handling Merge Conflicts

Conflicts occur when two branches change the same file differently.

Steps to resolve:

Open file → manually edit conflicts.

Stage changes → git add <file>

Commit merge → git commit

Helpful Commands:
```bash

git log --merge → see conflicting commits

git diff → view differences

git merge --abort → stop merge

git reset --hard → reset changes
```

7️⃣ Basic Git Commands (Daily Use)
# Setup identity
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

# Start project
```bash
git init              # Initialize repo
git clone <url>       # Clone remote repo
```

# Workflow
```bash
git add <file>        # Stage file
git add .             # Stage all files
git commit -m "msg"   # Commit staged changes
git status            # Check status
git log               # View commit history
```

# Remote
```bash
git remote -v
git remote add origin <url>
git push origin main
git pull origin main
```

8️⃣ Advanced Git Features
🔹 Git Stash (Save work temporarily)
```bash
git stash          # Save current changes
git stash list     # Show stashes
git stash apply    # Reapply stash
git stash pop      # Apply + remove stash
git stash drop     # Delete stash
```
🔹 Cherry-Pick (Pick single commit)
```bash
git cherry-pick <commit_hash>
```
🔹 Rebase (Clean history)
```bash
git rebase main
```

Moves commits on top of another branch.

Keeps linear history.

🔹 Squash (Combine commits)

During rebase, combine multiple commits → one clean commit.

🔟 Quick Visual Summary

📂 Working Directory → git add → 📦 Staging Area → git commit → 🏛️ Repository
↔️ Branches for features → Merge/PR → Resolve conflicts → Push → CI/CD Pipeline

✨ This version is exam-ready + interview-attractive because:

Uses structured bullet points.

Adds examples.

Includes visual flow & command blocks.

Looks like a professional cheatsheet.
