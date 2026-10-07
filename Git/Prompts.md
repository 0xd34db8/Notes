### Forgot to fork
```git
git remote set-url origin <LINK>
```

```git
git push -u origin HEAD
```

If you want to overwrite the history and show only one single commit:

### Create a new history containing the current working tree

```
git checkout --orphan clean-main
```

### Stage everything

```
git add -A
```

### Create the single commit

```
git commit -m "initial commit"
```

### Replace the remote branch with this one-commit history
git branch -M main
git push --force origin main
