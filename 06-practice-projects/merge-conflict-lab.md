# Merge Conflict Resolution Lab

## Overview

Merge conflicts occur when Git cannot automatically combine changes from two branches because the same lines of code have been modified differently.

Understanding how to identify, resolve, and verify merge conflicts is an essential skill for software developers and DevOps engineers working in collaborative environments.

---

# Learning Objectives

By completing this lab, you will learn how to:

* Create feature branches
* Simulate a merge conflict
* Identify conflict markers
* Resolve conflicts manually
* Complete the merge
* Verify repository history

---

# Prerequisites

* Git installed
* Basic Git knowledge
* Terminal or Git Bash
* A local Git repository

---

# Lab Architecture

```text
                    main
                      │
        ┌─────────────┴─────────────┐
        │                           │
        ▼                           ▼
feature/login              feature/dashboard
        │                           │
        │ Modify same file          │ Modify same file
        └─────────────┬─────────────┘
                      │
                      ▼
              Merge Conflict
                      │
                      ▼
           Manual Conflict Resolution
                      │
                      ▼
                Successful Merge
```

---

# Step 1 — Create a Repository

```bash
mkdir merge-conflict-lab

cd merge-conflict-lab

git init
```

---

# Step 2 — Create README

```bash
touch README.md
```

Add:

```text
Version 1
```

Stage and commit.

```bash
git add .

git commit -m "Initial commit"
```

---

# Step 3 — Create First Branch

```bash
git switch -c feature/login
```

Modify README.

```text
Version 1

Login Module Added
```

Commit.

```bash
git add .

git commit -m "Add login module"
```

---

# Step 4 — Create Second Branch

Return to main.

```bash
git switch main
```

Create another branch.

```bash
git switch -c feature/dashboard
```

Modify the same file.

```text
Version 1

Dashboard Module Added
```

Commit.

```bash
git add .

git commit -m "Add dashboard module"
```

---

# Step 5 — Merge Branches

Return to main.

```bash
git switch main
```

Merge the first branch.

```bash
git merge feature/login
```

Now merge the second branch.

```bash
git merge feature/dashboard
```

Git will report a merge conflict.

Example:

```text
CONFLICT (content): Merge conflict in README.md

Automatic merge failed.
```

---

# Step 6 — Inspect Conflict

Open README.md.

Git inserts conflict markers.

```text
<<<<<<< HEAD

Login Module Added

=======

Dashboard Module Added

>>>>>>> feature/dashboard
```

These markers indicate conflicting changes.

---

# Step 7 — Resolve Conflict

Edit the file manually.

Example:

```text
Version 1

Login Module Added

Dashboard Module Added
```

Remove all conflict markers.

Save the file.

---

# Step 8 — Mark Conflict as Resolved

```bash
git add README.md
```

---

# Step 9 — Complete Merge

```bash
git commit -m "Resolve merge conflict between login and dashboard features"
```

---

# Step 10 — Verify History

View commit history.

```bash
git log --oneline --graph --all
```

Example output:

```text
* Merge Commit
|\
| * Dashboard Commit
* | Login Commit
|/
* Initial Commit
```

---

# Common Conflict Scenarios

* Two developers edit the same line.
* Two developers rename the same file.
* One developer deletes a file while another modifies it.
* Simultaneous updates to configuration files.
* Documentation changes made in parallel.

---

# Best Practices

* Pull changes frequently.
* Keep feature branches short-lived.
* Commit small, focused changes.
* Resolve conflicts immediately.
* Review merged code before deployment.
* Communicate with teammates during active development.

---

# Common Mistakes

❌ Force deleting conflicted files.

❌ Ignoring conflict markers.

❌ Committing unresolved conflicts.

❌ Working directly on the `main` branch.

❌ Resolving conflicts without testing.

---

# Real-World DevOps Scenario

A development team is building an e-commerce platform.

* Developer A implements user authentication.
* Developer B updates the same authentication configuration.
* Both create Pull Requests.
* During merge, Git detects conflicting changes.
* The conflict is resolved manually.
* Automated CI pipelines validate the merged code.
* The application is deployed successfully.

This workflow is common in enterprise software development.

---

# Troubleshooting

## View Current Status

```bash
git status
```

## Abort Merge

```bash
git merge --abort
```

## Continue After Resolution

```bash
git add .

git commit
```

---

# Interview Questions

### What is a merge conflict?

A merge conflict occurs when Git cannot automatically combine changes made to the same section of a file.

---

### How do you resolve a merge conflict?

1. Open the conflicted file.
2. Remove conflict markers.
3. Keep the correct code.
4. Save the file.
5. Stage the changes.
6. Complete the merge with a commit.

---

### How can merge conflicts be reduced?

* Pull frequently.
* Use feature branches.
* Keep commits small.
* Communicate with teammates.
* Merge regularly.

---

# Skills Practiced

* Git Branching
* Git Merge
* Conflict Resolution
* Git Status
* Git Log
* Team Collaboration
* DevOps Workflow

---

# References

Git Merge Documentation

https://git-scm.com/docs/git-merge

Git Merge Conflicts

https://docs.github.com/en/get-started/using-git/resolving-merge-conflicts-after-a-git-rebase
