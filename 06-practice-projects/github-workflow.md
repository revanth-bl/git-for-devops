# GitHub Workflow

## Overview

The GitHub Workflow is a collaborative development process that enables multiple developers to work on the same project safely and efficiently. It combines Git version control with GitHub features such as Pull Requests, Branch Protection, and Continuous Integration (CI).

This workflow is widely adopted by software companies and DevOps teams to maintain code quality, improve collaboration, and automate deployments.

---

# Workflow Overview

```text
Developer
    │
    ▼
Clone Repository
    │
    ▼
Create Feature Branch
    │
    ▼
Develop Feature
    │
    ▼
Stage Changes
    │
    ▼
Commit Changes
    │
    ▼
Push Branch
    │
    ▼
Open Pull Request
    │
    ▼
Code Review
    │
    ▼
CI Pipeline Executes
    │
    ▼
Merge into Main
    │
    ▼
Deployment
```

---

# Prerequisites

* Git installed
* GitHub account
* Access to a remote repository
* Basic Git knowledge

---

# Step 1 — Clone the Repository

Clone the project from GitHub.

```bash
git clone https://github.com/username/project.git
```

Navigate into the repository.

```bash
cd project
```

---

# Step 2 — Create a Feature Branch

Never work directly on the **main** branch.

Create a new feature branch.

```bash
git switch -c feature/user-authentication
```

Verify the current branch.

```bash
git branch
```

---

# Step 3 — Develop Your Feature

Implement your changes.

Example:

* Add authentication
* Fix a bug
* Update documentation
* Improve performance

---

# Step 4 — Check Repository Status

```bash
git status
```

Review modified files before staging.

---

# Step 5 — Stage Changes

Stage all files.

```bash
git add .
```

Or stage individual files.

```bash
git add app.py
```

---

# Step 6 — Commit Changes

Create a meaningful commit message.

```bash
git commit -m "Implement user authentication"
```

Good commit messages describe **what changed**.

---

# Step 7 — Push Changes

Upload your feature branch.

```bash
git push -u origin feature/user-authentication
```

The **-u** flag sets the upstream branch.

---

# Step 8 — Open a Pull Request

On GitHub:

* Compare changes
* Describe the feature
* Request reviewers
* Wait for automated checks

A Pull Request allows teammates to review the code before merging.

---

# Step 9 — Code Review

Reviewers may:

* Approve the changes
* Request modifications
* Leave comments

Address all review feedback before merging.

---

# Step 10 — Continuous Integration

After opening a Pull Request, CI tools automatically execute tasks such as:

* Build project
* Run unit tests
* Execute integration tests
* Check code formatting
* Perform security scans

Common CI platforms include:

* GitHub Actions
* Jenkins
* GitLab CI
* Azure DevOps

---

# Step 11 — Merge the Pull Request

Once approved:

* Merge into `main`
* Delete the feature branch
* Pull the latest changes locally

```bash
git switch main

git pull origin main
```

---

# Branch Protection Rules

Production repositories should protect important branches.

Recommended rules:

* Require Pull Requests
* Require code review
* Require successful CI
* Restrict force pushes
* Restrict direct commits to main

---

# Best Practices

✅ Create one branch per feature

✅ Write descriptive commit messages

✅ Pull latest changes frequently

✅ Keep Pull Requests small

✅ Review code carefully

✅ Delete merged branches

✅ Protect the main branch

---

# Common Mistakes

❌ Working directly on `main`

❌ Huge Pull Requests

❌ Skipping code review

❌ Force pushing shared branches

❌ Generic commit messages

```
update
fix
changes
```

Instead use:

```
Implement JWT authentication

Fix Docker build failure

Update Kubernetes deployment manifest
```

---

# Real-World DevOps Scenario

A developer implements a new API endpoint.

Workflow:

1. Clone repository
2. Create feature branch
3. Develop feature
4. Commit changes
5. Push branch
6. Open Pull Request
7. Team reviews code
8. GitHub Actions executes tests
9. Pull Request approved
10. Merge into main
11. CI/CD pipeline deploys application

---

# Interview Questions

### Why shouldn't developers work directly on the main branch?

To protect production code and ensure changes are reviewed before deployment.

---

### What is a Pull Request?

A Pull Request is a request to merge changes from one branch into another after review.

---

### What happens after pushing a branch?

Developers usually open a Pull Request where automated CI pipelines execute builds and tests.

---

### Why use feature branches?

They isolate work, reduce conflicts, and improve collaboration.

---

# References

Official Git Documentation

https://git-scm.com/docs

GitHub Documentation

https://docs.github.com/

GitHub Flow

https://docs.github.com/en/get-started/using-github/github-flow
