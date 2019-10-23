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
cat ./-file00
# probably contains system trap command, can't read that file
cat -- -file0{1..9}
# U"7wHêQ(# Tv(ִA*
2JŞ؇_y7.Au#w$N?c-Db3==W htZ!{U+pm;:D^@ glQ@%@ZP*E1V̫*koReBOKuIDDepwhWk7jZC0RTdopnAYKh
FPn'UM/uXS
muzхN{Yd4]3 9(
### The password is koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```

