# Retos Bandit 
# Bandido Nivel 22 → Nivel 23

# Objetivo 
Un programa se ejecuta automáticamente a intervalos regulares desde **cron**, el programador de trabajos basado en el tiempo. Busque en **/etc/cron.d/** la configuración y ver qué comando se está ejecutando.

**NOTA:** Mirar los scripts de shell escritos por otras personas es una Habilidad muy útil. El guión para este nivel se ha creado intencionadamente Fácil de leer. Si tiene problemas para entender lo que hace, Intente ejecutarlo para ver la información de depuración que imprime.

# Datos de acceso al nivel 
bandit22
ssh -l bandit22 bandit.labs.overthewire.org -p 2220
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
# Solución 

```
bandit22@bandit:~$  ls /etc/cron.d -la
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
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ whoamin
Command 'whoamin' not found, did you mean:
  command 'whoami' from deb coreutils (8.32-4.1ubuntu1)
Try: apt install <deb name>
bandit22@bandit:~$ whoami
bandit22
bandit22@bandit:~$ myname=$(whomai)
Command 'whomai' not found, did you mean:
  command 'whoami' from deb coreutils (8.32-4.1ubuntu1)
Try: apt install <deb name>
bandit22@bandit:~$ myname=$(whoi)
Command 'whoi' not found, did you mean:
  command 'whois' from deb whois (5.5.13)
  command 'whom' from deb mailutils-mh (1:3.14-1)
  command 'whom' from deb mmh (0.4-4)
  command 'whom' from deb nmh (1.7.1-11)
  command 'who' from deb coreutils (8.32-4.1ubuntu1)
  command 'whob' from deb lft (3.91-1)
Try: apt install <deb name>
bandit22@bandit:~$ myname=$(whoami)
bandit22@bandit:~$ echo $myname
bandit22
bandit22@bandit:~$ echo i am user $myname
i am user bandit22
bandit22@bandit:~$ echo i am user $myname | md5sum
954338263902d18f7e5d0a954ef0ce18  -
bandit22@bandit:~$ echo I am user $myname | md5sum | cut -d ' ' -f 1
8169b67bd894ddbb4412f91573b38db3
bandit22@bandit:~$ myname=bandit23
bandit22@bandit:~$ echo I am user $myname | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
bandit22@bandit:~$
```

# Notas 

