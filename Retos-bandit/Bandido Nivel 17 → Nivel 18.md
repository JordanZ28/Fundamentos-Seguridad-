# Retos Bandit 
# Bandido Nivel 17 → Nivel 18

# Objetivo 
Hay 2 archivos en el directorio de inicio: **passwords.old y passwords.new**. La contraseña para el siguiente nivel se encuentra en passwords.new y es la única línea que se ha cambiado entre **passwords.old y passwords.new**

**NOTA: si has resuelto este nivel y ves '¡Byebye!' al intentarlo Para iniciar sesión en Bandit18, esto está relacionado con el siguiente nivel, Bandit19**

# Datos de acceso al nivel 
bandit17
ssh -l bandit17 bandit.labs.overthewire.org -p 2220
# Solución 
```
jordanz28@LAPTOP-UM00GHQE:~$ nano lallave
jordanz28@LAPTOP-UM00GHQE:~$ ls -la lallave
-rw-r--r-- 1 jordanz28 jordanz28 1676 Feb 21 12:24 lallave
jordanz28@LAPTOP-UM00GHQE:~$ chmod 600 lallave
jordanz28@LAPTOP-UM00GHQE:~$ notepad lallave
notepad: command not found
jordanz28@LAPTOP-UM00GHQE:~$ ls - la lallave
ls: cannot access '-': No such file or directory
ls: cannot access 'la': No such file or directory
lallave
jordanz28@LAPTOP-UM00GHQE:~$ ls -la lallave
-rw------- 1 jordanz28 jordanz28 1676 Feb 21 12:24 lallave
jordanz28@LAPTOP-UM00GHQE:~$ ssh -i lallave  bandit17@bandit.labs.overthewire.org -p 2220
The authenticity of host '[bandit.labs.overthewire.org]:2220 ([51.20.13.48]:2220)' can't be established.
ECDSA key fingerprint is SHA256:IJ7FrX0mKSSHTJ63ezxjqtnOE0Hg116Aq+v5mN0+HdE.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[bandit.labs.overthewire.org]:2220,[51.20.13.48]:2220' (ECDSA) to the list of known hosts.
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames


      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * peda (https://github.com/longld/peda.git) in /opt/peda/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit17@bandit:~$


bandit17@bandit:~$ ls -la
total 36
drwxr-xr-x  3 root     root     4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root     4096 Oct  5 06:20 ..
-rw-r-----  1 bandit17 bandit17   33 Oct  5 06:19 .bandit16.password
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r-----  1 bandit18 bandit17 3300 Oct  5 06:19 passwords.new
-rw-r-----  1 bandit18 bandit17 3300 Oct  5 06:19 passwords.old
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
drwxr-xr-x  2 root     root     4096 Oct  5 06:19 .ssh
bandit17@bandit:~$ wc -passwords.old
wc: invalid option -- 'p'
Try 'wc --help' for more information.
bandit17@bandit:~$ wc -l passwords.old
100 passwords.old
bandit17@bandit:~$ wc -l passwords.new
100 passwords.new
bandit17@bandit:~$ head passwords.old
fMOYjvUY5uCDCbweKVmOqsxGmiqCug2W
i9zj4BOYY9OATSdwqBnAAsPTyoOpdlVW
4ipWQKzhSdNXLNkn3ytQAXapg0sm21xj
vCSTATER0iHC3AcfoaaugfYPpe2KbxlY
zeRdb0bCAurzvgkBbrdn1Vd2k7EzEquQ
63a4svAasv5xD1SsKq7UejZkFMwQ8TrC
ESR2tsFvQVuPdheIrV1cQHRzWPqjEspR
hIZ7ehVTkQ0iU8z3HIQaUBH9at9yRvpP
ub3exqqKUBxwGYvP93GkoZdNgYMCg2ax
25LhvrMLb4x4qFsl7CDsTi2bxI5OImIr
bandit17@bandit:~$ head passwords.new
fMOYjvUY5uCDCbweKVmOqsxGmiqCug2W
i9zj4BOYY9OATSdwqBnAAsPTyoOpdlVW
4ipWQKzhSdNXLNkn3ytQAXapg0sm21xj
vCSTATER0iHC3AcfoaaugfYPpe2KbxlY
zeRdb0bCAurzvgkBbrdn1Vd2k7EzEquQ
63a4svAasv5xD1SsKq7UejZkFMwQ8TrC
ESR2tsFvQVuPdheIrV1cQHRzWPqjEspR
hIZ7ehVTkQ0iU8z3HIQaUBH9at9yRvpP
ub3exqqKUBxwGYvP93GkoZdNgYMCg2ax
25LhvrMLb4x4qFsl7CDsTi2bxI5OImIr
bandit17@bandit:~$ diff passwords.old
diff: missing operand after 'passwords.old'
diff: Try 'diff --help' for more information.
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< p6ggwdNHncnmCNxuAt0KtKVq185ZU7AW
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
bandit17@bandit:~$ diff passwords.old passwords.new --color
42c42
< p6ggwdNHncnmCNxuAt0KtKVq185ZU7AW
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
bandit17@bandit:~$

```

# Notas 

Se creo un txt con la contraseña esta contraseña se guardo con el nombre de llave para poder hacer publico el txt se utilizo el comando  chmod 600