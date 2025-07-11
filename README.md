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
# or
git restore --staged file.py
```

- clean unstaged files
```
git clean -n # show files that will be deleted
git clean -f # remove them
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

git stash save "File1 and File2" # add stash name
```
- list
```
git stash list
```

- pop

git stash pop # Applies the most recent stash and removes it from the stash list.
```
 if you got error msg due to some modification in one of the stashed file, you can restore it first (but you will lose the current modifications) using `git restore filename`

```
 git stash 
- apply
```
git stash apply # Applies the most recent stash but keeps it in the stash list.
```


Note that pop and apply -> get the latest stash 

So, if you need a specific one, you can get it by id

```
git stash pop stash@{2}
```


- drop
```
git stash drop # rem the latest
git stash drop stash@{1}
```

- show
```
git stash show stash@{1} # show content in stash
```

- clear
clear all 
```
git stash clear
```

# commit
you can go to a specific previous commit using:
```
git reset --hard commit_hash 
```
but note that other newer commits will still be there.
Then, update the main repo:
```
git push origin main --force
```
Now the remote repo is updated and all following commits will be deleted there



Notes:

1. --hard
```
git reset --hard <commit-hash>
```
Moves HEAD to the specified commit.

Deletes all changes in the staging area and working directory.

2. --soft

```
git reset --soft <commit-hash>
```
Moves HEAD to the specified commit.

Keeps changes in the staging area (index).

Your files still look like they were committed — just uncommitted now.


# Tag
```
git tag v1.0 # create tag
git tag # show
git push origin main v1.0 # push it (lightweight tag "get its msg from commit msg")

```
adjust the msg of the tag yourself
```
git tag -a v2.0 -m "second version"
```