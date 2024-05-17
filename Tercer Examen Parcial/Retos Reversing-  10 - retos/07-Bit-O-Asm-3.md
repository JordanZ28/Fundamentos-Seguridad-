
# Objetivo 
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).

# Solución 
```
                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R17]
└─$ wget https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt
--2024-05-16 21:22:52--  https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.238.4.64, 18.238.4.16, 18.238.4.55, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.238.4.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 461 [application/octet-stream]
Saving to: ‘disassembler-dump0_c.txt’

disassembler-dump0_c.txt        100%[=====================================================>]     461  --.-KB/s    in 0s      

2024-05-16 21:22:52 (30.0 MB/s) - ‘disassembler-dump0_c.txt’ saved [461/461]

                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R17]
└─$ cat disassembler-dump0_c.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret
                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R17]
└─$ python3 
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> exa=0x9fe1a
>>> hex(0x9fe1a*0x4)
'0x27f868'
>>> hex(0x27f868+0x1f5)
'0x27fa5d'
>>> ascii(0x27fa5d)
'2619997'
>>> 
                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R17]
└─$ 

picoCTF{2619997}

```
# Notas 

