# Retos Bandit 
# Bandido Nivel 15 → Nivel 16

# Objetivo 
La contraseña para el siguiente nivel se puede recuperar enviando el archivo contraseña del nivel actual al **puerto 30001 en localhost** usando Encriptación SSL.

**Nota útil: ¿Obtener "HEARTBEATING" y "Read R BLOCK"? Uso -ign_eof y lea la sección "COMANDOS CONECTADOS" en la página de manual. Junto a 'R' y 'Q', el comando 'B' también funciona en esta versión de ese mando...**
# Datos de acceso al nivel 
bandit14
ssh -l bandit14 bandit.labs.overthewire.org -p 2220
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
# Solución 
```
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 18 10:54:16 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 18 10:54:16 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 18 10:53:16 2024 GMT; NotAfter: Feb 18 10:54:16 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEcjY6OTANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjE4MTA1MzE2WhcNMjQwMjE4MTA1NDE2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCz
TX1NLedZhpQfXiWbWWD2BlNYjANpj+TnzUOI9ZbKJnOQJAbFfWZLA6No7XOStgje
+RPIoAHrX42G95VDfWtRms+qCsCTlUaS9291dZJQ3iOjBIE+PvmRcGdUlFJXDYa6
E61L2DKLbb8YSAnSuUPG3K7CtdxJpA5DpCBCmHEA9t5gZ5HGo9Gt9Kay9lhApX78
ocytwwHG15LplXI6LQB3ykhyCAcfljR3azd90T83dz7kLyM7yIMt60k1kemuX6RW
qSvkCvxmckRFoQPjwKZUopGLlhcC58Kb2xlwEGK+9j/ibBRkmEdBkOOeb5pJol7K
Wkd9LdG0nTWrggni7EKbAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQCA
j53OECoyjZMkHINZj35xk2kKQc9Jj9XjoCE0HlooUWd1ETik/2TkIbdWenozDrgH
10Jqmu/zAEhQkfFALBXCR7Vo0319yvR3rlnC2TdzMeBeUQ/n6ivPsCCL6SF8UTWT
XZJoTEfmp+Ma4zup/mEs23uO/FQ0J3LmSgICtXzPCA09M/ffj2UgTENdTHDltQxl
nQpzF+U40+bg/2PQ83XOTQJbZVbU2FnP/MitSYycxemLJXzbdsIxQhQy0VmTY73E
ZFemHVTbzEzcsCJRak4AyPZ9Zpi2uozHA8r1PqtnDzsN5FBFwuJxCuc+F8QeHh9e
QoyfsotkA6BO0LBqWNvE
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
    Session-ID: A63FAC03DD42916CFF7A2FADBC342ED2BE12CE099EFC9AB37841060A62CE91AA
    Session-ID-ctx:
    Resumption PSK: 7B01C072484BBFD15F799FB82F85E978362A589B75F954389E9DAEFBD3EE9823E1F365191AA53191D5B4A3F0A52257CF
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - dc 1b 67 7e 6b 49 ec f9-e1 0a 8a 6e cb ac b4 e6   ..g~kI.....n....
    0010 - f4 8b f2 b4 0b 30 ce 1c-91 cd 21 49 f7 ff b0 e8   .....0....!I....
    0020 - 44 51 62 b4 18 26 55 88-7f 64 b8 68 05 02 64 b1   DQb..&U..d.h..d.
    0030 - 08 79 c3 f4 3d 5a 13 3a-12 5e d5 f0 3f 3c fa ff   .y..=Z.:.^..?<..
    0040 - 91 44 90 9d 56 08 3c 8f-5d f8 1e 49 5f 3f b1 67   .D..V.<.]..I_?.g
    0050 - 57 96 b9 45 80 6e 5e c3-d1 1e 32 57 3b 4e 42 a3   W..E.n^...2W;NB.
    0060 - 16 37 a3 75 de 21 96 27-c0 a7 ee e4 b8 9b d3 06   .7.u.!.'........
    0070 - 0f 96 05 64 e5 a2 5d 0f-39 73 ce d9 fe d0 db c0   ...d..].9s......
    0080 - 55 f4 bd 66 7d 76 83 28-31 54 ec 0e 05 3d 0c 4f   U..f}v.(1T...=.O
    0090 - 37 88 25 03 d9 32 40 fa-d2 3a 79 93 d4 a7 34 be   7.%..2@..:y...4.
    00a0 - c8 25 31 16 11 b1 04 2f-6e 3c c1 88 f6 3a 19 c1   .%1..../n<...:..
    00b0 - 14 56 c7 4d 14 43 54 1a-e2 33 e7 8d a8 d4 ee 88   .V.M.CT..3......
    00c0 - 5e 92 95 e4 30 3e 9d e3-75 e9 85 ca 82 c5 27 27   ^...0>..u.....''

    Start Time: 1708370591
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
    Session-ID: 92DFF80A58435D34DD198F48E512B22A952CD990BA2D609430150DB8186ECC84
    Session-ID-ctx:
    Resumption PSK: 79586DB6D182BC7F95261B935E15CCE2F524C98216C3DFE1AFF66D80998DEF73F7B6BAFCB5BBFD6CD19CA096ECE62BDB
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - dc 1b 67 7e 6b 49 ec f9-e1 0a 8a 6e cb ac b4 e6   ..g~kI.....n....
    0010 - ac 8a 75 9f 7d a8 b1 f2-ad 7e a1 75 37 66 0a 9a   ..u.}....~.u7f..
    0020 - 9b 02 64 a2 a5 a0 43 5b-a6 a9 6f c4 06 d2 98 19   ..d...C[..o.....
    0030 - 5c 5a 98 f4 6a 4a b4 16-54 8b 35 a4 b6 c1 97 74   \Z..jJ..T.5....t
    0040 - c2 04 20 02 d5 50 6b 5f-6e ff a2 f8 76 7f 9d 29   .. ..Pk_n...v..)
    0050 - 72 16 cf 9f 27 a1 92 06-ec a8 fb 7a a8 14 73 77   r...'......z..sw
    0060 - 41 f4 54 e9 86 5a f7 a7-52 92 7a 10 dc 3d d3 ea   A.T..Z..R.z..=..
    0070 - 69 3e a8 1a fa e6 b4 7b-4e bd ee 0b b5 9b 7d 4f   i>.....{N.....}O
    0080 - 03 93 a7 87 29 43 86 50-ab 29 24 c4 ed bc d6 97   ....)C.P.)$.....
    0090 - 0d 02 ff f4 5b 30 9e 67-bb 64 c2 cf 1c ac 4b b7   ....[0.g.d....K.
    00a0 - d6 f2 10 5e dc 69 27 a3-ea 89 1f a3 b1 50 f8 ab   ...^.i'......P..
    00b0 - 91 b1 17 5b 5f 9e be e0-ec 58 82 f7 b8 79 a4 2e   ...[_....X...y..
    00c0 - 4c 79 a8 ca c2 64 f0 ce-e6 2f 19 38 35 e5 bf 4a   Ly...d.../.85..J

    Start Time: 1708370591
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$
```
# Notas 

# Referencias 
[Seguridad de la capa de transporte - Wikipedia, la enciclopedia libre](https://en.wikipedia.org/wiki/Transport_Layer_Security#SSL_1.0,_2.0,_and_3.0)
[OpenSSL - Wikipedia, la enciclopedia libre](https://es.wikipedia.org/wiki/OpenSSL)


