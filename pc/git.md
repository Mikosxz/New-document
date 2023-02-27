# Git

## graph

```mermaid
graph LR
A[workspace] --> B(add)
    B --> C[index/stage area]
    C --> D(commit)
    D --> E[Head]
    E --> F(pull)
    F --> G[local repository]
    G --> H(push)
    H --> I[remote repository]
```

## command

git init

git config --global user.name "name"

git config --global user.email "mark@example.com"

git config --global --list

git add .

git add *

git commit -m "message"

git push

git pull

git checkout

git fetch/clone 

git reset

git status

git log

.gitignore

git rm -r --cached .

ssh-keygen -t rsa

git remote add name url

git remote -v

git remote remove repo

## learn git branching

git checkout bugFix

git commit

git checkout main

git commit

git merge bugFix

git rebase bugFix

--- relative refs

git checkout bugFix^

git checkout HEAD^

git checkout HEAD~4

git branch -f main HEAD~3

git branch -f bugFIx c4

git reset main

git revert HEAD~3

git cherry-pick c2 c4

git rebase -i HEAD~4

```
! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'github.com:ZeroMarker/coding.git'
```
git pull --rebase github master

```
github
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
```