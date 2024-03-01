
# Objetivo 

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/15/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/15/level2.flag.txt.enc) in the same directory too.
# Solución
```
jordanza-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/15/level2.py
--2024-03-01 18:09:37--  https://artifacts.picoctf.net/c/15/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.128, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py                                                  100%[======================================================================================================================================>]     914  --.-KB/s    in 0s      

2024-03-01 18:09:37 (48.3 MB/s) - 'level2.py' saved [914/914]

jordanza-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/15/level2.flag.txt.enc
--2024-03-01 18:09:58--  https://artifacts.picoctf.net/c/15/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.128, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc                                        100%[======================================================================================================================================>]      31  --.-KB/s    in 0s      

2024-03-01 18:09:58 (14.2 MB/s) - 'level2.flag.txt.enc' saved [31/31]

jordanza-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  Addadshashanammu.zip.1  README.txt  code.py  codebook.txt  convertme.py  file  fixme1.py  fixme2.py  flag  level1.flag.txt.enc  level1.py  level2.flag.txt.enc  level2.py  static  strings  warm
jordanza-picoctf@webshell:~$ ls -la
total 892
drwxr-xr-x 5 jordanza-picoctf jordanza-picoctf   4096 Mar  1 18:09 .
drwxr-xr-x 3 root             root                 30 Feb 26 18:19 ..
-rw------- 1 jordanza-picoctf jordanza-picoctf   1620 Mar  1 04:58 .bash_history
-rw-r--r-- 1 jordanza-picoctf jordanza-picoctf    220 Feb 26 18:19 .bash_logout
-rw-r--r-- 1 jordanza-picoctf jordanza-picoctf   3771 Feb 26 18:19 .bashrc
-rw------- 1 jordanza-picoctf jordanza-picoctf     20 Mar  1 04:58 .lesshst
drwxrwxr-x 3 jordanza-picoctf jordanza-picoctf     19 Mar  1 05:30 .local
-rw-r--r-- 1 jordanza-picoctf jordanza-picoctf    807 Feb 26 18:19 .profile
drwx------ 2 jordanza-picoctf jordanza-picoctf     48 Feb 26 19:17 .ssh
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf    167 Mar  1 05:41 .wget-hsts
drwxr-xr-x 3 jordanza-picoctf jordanza-picoctf     28 Mar 16  2021 Addadshashanammu
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf   4520 Mar 16  2021 Addadshashanammu.zip
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf   4520 Mar 16  2021 Addadshashanammu.zip.1
-rw-r--r-- 1 root             root               4443 Mar  1 17:47 README.txt
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf   1278 Mar 16  2023 code.py
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf     27 Mar 16  2023 codebook.txt
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf   1189 Mar 16  2023 convertme.py
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf  14551 Oct 26  2020 file
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf    835 Mar  1 05:32 fixme1.py
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf   1030 Mar  1 17:52 fixme2.py
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf     34 Mar 16  2021 flag
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf     30 Mar 16  2023 level1.flag.txt.enc
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf    876 Mar 16  2023 level1.py
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf     31 Mar 16  2023 level2.flag.txt.enc
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf    914 Mar 16  2023 level2.py
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf   8376 Mar 16  2021 static
-rw-rw-r-- 1 jordanza-picoctf jordanza-picoctf 776032 Oct 26  2020 strings
-rwxrwxr-x 1 jordanza-picoctf jordanza-picoctf  10936 Mar 16  2021 warm
jordanza-picoctf@webshell:~$ 
jordanza-picoctf@webshell:~$ 
jordanza-picoctf@webshell:~$ nano level2.py
jordanza-picoctf@webshell:~$ nano level2.flag.txt.enc 
jordanza-picoctf@webshell:~$ 
jordanza-picoctf@webshell:~$ python level2.py
Please enter correct password for flag: 39ce
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_502ec42e}
jordanza-picoctf@webshell:~$ 
```

# Notas 
 chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65)  convertir esto a ascii para poder obtener la contraseña para poder obtener la bandera 
 
 0x33 + 0x39 + 0x63 + 0x65 = 39ce  