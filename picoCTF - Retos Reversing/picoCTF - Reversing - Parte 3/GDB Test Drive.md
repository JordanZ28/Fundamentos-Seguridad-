
# Objetivo 

Can you get the flag? Download this [binary](https://artifacts.picoctf.net/c/86/gdbme). Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`
# Solución 
```
┌──(jordan㉿kali)-[~/Pico/Revers/Parte3/R1]
└─$ gdb gdbme           
GNU gdb (Debian 13.2-1) 13.2
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm 
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte3/R1]
└─$ chmod +x gdbme 
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte3/R1]
└─$ gdb gdbme            
GNU gdb (Debian 13.2-1) 13.2
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm 
                              

multi-thre No process In: (gdb) break *(main+99) Breakpoint 1 at 0x132a (gdb) run
Starting program: /home/jordan/Pico/Revers/Parte3/R1/gdbme [Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
Breakpoint 1, 0x000055555555532a in main () (gdb) jump *(main+104) tegorized Continuing at 0x55555555532f. picoCTF{d3bugg3r_dr1v3_72bd8355}
(gdb) sSsSss(process 10219) exited normally] Original Event
gdb) brea (main+1


```

# Notas 
La bandera es picoCTF{d3bugg3r_dr1v3_72bd8355}
