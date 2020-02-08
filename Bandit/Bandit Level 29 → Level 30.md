# Bandit Level 29 → Level 30

## Level Goal

There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

## Commands you may need to solve this level

git



```
ssh bandit29@bandit.labs.overthewire.org -p 2220
bbc96594b4e001778eee9975372716b2

mkdir /tmp/bandit29_repo
cd /tmp/bandit29_repo
git clone ssh://bandit29-git@localhost/home/bandit29-git/repo
bbc96594b4e001778eee9975372716b2
cd repo

ls #README.md
cat README.md
/*
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>
*/

git branch -a
/*
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
*/

git checkout remotes/origin/dev
cat README.md
/*
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: 5b90576bedb2cc04c86a9e924ce42faf
*/
```