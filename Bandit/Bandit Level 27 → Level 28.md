# Bandit Level 27 → Level 28

## Level Goal

There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.

## Commands you may need to solve this level

git



```
ssh bandit27@bandit.labs.overthewire.org -p 2220
3ba3118a22e93127a4ed485be72ef5ea

mkdir /tmp/bandit27_repo
cd /tmp/bandit27_repo

git clone ssh://bandit27-git@localhost/home/bandit27-git/repo
3ba3118a22e93127a4ed485be72ef5ea

ls #repo
cd repo
ls #README
cat README
#The password to the next level is: 0ef186ac70e04ea33b4c1853d2526fa2
```

