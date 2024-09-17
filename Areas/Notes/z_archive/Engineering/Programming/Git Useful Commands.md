---
up: 
tags: []
---
### Git revert all changes and come back into initial state

``` sh 
git reset --hard HEAD
```

### Git rename current branch

```sh
git branch -m <new_branch_name>
```

### Git delete branch


```sh
git push -d <remote_name> <branchname>

git branch -d <branch_name>
git branch -D <branch_name> 
```

The -D option is an alias for `--delete` `--force`, which deletes the branch
"irrespective of its merged status." 
