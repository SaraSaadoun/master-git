# master-git

Git Commands:

1. Staging Area (Add & Remove)
- Add (now it is tracked file)

``` 
git add file.py  # add a specific file
git add . # add all
```

- Remove (now it is untracked file `U`)

```
git reset head file.py 
```

# Remote
- push
```
git push remote_name branch_name
```
to know the remote name, use
```
git remote -v
```
you will see `origin`
now, as I've not created any branchs yet, it is the `main` branch 
```
git push origin main
```


```
git pull origin # = fetch + merge local with fetched data
```

- list config:
```
git config --list # or -l
git help config # open git manual
git config --global user.email # get the configured email
git config --global user.email "sarasaadoun4@gmail.com" # set email
git config --global --unset user.email # unset email
git config --global --edit

```
- alias
```
git config --global alias.st status
```
# Steps for initializing git on your local repo, then linking it with a remote repo
```
git init
git remote add origin your_github_repo_link
git push -u origin main # -u means to pull first then push
```

# Branch
```
git branch # get all branches

git branch feat1 # create

git checkout feat1 # goto

git checkout -b feat1 # create + goto
```

## Merging branch
- locally 
```
git checkout main
git merge feat1
git branch -d feat1 # delete it
```

- delete branch note:
```
git branch -d feat1 # will work only if the branch is merged
git branch -D feat1 # will delete the branch whether it has already been deleted or not.
```

- push branch
```
git checkout feat1
git push origin feat1 # creates and push to remote feat1 branch 
```

# Stash
- stash
```
git stash # to save your work for later when you're not ready to commit yet.
```

- list
```
git stash list
```

- pop
```
git stash pop # Applies the most recent stash and removes it from the stash list.
```
 if you got error msg due to some modification in one of the stashed file, you can restore it first (but you will lose the current modifications) using `git restore filename`
- apply
```
git stash apply # Applies the most recent stash but keeps it in the stash list.
```