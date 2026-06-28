# Project 1: Enterprise Git Repository Setup

## Project Overview

This hands-on project demonstrates the complete lifecycle of creating and managing a Git repository following industry-standard practices. It covers repository initialization, version control, branching, tagging, and preparing a project for collaboration.

By completing this project, you will understand the Git workflow used by professional software development and DevOps teams.

---

# Project Objectives

* Initialize a Git repository
* Configure Git
* Track project files
* Create meaningful commits
* Create and manage branches
* Merge changes
* Tag releases
* View repository history
* Follow Git best practices

---

# Project Architecture

```text
Developer
     │
     ▼
Create Project
     │
     ▼
Initialize Git
     │
     ▼
Configure Git
     │
     ▼
Create Project Files
     │
     ▼
Stage Changes
     │
     ▼
Commit Changes
     │
     ▼
Create Feature Branch
     │
     ▼
Merge Changes
     │
     ▼
Create Release Tag
```

---

# Prerequisites

* Git installed
* Terminal or Git Bash
* Basic Linux or Windows command-line knowledge

Verify Git installation:

```bash
git --version
```

---

# Step 1 — Create a Project Directory

```bash
mkdir devops-demo

cd devops-demo
```

---

# Step 2 — Initialize Git

```bash
git init
```

Expected output:

```text
Initialized empty Git repository
```

---

# Step 3 — Configure Git

Configure your username:

```bash
git config --global user.name "Your Name"
```

Configure your email:

```bash
git config --global user.email "your@email.com"
```

Verify configuration:

```bash
git config --list
```

---

# Step 4 — Create Project Files

Create a README file:

```bash
touch README.md
```

Create a project folder:

```bash
mkdir src
```

Create a sample file:

```bash
touch src/app.txt
```

Example structure:

```text
devops-demo/
│
├── README.md
└── src/
    └── app.txt
```

---

# Step 5 — Check Repository Status

```bash
git status
```

Git displays all untracked files.

---

# Step 6 — Stage Files

Stage every file:

```bash
git add .
```

Verify:

```bash
git status
```

---

# Step 7 — Create the First Commit

```bash
git commit -m "Initial project setup"
```

Each commit should have a clear and descriptive message.

---

# Step 8 — View Commit History

```bash
git log
```

Compact view:

```bash
git log --oneline
```

---

# Step 9 — Create a Feature Branch

```bash
git switch -c feature/documentation
```

Verify:

```bash
git branch
```

Current branch is highlighted with `*`.

---

# Step 10 — Update Documentation

Edit `README.md` and add project information.

Stage changes:

```bash
git add README.md
```

Commit:

```bash
git commit -m "Add project documentation"
```

---

# Step 11 — Merge Feature Branch

Return to the main branch:

```bash
git switch main
```

Merge:

```bash
git merge feature/documentation
```

---

# Step 12 — Create a Release Tag

Create Version 1.0:

```bash
git tag v1.0.0
```

List tags:

```bash
git tag
```

---

# Final Repository Structure

```text
devops-demo/
│
├── README.md
├── src/
│   └── app.txt
└── .git/
```

---

# Best Practices

* Commit frequently with meaningful messages.
* Use feature branches for new work.
* Keep commits focused on a single change.
* Tag important releases.
* Review repository status before committing.
* Never commit sensitive information such as passwords or API keys.

---

# Common Mistakes

❌ Committing directly to the `main` branch.

❌ Using vague commit messages.

```text
update
fix
changes
```

Instead use:

```text
Add authentication module

Update deployment documentation

Fix Docker configuration
```

❌ Forgetting to check `git status`.

❌ Tracking temporary or generated files.

---

# Troubleshooting

## View Repository Status

```bash
git status
```

## View Commit History

```bash
git log --oneline
```

## Undo Last Commit (Keep Changes)

```bash
git reset --soft HEAD~1
```

## Restore a File

```bash
git restore README.md
```

---

# Skills Practiced

* Repository Initialization
* Git Configuration
* File Tracking
* Commit Management
* Branch Management
* Merge Operations
* Release Tagging
* Repository Inspection

---

# Real-World DevOps Scenario

A DevOps engineer begins a new Infrastructure as Code (IaC) project.

They:

1. Create a new Git repository.
2. Configure Git.
3. Add Terraform configuration files.
4. Commit the initial project.
5. Create feature branches for infrastructure updates.
6. Merge reviewed changes into the main branch.
7. Tag stable infrastructure releases before deployment.

This workflow ensures traceability, collaboration, and version control across the infrastructure lifecycle.

---

# Learning Outcomes

After completing this project, you should be able to:

* Create and initialize Git repositories.
* Manage project history with commits.
* Organize work using feature branches.
* Merge changes safely.
* Tag project releases.
* Apply Git best practices used in professional DevOps environments.

---

# References

* Git Documentation: https://git-scm.com/docs
* Pro Git Book: https://git-scm.com/book/en/v2
* GitHub Documentation: https://docs.github.com/
