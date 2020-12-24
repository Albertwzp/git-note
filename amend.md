## config name & email
git config user.name "Albertwzp"
git config user.email "wzp.albert@gmail.com"

## amend last commit
git commit --amend --author="Albertwzp <wzp.albert@gmail.com>"

## amend batch
```shell
git filter-branch --env-filter '
if [ "$GIT_AUTHOR_NAME" = "oldName" ]
then
export GIT_AUTHOR_NAME="newName"
export GIT_AUTHOR_EMAIL="newEmail"
fi
' ${ref}..HEAD

git filter-branch --env-filter '
if [ "$GIT_COMMITTER_NAME" = "oldName" ]
then
export GIT_COMMITTER_NAME="newName"
export GIT_COMMITTER_EMAIL="newEmail"
fi
' ${ref}..HEAD
```
