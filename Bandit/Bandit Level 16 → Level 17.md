# Bandit Level 16 → Level 17

## Level Goal

The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

## Commands you may need to solve this level

ssh, telnet, nc, openssl, s_client, nmap

## Helpful Reading Material

- [Port scanner on Wikipedia](https://en.wikipedia.org/wiki/Port_scanner)



```
ssh bandit16@bandit.labs.overthewire.org -p 2220
cluFn7wTiGryunymYOu4RcffSxQluehd

nmap -p 31000-32000 localhost
/*
Starting Nmap 7.40 ( https://nmap.org ) at 2020-02-05 18:31 CET
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00023s latency).
Not shown: 999 closed ports
PORT      STATE SERVICE
31518/tcp open  unknown
31790/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.10 seconds
*/

openssl s_client -connect localhost:31518
/*
CONNECTED(00000003)
depth=0 CN = localhost
verify error:num=18:self signed certificate
verify return:1
depth=0 CN = localhost
verify return:1
---
Certificate chain
 0 s:/CN=localhost
   i:/CN=localhost
---
Server certificate
-----BEGIN CERTIFICATE-----
MIICBjCCAW+gAwIBAgIETW4bJzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjAwMTA1MTU1NzU4WhcNMjEwMTA0MTU1NzU4WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwgZ8wDQYJKoZIhvcNAQEBBQADgY0AMIGJAoGBAMMv0GC9
Sx0BBXj1L9tYJZ+f2FD5ww++6E2NJ2BYj6/45SgePi5SObxeyRhxAmCeHW+zWic0
YNIqGYZGArUakII7fvF4rJYrwcE6kzbhuDK/YKyENtqFcEnXL59IJjzs2A5B07dh
D7yTes4K2Lf5jhh8TYV4/gJ3190ivmq0jIojAgMBAAGjZTBjMBQGA1UdEQQNMAuC
CWxvY2FsaG9zdDBLBglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0
ZWQgYnkgTmNhdC4gU2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3
DQEBBQUAA4GBAMEGhPKv5PaYgpegqjlovdOLbdS3baqhwGTWBYRBfdezipWySYdg
zNlZY1dUnNI4sW88uDeQ47vXfipCAA9xx/HCdqj1znDb+0lA1DEwpg3yoHQNEhFJ
BNwYPelhnHkZs1kyUi19gFEuwyrtstOFvhPSHKfiR1VH7sAYpiOADks+
-----END CERTIFICATE-----
subject=/CN=localhost
issuer=/CN=localhost
---
No client certificate CA names sent
Peer signing digest: SHA512
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1019 bytes and written 269 bytes
Verification error: self signed certificate
---
New, TLSv1.2, Cipher is ECDHE-RSA-AES256-GCM-SHA384
Server public key is 1024 bit
Secure Renegotiation IS supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
SSL-Session:
    Protocol  : TLSv1.2
    Cipher    : ECDHE-RSA-AES256-GCM-SHA384
    Session-ID: 0D5FE449C23D4F49E221D8B54505DDA5FE6D38AF7336AB5618A94C5FD53249A3
    Session-ID-ctx:
    Master-Key: F8FA372AEA25BB97F553E6F1CC0AEA98C9C738EFCDDD526CC59C6ECD27E5C37CBC19475A2449E230BE55B7040D3AB1EF
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - dd 0c df 05 d4 49 65 b0-fa b3 69 c5 b1 91 d0 c6   .....Ie...i.....
    0010 - 0f 8c 44 cf 3d 54 4f f4-31 8d 64 7f 55 1c c3 e1   ..D.=TO.1.d.U...
    0020 - 64 f5 b9 55 15 14 e4 29-52 33 cc a3 0e fc 99 b6   d..U...)R3......
    0030 - 8a e5 7f 52 b8 f9 9b a8-2d 86 32 47 da d4 16 b4   ...R....-.2G....
    0040 - d3 19 49 14 e4 a7 d3 56-cc ad 8f 4a a0 a7 8b 3c   ..I....V...J...<
    0050 - 7e 4e b9 54 4d 5e 04 6e-89 da 5e 0a 69 13 10 83   ~N.TM^.n..^.i...
    0060 - 93 ae 93 84 ea 8c a8 4a-c2 13 fb 17 c5 30 ea 65   .......J.....0.e
    0070 - 3a 80 80 46 9b 2e 05 9d-81 d8 75 c7 5a a5 c9 63   :..F......u.Z..c
    0080 - ef 3c 7a a0 6a 81 e9 84-d3 54 49 48 52 0c 16 4b   .<z.j....TIHR..K
    0090 - 65 0c 37 6a 06 22 ec ef-a2 8e 59 a4 35 85 89 6c   e.7j."....Y.5..l

    Start Time: 1580923989
    Timeout   : 7200 (sec)
    Verify return code: 18 (self signed certificate)
    Extended master secret: yes
---
cluFn7wTiGryunymYOu4RcffSxQluehd
cluFn7wTiGryunymYOu4RcffSxQluehd
^Z
*/

openssl s_client -connect localhost:31790
/*
CONNECTED(00000003)
depth=0 CN = localhost
verify error:num=18:self signed certificate
verify return:1
depth=0 CN = localhost
verify return:1
---
Certificate chain
 0 s:/CN=localhost
   i:/CN=localhost
---
Server certificate
-----BEGIN CERTIFICATE-----
MIICBjCCAW+gAwIBAgIEHYaZVDANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjAwMTA1MTU1NzU4WhcNMjEwMTA0MTU1NzU4WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwgZ8wDQYJKoZIhvcNAQEBBQADgY0AMIGJAoGBALnNkoES
dc+bJYmoBnjc43xt4n/zq0OIlxe37wkJzsH4Zkr5wHwoRTH4Q/g4MarLhcHpyFS7
YBT1hFdxG76tlWhQKjqe680PnxHMrZJFVtO/Gscl9luzalM/h2AebrJ0lX9pPTBX
Yrizk17mvyl50yYj9MLuvIAfb353gv3frwcRAgMBAAGjZTBjMBQGA1UdEQQNMAuC
CWxvY2FsaG9zdDBLBglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0
ZWQgYnkgTmNhdC4gU2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3
DQEBBQUAA4GBADRDuQtY5NX3aZpNcgracBO3f5fNhdTYp+qERd6xVhq5wdEn9iuJ
zXJh/halRZuriUnqoQmhhmHlBX4NGVVue+9OSh3yfGeNDkP+rnZ0Xji4gXRiBZao
+HCq5y9yG1sEufHUFCq2ZRZQ9IOghWiA/qxxGQQD+hocFVljquCricbf
-----END CERTIFICATE-----
subject=/CN=localhost
issuer=/CN=localhost
---
No client certificate CA names sent
Peer signing digest: SHA512
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1019 bytes and written 269 bytes
Verification error: self signed certificate
---
New, TLSv1.2, Cipher is ECDHE-RSA-AES256-GCM-SHA384
Server public key is 1024 bit
Secure Renegotiation IS supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
SSL-Session:
    Protocol  : TLSv1.2
    Cipher    : ECDHE-RSA-AES256-GCM-SHA384
    Session-ID: 141AD13162A5FCBF5679638CB0D9A63D5038489F5111BD8D2DB34EE1DD0CAC1A
    Session-ID-ctx:
    Master-Key: A34D5865B62A2F281C3A35758AA73AEBF3BAAB37C9C21BA3A801721CDC1613D2D91D528EE97DAEE6D153341FFE240BCC
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - ba ef 89 66 b0 7e fc 80-8f e1 37 6a 85 4c c3 2c   ...f.~....7j.L.,
    0010 - 64 80 cd 94 d7 5f c4 a3-e5 27 ef df b7 9d 8a 75   d...._...'.....u
    0020 - a2 41 80 f1 03 4f 67 26-ba 48 73 15 d8 25 e1 06   .A...Og&.Hs..%..
    0030 - f3 0b 17 9c 74 39 ff d0-c4 34 a5 8d a0 b8 45 21   ....t9...4....E!
    0040 - d3 29 85 4b 85 c5 2c ff-a2 84 20 07 44 6a 25 0a   .).K..,... .Dj%.
    0050 - 5d d6 3f cb 54 d8 54 07-f3 78 ca 24 fc 3f 1d 51   ].?.T.T..x.$.?.Q
    0060 - ed 94 b9 d1 5a 67 90 11-e8 a8 7f c2 5d 94 9f 7f   ....Zg......]...
    0070 - be 53 84 26 0a fa c5 44-bd ba 87 92 a5 d9 bb 2a   .S.&...D.......*
    0080 - ac 6b 0b 70 88 0f db 56-f1 ec 2d 11 4e b7 7e b9   .k.p...V..-.N.~.
    0090 - a7 ac c4 e3 42 3e ca 61-fa 61 44 e7 3d 60 50 d7   ....B>.a.aD.=`P.

    Start Time: 1580924074
    Timeout   : 7200 (sec)
    Verify return code: 18 (self signed certificate)
    Extended master secret: yes
---
cluFn7wTiGryunymYOu4RcffSxQluehd
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
*/
```

