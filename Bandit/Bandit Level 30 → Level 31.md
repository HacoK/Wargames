# Bandit Level 30 → Level 31

## Level Goal

There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

## Commands you may need to solve this level

git



```
ssh bandit30@bandit.labs.overthewire.org -p 2220
5b90576bedb2cc04c86a9e924ce42faf

mkdir /tmp/bandit30_repo
cd /tmp/bandit30_repo
git clone ssh://bandit30-git@localhost/home/bandit30-git/repo
5b90576bedb2cc04c86a9e924ce42faf
cd repo

cat README.md
#just an epmty file... muahaha

git show-ref
/*
3aa4c239f729b07deb99a52f125893e162daac9e refs/heads/master
3aa4c239f729b07deb99a52f125893e162daac9e refs/remotes/origin/HEAD
3aa4c239f729b07deb99a52f125893e162daac9e refs/remotes/origin/master
f17132340e8ee6c159e0a4a6bc6f80e1da3b1aea refs/tags/secret
*/

git show f17132340e8ee6c159e0a4a6bc6f80e1da3b1aea
#47e603bb428404d265f59c42920d81e5
```

