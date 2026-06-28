````markdown
# git bisect

The `git bisect` command helps find the commit that introduced a bug using binary search.

## Start bisect

```bash
git bisect start
```

## Mark current commit as bad

```bash
git bisect bad
```

## Mark a known good commit

```bash
git bisect good <commit-id>
```

## Finish bisect

```bash
git bisect reset
```

This command is useful for debugging large projects.
````
