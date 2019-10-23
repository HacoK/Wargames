# Bandit Level 8 → Level 9

## Level Goal

The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

## Helpful Reading Material

- [The unix commandline: pipes and redirects](http://www.westwind.com/reference/os-x/commandline/pipes.html)



```
ssh bandit8@bandit.labs.overthewire.org -p 2220
cvX2JJa4CFALtqS87jk27qwqGhBM9plV

sort data.txt|uniq -u
# UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```

