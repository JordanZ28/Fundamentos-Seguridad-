# Retos Bandit 
# Bandido Nivel 16 → Nivel 17
# Objetivo 
Las credenciales para el siguiente nivel se pueden recuperar enviando el archivo contraseña del nivel actual a **un puerto en localhost en el rango De 31000 a 32000**. Primero averigüe cuáles de estos puertos tienen un servidor escuchándolos. A continuación, averigüe cuáles de ellos hablan SSL y cuáles No. Solo hay 1 servidor que dará las siguientes credenciales, el otros simplemente te enviarán lo que tú le envíes.

# Datos de acceso al nivel 
bandit16
ssh -l bandit16 bandit.labs.overthewire.org -p 2220
JQttfApK4SeyHwDlI9SXGR50qclOAil1
# Solución 
```
bandit16@bandit:~$ nmap 127.0.0.1 -p 31000-32000
Starting Nmap 7.80 ( https://nmap.org ) at 2024-02-21 18:10 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00011s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.05 seconds
bandit16@bandit:~$
bandit16@bandit:~$ which nmap
/usr/bin/nmap
bandit16@bandit:~$ which nc
/usr/bin/nc
bandit16@bandit:~$ nc -vz localhost 31000-32000 2>/dev/null | freo succ
Command 'freo' not found, did you mean:
  command 'free' from deb procps (2:3.3.17-6ubuntu2)
Try: apt install <deb name>
bandit16@bandit:~$ nc -vz localhost 31000-32000 2>/dev/null | grep succ
bandit16@bandit:~$ nc -vz localhost 31000-32000 2>&1 | grep succ
Connection to localhost (127.0.0.1) 31046 port [tcp/*] succeeded!
Connection to localhost (127.0.0.1) 31518 port [tcp/*] succeeded!
Connection to localhost (127.0.0.1) 31691 port [tcp/*] succeeded!
Connection to localhost (127.0.0.1) 31790 port [tcp/*] succeeded!
Connection to localhost (127.0.0.1) 31960 port [tcp/*] succeeded!
bandit16@bandit:~$


bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 20 17:50:06 2024 GMT; NotAfter: Feb 20 17:51:06 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEQ9wEgDANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjIwMTc1MDA2WhcNMjQwMjIwMTc1MTA2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDA
gdd50zQdwKnADuCYAoUSFvGreD2Mr/e6QZK+31XsKXCd/+cGHdmkqerggVlwno8T
3lmAaRw+Pk/nNdn3xJEGGq5guV2YhAnT+IQgP6+76ii/4gUCQxnaTtmslJDSfv7i
km+qYsFRL1YdtOo5od2etkLdorXGqGcIrB6ilCgKgQ2Q7FqMjh7n37HPk8yaWCwX
M/JZ7jkXw4mf2Un9UILgo/oJfR0JhMq6cDkHztG0E6j5ruknDeeOMGimH9pmzaa9
xdJe1GTtk+v03FIng0IfHi0HVPUCN8dl9rKLzn/LKZ3UftyffIErE7nDCLaGpVBK
DQzkq5gMPShGa1RT7nkFAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBh
XmVUELbEPhoHaMrhwHyd24bRzYiiOemi75OA6QywOLh7moC8MGKvtI0mHhhA+lfB
eEvOOPwL5om4culG+KnC24fdWzwX/PPtkYKocNSrIQINrVhTwBbGwnC+WCSYizZS
43Zav+szrJ6H66qO4x4wXU9p1qC24dIpY5dfBsy4m8P/XzUtg68YJng1EIuGM6DF
CnMWXUB0cfUgBsbWPMrQlJd5sHifKeglK3kBCXn3zb9T881YbLNAwMK2a5SnPdh8
eTg1e7pdNYwPvHcxYPySGyQCkLpLHduWUxVNrUfsVHrxI6rrHynZ5vv4+ulAmhAc
YoU33/wx/D1oycw1GLHh
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 4D7367AA1AA4396EB8AC30B2673D85CCCAC4CB52458FD6AC1BDA95283CBEE58C
    Session-ID-ctx:
    Resumption PSK: 80A8C62C5FE079AA9AF9DD7113044B458EE2936913362338F311B530584037815A39E605FBD7A63994E3AB0EE77D6A21
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 92 ed 0d d5 75 f9 0c 95-ed 08 73 73 af f3 6c c3   ....u.....ss..l.
    0010 - c6 65 a2 ca ca 7d 72 c5-e3 82 2a ad 45 4d 65 cb   .e...}r...*.EMe.
    0020 - a5 28 c8 54 b5 49 80 76-f8 7b 30 0c 62 c0 49 61   .(.T.I.v.{0.b.Ia
    0030 - b1 3e f0 59 f0 8a ae e5-12 86 d1 7d 82 bd cf 18   .>.Y.......}....
    0040 - cd 6a 55 cc 91 a3 43 d5-99 c8 30 98 91 2d b0 1d   .jU...C...0..-..
    0050 - 92 08 2c 79 a3 11 f5 c9-86 01 a4 c5 c1 06 a8 2c   ..,y...........,
    0060 - 0b 40 6b 6e 85 35 78 88-c3 83 f6 e6 a5 24 8a fe   .@kn.5x......$..
    0070 - 1d 9e 1b 84 72 50 43 ef-ac 6d fa c1 f0 1d 6a 3c   ....rPC..m....j<
    0080 - a3 8b bf a8 59 e2 b4 28-6c 18 2e 31 86 0b 20 45   ....Y..(l..1.. E
    0090 - 9c 7d 25 39 17 a2 80 36-ed 4c e1 c0 86 41 74 66   .}%9...6.L...Atf
    00a0 - 17 c0 ea 5b 14 1e 28 b3-d0 87 0f c8 d0 2c 3a 90   ...[..(......,:.
    00b0 - 46 7e a6 10 fc 1c 72 03-75 bb 46 3a 85 a5 a4 a7   F~....r.u.F:....
    00c0 - 81 61 0e b5 ae 66 58 e9-52 6a 84 5f cd cc 7e 9f   .a...fX.Rj._..~.

    Start Time: 1708539442
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 6A86371D62296BB4669CA75D2BF5535362B69784A30D70C3CF7038B9785C4A07
    Session-ID-ctx:
    Resumption PSK: 1A2CB0973B99D4A604F26A8B9CE093B18F5655786EED74CB754F61EFBE6FBB0213E2F900CD6DFD883E485E895DA79167
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 92 ed 0d d5 75 f9 0c 95-ed 08 73 73 af f3 6c c3   ....u.....ss..l.
    0010 - fd 0f c5 35 8b 26 ba 0b-21 30 fc 5f d7 a5 56 5d   ...5.&..!0._..V]
    0020 - 9b 3f 1c df 61 ef e4 bd-5c 1e e2 28 25 7d 6d ad   .?..a...\..(%}m.
    0030 - 13 02 37 40 de 44 e3 f4-27 a6 a6 a5 8a 8d 05 11   ..7@.D..'.......
    0040 - 8b 96 75 4b 36 e7 23 f0-b5 c0 35 7b ec 60 1d 29   ..uK6.#...5{.`.)
    0050 - a4 1f d0 af da ca fd d8-bb c4 cd 61 ad 50 8e 65   ...........a.P.e
    0060 - 34 f4 d1 f8 58 5a 93 cd-d8 77 6e 8e c4 96 9a 6a   4...XZ...wn....j
    0070 - 16 e1 2e f8 7c e3 95 1c-e2 c2 26 f5 36 2f 06 cf   ....|.....&.6/..
    0080 - 91 4e 6a 2f a2 22 30 e5-89 13 49 6d aa 61 65 87   .Nj/."0...Im.ae.
    0090 - 8c 71 fc 18 7b c4 2c 68-9a 17 c4 cc c3 6a 94 ad   .q..{.,h.....j..
    00a0 - e0 48 af d8 33 78 54 89-fa 40 01 55 4e 16 cd 74   .H..3xT..@.UN..t
    00b0 - 2c 4d 34 48 f3 71 63 0c-ae 99 a9 c3 af 1e a7 02   ,M4H.qc.........
    00c0 - bc 7e b0 2c 09 8b 56 db-2c a8 4d 1e e9 7b 81 7b   .~.,..V.,.M..{.{

    Start Time: 1708539442
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
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
bandit16@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:\Users\jorda>

```

# Notas 
El comando nmap nos puede servir como ayuda a la hora de rastreó de puestos 