
# Objetivo 

This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program. You can download the file from [here](https://artifacts.picoctf.net/c/506/asciiftw).
# Solución 
```
┌──(jordan㉿kali)-[~/Pico/Examen3/R14]
└─$ wget https://artifacts.picoctf.net/c/506/asciiftw                                         
--2024-05-16 21:03:28--  https://artifacts.picoctf.net/c/506/asciiftw
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.238.4.64, 18.238.4.16, 18.238.4.55, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.238.4.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16752 (16K) [application/octet-stream]
Saving to: ‘asciiftw’

asciiftw                        100%[====================================================>]  16.36K  --.-KB/s    in 0s      

2024-05-16 21:03:29 (57.1 MB/s) - ‘asciiftw’ saved [16752/16752]

                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Examen3/R14]
└─$ cat asciiftw           
@@@@�▒▒▒XX��   pp�-�=�=`h�-�=�=�888 XXXDDS�td888 P�td      DDQ�tdR�td�-�=�=PP/lib64/ld-linux-x86-64.so.2GNU�GNU�x.�:��sMw���[`�F�GNU��e�mZ 
              2v � #"libc.so.6__stack_chk_failprintf__cxa_finalize__libc_start_mainGLIBC_2.2.5GLIBC_2.4_ITM_deregisterTMClone�H�=��2/��H�=Y/H�R/H9�tH�/H��t�������H�=)/H�5"/H)�H��H��?H��H�H��tH��.H����fD�����=�.u+UH�=�.H��t��H���PTL�H�
                                                                                                 H�=�.� ����d�����.]������w�����UH��H��0dH�%(H�E�1��E�p�E�i�E�c�E�o�E�C�E�T�E�F�E�{�E�A�E�S�E�C�E�I�E�I�E�_�E�I�E�S�E�_�E�E�E�A�E�S�E�Y�E�_�E�3�E�C�E�F�E���V����H�E�dH3%(t�1�����f.�D��AWL�=c+AVI��AUI��ATA��UH�-T+SL)�H������H��t1��L��L��D��A��H��H9�u�H�[]A\A]A^A_�ff.������H�H��The flag starts with %x
D���x0����@����`���`I���� ��������8zRx
                                     ����/D$4����0F▒J
�                                                    �?▒:*3$"\����t���� �q����E�C
D�(���eF�I▒�E �E(�D0�H8�G@n8A0A(B B▒B�P���` 
��▒����o���
�
 ▒�?0(� ������o8���o���o(���o�=0@GCC: (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0▒8X|��(      8
h
 (
 P`��   h �=�=�=▒�?@▒@�
                       ��! 7▒@F�=m`y�=������l!����=��=��=�  �▒�?�
                                                                 � � @3@�:Vj�@� @� �@e�▒▒@��/�▒@�i��@�"crtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.8061__do_global_dtors_aux_fini_array_entryframe_dummy__frame_dummy_init_array_entryasciiftw.c__FRAME_END____init_array_end_DYNAMIC__init_array_start__GNU_EH_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_csu_fini_ITM_deregisterTMCloneTable_edata__stack_chk_fail@@GLIBC_2.4printf@@GLIBC_2.2.5__libc_start_main@@GLIBC_2.2.5__data_start__gmon_start____dso_handle_IO_stdin_used__libc_csu_init__bss_startmain__TMC_END___ITM_registerTMCloneTable__cxa_finalize@@GLIBC_2.2.5.symtab.strtab.shstrtab.interp.note.gnu.property.note.gnu.build-id.note.ABI-tag.gnu.hash.dynsym.dynstr.gnu.version.gnu.version_r.rela.dyn.rela.plt.init.plt.got.plt.sec.text.fini.rodata.eh_frame_hdr.eh_frame.init_array.fini_array.dynamic.data.bss.comment▒▒#886XX$I|| W���o��a
�  �    D�h ������=�-��?�@0���o((~���o88�hh▒�B((0▒�  0�PP�`` ���5���
                         @00+@00▒       p6$�8▒                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Examen3/R14]
└─$ chmod +x asciiftw 
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Examen3/R14]
└─$ gdb -q asciiftw
Reading symbols from asciiftw...
(No debugging symbols found in asciiftw)
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000001169 <+0>:     endbr64
   0x000000000000116d <+4>:     push   %rbp
   0x000000000000116e <+5>:     mov    %rsp,%rbp
   0x0000000000001171 <+8>:     sub    $0x30,%rsp
   0x0000000000001175 <+12>:    mov    %fs:0x28,%rax
   0x000000000000117e <+21>:    mov    %rax,-0x8(%rbp)
   0x0000000000001182 <+25>:    xor    %eax,%eax
   0x0000000000001184 <+27>:    movb   $0x70,-0x30(%rbp)
   0x0000000000001188 <+31>:    movb   $0x69,-0x2f(%rbp)
   0x000000000000118c <+35>:    movb   $0x63,-0x2e(%rbp)
   0x0000000000001190 <+39>:    movb   $0x6f,-0x2d(%rbp)
   0x0000000000001194 <+43>:    movb   $0x43,-0x2c(%rbp)
   0x0000000000001198 <+47>:    movb   $0x54,-0x2b(%rbp)
   0x000000000000119c <+51>:    movb   $0x46,-0x2a(%rbp)
   0x00000000000011a0 <+55>:    movb   $0x7b,-0x29(%rbp)
   0x00000000000011a4 <+59>:    movb   $0x41,-0x28(%rbp)
   0x00000000000011a8 <+63>:    movb   $0x53,-0x27(%rbp)
   0x00000000000011ac <+67>:    movb   $0x43,-0x26(%rbp)
   0x00000000000011b0 <+71>:    movb   $0x49,-0x25(%rbp)
   0x00000000000011b4 <+75>:    movb   $0x49,-0x24(%rbp)
   0x00000000000011b8 <+79>:    movb   $0x5f,-0x23(%rbp)
   0x00000000000011bc <+83>:    movb   $0x49,-0x22(%rbp)
--Type <RET> for more, q to quit, c to continue without paging--
   0x00000000000011c0 <+87>:    movb   $0x53,-0x21(%rbp)                                                                      
   0x00000000000011c4 <+91>:    movb   $0x5f,-0x20(%rbp)                                                                      
   0x00000000000011c8 <+95>:    movb   $0x45,-0x1f(%rbp)                                                                      
   0x00000000000011cc <+99>:    movb   $0x41,-0x1e(%rbp)                                                                      
   0x00000000000011d0 <+103>:   movb   $0x53,-0x1d(%rbp)                                                                      
   0x00000000000011d4 <+107>:   movb   $0x59,-0x1c(%rbp)                                                                      
   0x00000000000011d8 <+111>:   movb   $0x5f,-0x1b(%rbp)                                                                      
   0x00000000000011dc <+115>:   movb   $0x33,-0x1a(%rbp)                                                                      
   0x00000000000011e0 <+119>:   movb   $0x43,-0x19(%rbp)                                                                      
   0x00000000000011e4 <+123>:   movb   $0x46,-0x18(%rbp)                                                                      
   0x00000000000011e8 <+127>:   movb   $0x34,-0x17(%rbp)                                                                      
   0x00000000000011ec <+131>:   movb   $0x42,-0x16(%rbp)                                                                      
   0x00000000000011f0 <+135>:   movb   $0x46,-0x15(%rbp)
   0x00000000000011f4 <+139>:   movb   $0x41,-0x14(%rbp)
   0x00000000000011f8 <+143>:   movb   $0x44,-0x13(%rbp)
   0x00000000000011fc <+147>:   movb   $0x7d,-0x12(%rbp)
   0x0000000000001200 <+151>:   movzbl -0x30(%rbp),%eax
   0x0000000000001204 <+155>:   movsbl %al,%eax
   0x0000000000001207 <+158>:   mov    %eax,%esi
   0x0000000000001209 <+160>:   lea    0xdf4(%rip),%rdi        # 0x2004
   0x0000000000001210 <+167>:   mov    $0x0,%eax
   0x0000000000001215 <+172>:   call   0x1070 <printf@plt>
   0x000000000000121a <+177>:   nop
   0x000000000000121b <+178>:   mov    -0x8(%rbp),%rax
   0x000000000000121f <+182>:   xor    %fs:0x28,%rax
   0x0000000000001228 <+191>:   je     0x122f <main+198>
   0x000000000000122a <+193>:   call   0x1060 <__stack_chk_fail@plt>
   0x000000000000122f <+198>:   leave
   0x0000000000001230 <+199>:   ret
End of assembler dump.
(gdb) 


picoCTF{ASCII_IS_EASY_3CF4BFAD}
```
# Notas 

