# Bandit Level 12 → Level 13

## Level Goal

The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp, mv, file

## Helpful Reading Material

- [Hex dump on Wikipedia](https://en.wikipedia.org/wiki/Hex_dump)



```
ssh bandit12@bandit.labs.overthewire.org -p 2220
5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

mkdir /tmp/haco
cp data.txt /tmp/haco
cd /tmp/haco

xxd -r data.txt > bandit
file bandit
# bandit: gzip compressed data, was "data2.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
mv bandit bandit.gz
gzip -d bandit.gz
file bandit
# bandit: bzip2 compressed data, block size = 900k
mv bandit bandit.bz2
bzip2 -d bandit.bz2
file bandit
# bandit: gzip compressed data, was "data4.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
mv bandit bandit.gz
gzip -d bandit.gz
file bandit
# bandit: POSIX tar archive (GNU)
tar -xvf bandit
# data5.bin
file data5.bin
# data5.bin: POSIX tar archive (GNU)
tar -xvf data5.bin
# data6.bin
file data6.bin
# data6.bin: bzip2 compressed data, block size = 900k
mv data6.bin data6.bz2
bzip2 -d data6.bz2
file data6
# data6: POSIX tar archive (GNU)
tar -xvf data6
# data8.bin
file data8.bin
# data8.bin: gzip compressed data, was "data9.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
mv data8.bin data8.gz
gzip -d data8.gz
file data8
# data8: ASCII text
cat data8
# The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
```

