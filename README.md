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