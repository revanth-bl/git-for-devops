# Git Push

## Overview

The `git push` command uploads local commits to a remote Git repository. It is commonly used to synchronize local development with remote repositories such as GitHub, GitLab, or Bitbucket.

---

## Syntax

```bash
git push <remote> <branch>
```

---

## Example

```bash
git push origin main
```

Push a newly created branch:

```bash
git push -u origin feature/authentication
```

---

## Options

| Option | Description |
|---------|-------------|
| -u | Set upstream branch |
| --force | Force push |
| --tags | Push all tags |

---

## Real-World DevOps Example

After implementing a new CI/CD pipeline, developers push their changes to GitHub:

```bash
git add .
git commit -m "Configure GitHub Actions pipeline"
git push origin main
```

The push automatically triggers the CI/CD workflow.

---

## Best Practices

- Pull latest changes before pushing.
- Avoid using `--force` on shared branches.
- Use descriptive commit messages.

---

## Common Errors

### Rejected Push

```
failed to push some refs
```

Solution:

```bash
git pull origin main
git push origin main
```

---

## Related Commands

- git fetch
- git pull
- git clone

---

## References

https://git-scm.com/docs/git-push