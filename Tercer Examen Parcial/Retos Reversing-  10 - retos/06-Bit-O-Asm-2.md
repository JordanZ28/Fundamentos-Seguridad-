
# Objetivo 

Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).
# Solución 
```
                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R16]
└─$ wget https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
--2024-05-16 21:16:42--  https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.238.4.55, 18.238.4.32, 18.238.4.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.238.4.55|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: ‘disassembler-dump0_b.txt’

disassembler-dump0_b.txt        100%[=====================================================>]     270  --.-KB/s    in 0s      

2024-05-16 21:16:42 (1.15 MB/s) - ‘disassembler-dump0_b.txt’ saved [270/270]

                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R16]
└─$ cat disassembler-dump0_b.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R16]
└─$ python3 
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> ascii(0x9fe1a)
'654874'
>>> 
picoCTF{654874}
```

# Notas 

