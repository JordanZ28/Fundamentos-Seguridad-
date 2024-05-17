
# Objetivo 
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Debug [this](https://artifacts.picoctf.net/c/520/debugger0_b).

# Solución 
```

                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R20]
└─$ wget https://artifacts.picoctf.net/c/520/debugger0_b
--2024-05-16 21:42:13--  https://artifacts.picoctf.net/c/520/debugger0_b
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.238.4.64, 18.238.4.55, 18.238.4.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.238.4.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16304 (16K) [application/octet-stream]
Saving to: ‘debugger0_b’

debugger0_b                     100%[=====================================================>]  15.92K  --.-KB/s    in 0s      

2024-05-16 21:42:14 (57.4 MB/s) - ‘debugger0_b’ saved [16304/16304]

                                                                                                
                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R20]
└─$ cat debugger0_b
@@@@@�▒▒@▒@@@��@@��  @ @��P.P>@P>@��`.`>@`>@�88@8@ XX@X@DDS�td88@8@ P�td  @ @44Q�tdR�tdP.P>@P>@��/lib64/ld-linux-x86-64.so.2GNU�GNU�� ;��.u���[       ����GNU
                               ) libc.so.6__libc_start_mainGLIBC_2.2.5__gmon_start__u▒i �?@�?@��H�H��/H��t��H����1�I��^H��H���PTI���@H��P@H��@��/�����f.���(@@H=(@@t�H��t     �(@@��f��ff.�@�(@@H��(@@H��H��?H��H�H��t�H��t�(@@���ff.�@���=M/uUH���z����;/]Ð�ff.�@������UH���}�H�u��E����E�_�E��
�E�E��E��E�;E�|��E�]�f.���AWL�=�,AVI��AUI��ATA��UH�-�,SL)�H�����H��t1��L��L��D��A��H��H9�u�H�[]A\A]A^A_�ff.������H�H��0���LL���`���tL���������zRx
t                 ����/D0����D����=E�C
Dd����eF�I▒�E �E(�D0�H8�G@n8A0A(B B▒B�����@�@
�@P>▒X>���o�@�@                              @
8
 ▒h0    ▒���oH@���o���o@@`>@GCC: (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0▒@8@X@|@�@�@@     H@
h@
  @
�@ @ @8 @P>@X>@`>@�?@@@▒@@(@@▒��

                                `@
                                  �@!
                                     �@7(@@FX>@m
                                                @yP>@������� @���X>@�`>@�P>@� @�@@

�@!@▒@@M \ @@i @x
                 P@e�0@@�
                         P@F
                             @/�(@@�
                                    @=�(@@�
                                           @crtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.8061__do_global_dtors_aux_fini_array_entryframe_dummy__frame_dummy_init_array_entrydebugger0_b.c__FRAME_END____init_array_end_DYNAMIC__init_array_start__GNU_EH_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_csu_fini_edata__libc_start_main@@GLIBC_2.2.5__data_start__gmon_start____dso_handle_IO_stdin_used__libc_csu_init_dl_relocate_static_pie__bss_startmain__TMC_END__.symtab.strtab.shstrtab.interp.note.gnu.property.note.gnu.build-id.note.ABI-tag.gnu.hash.dynsym.dynstr.gnu.version.gnu.version_r.rela.dyn.init.text.fini.rodata.eh_frame_hdr.eh_frame.init_array.fini_array.dynamic.got.got.plt.data.bss.comment▒@▒#8@86X@X$I|@| W���o�@a
                                                                                                 �@�▒8q���o@@@~���oH@H�h@h▒�@ � @ � @ 4�8 @8 �P>�X>�`>@`.��?@�@@�▒@@▒(@@(0(0+X0�▒▒    �5��7
                                                                                                                                                                                           
┌──(jordan㉿kali)-[~/Pico/Examen3/R20]
└─$ chmod +x debugger0_b                           
                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R20]
└─$ gdb -q debugger0_b                                
Reading symbols from debugger0_b...
(No debugging symbols found in debugger0_b)
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   %rbp
   0x000000000040110b <+5>:     mov    %rsp,%rbp
   0x000000000040110e <+8>:     mov    %edi,-0x14(%rbp)
   0x0000000000401111 <+11>:    mov    %rsi,-0x20(%rbp)
   0x0000000000401115 <+15>:    movl   $0x1e0da,-0x4(%rbp)
   0x000000000040111c <+22>:    movl   $0x25f,-0xc(%rbp)
   0x0000000000401123 <+29>:    movl   $0x0,-0x8(%rbp)
   0x000000000040112a <+36>:    jmp    0x401136 <main+48>
   0x000000000040112c <+38>:    mov    -0x8(%rbp),%eax
   0x000000000040112f <+41>:    add    %eax,-0x4(%rbp)
   0x0000000000401132 <+44>:    addl   $0x1,-0x8(%rbp)
   0x0000000000401136 <+48>:    mov    -0x8(%rbp),%eax
   0x0000000000401139 <+51>:    cmp    -0xc(%rbp),%eax
   0x000000000040113c <+54>:    jl     0x40112c <main+38>
   0x000000000040113e <+56>:    mov    -0x4(%rbp),%eax
   0x0000000000401141 <+59>:    pop    %rbp
   0x0000000000401142 <+60>:    ret
End of assembler dump.
(gdb) quit
                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R20]
└─$ gdb -q debugger0_b
Reading symbols from debugger0_b...
(No debugging symbols found in debugger0_b)
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   %rbp
   0x000000000040110b <+5>:     mov    %rsp,%rbp
   0x000000000040110e <+8>:     mov    %edi,-0x14(%rbp)
   0x0000000000401111 <+11>:    mov    %rsi,-0x20(%rbp)
   0x0000000000401115 <+15>:    movl   $0x1e0da,-0x4(%rbp)
   0x000000000040111c <+22>:    movl   $0x25f,-0xc(%rbp)
   0x0000000000401123 <+29>:    movl   $0x0,-0x8(%rbp)
   0x000000000040112a <+36>:    jmp    0x401136 <main+48>
   0x000000000040112c <+38>:    mov    -0x8(%rbp),%eax
   0x000000000040112f <+41>:    add    %eax,-0x4(%rbp)
   0x0000000000401132 <+44>:    addl   $0x1,-0x8(%rbp)
   0x0000000000401136 <+48>:    mov    -0x8(%rbp),%eax
   0x0000000000401139 <+51>:    cmp    -0xc(%rbp),%eax
   0x000000000040113c <+54>:    jl     0x40112c <main+38>
   0x000000000040113e <+56>:    mov    -0x4(%rbp),%eax
   0x0000000000401141 <+59>:    pop    %rbp
   0x0000000000401142 <+60>:    ret
End of assembler dump.
(gdb) break main 
Breakpoint 1 at 0x40110e
(gdb) run 
Starting program: /home/jordan/Pico/Examen3/R20/debugger0_b 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000000000040110e in main ()
(gdb) break *0x401142
Breakpoint 2 at 0x401142
(gdb) c
Continuing.

Breakpoint 2, 0x0000000000401142 in main ()
(gdb) print/d $eax
$1 = 307019
(gdb) quit 
A debugging session is active.

        Inferior 1 [process 48273] will be killed.

Quit anyway? (y or n) y
                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R20]
└─$ 

```
# Notas 
picoCTF{307019}

