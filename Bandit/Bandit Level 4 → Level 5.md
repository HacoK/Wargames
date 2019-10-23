# Bandit Level 4 → Level 5

## Level Goal

The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

## Commands you may need to solve this level

ls, cd, cat, file, du, find



```
ssh bandit4@bandit.labs.overthewire.org -p 2220
pIwrPrtPN36QITSp3EQaw936yaFoFgAB

cd inhere
ls
# -file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
cat -- -file0{0..9}
###
▒▒▒▒▒▒~%        C[▒걱>▒▒| ▒▒▒▒U"7▒w▒▒▒H▒▒ê▒Q▒▒(▒▒▒#▒▒▒▒T▒v▒▒(▒ִ▒▒▒▒▒A*▒
2J▒Ş؇_▒y7▒.A▒▒u▒▒#▒▒▒w$N?c▒-▒▒Db3▒▒=▒▒=<▒W▒▒▒▒▒ht▒Z▒▒!▒▒{▒U
                                                           ▒+▒▒pm▒▒▒;▒▒:D▒▒^▒▒@▒gl▒Q▒▒@▒%@▒▒▒ZP*E▒▒1▒V▒▒▒̫*▒▒▒▒koReBOKuIDDepwhWk7jZC0RTdopnAYKh
FPn▒
    '▒U▒▒▒M▒▒/u
XS
▒mu▒z▒▒▒хN▒{▒▒Y▒d4▒▒▒]3▒▒▒▒▒9(▒
Q▒▒▒bandit4@
###
!!! The password is koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```

