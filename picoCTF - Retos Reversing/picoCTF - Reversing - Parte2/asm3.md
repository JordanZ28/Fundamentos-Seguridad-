
# Objetivo 
What does asm3(0xba6c5a02,0xd101e3dd,0xbb86a173) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/cb753ae52bca4aa303deca5fbfb01bfb/test.S)

# Solución 
```
┌──(jordan㉿kali)-[~/Pico/Revers/Parte2/Asm3]
└─$ cat test.S 
asm3:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   xor    eax,eax
        <+5>:   mov    ah,BYTE PTR [ebp+0xb]
        <+8>:   shl    ax,0x10
        <+12>:  sub    al,BYTE PTR [ebp+0xd]
        <+15>:  add    ah,BYTE PTR [ebp+0xc]
        <+18>:  xor    ax,WORD PTR [ebp+0x12]
        <+22>:  nop
        <+23>:  pop    ebp
        <+24>:  ret    

se abre un emulador 
start: 
		push 0xbb86a173
		push 0xd101e3dd
		push 0xba6c5a02
        call asm3
asm3:
           push   ebp
           mov    ebp,esp
           xor    eax,eax
           mov    ah,BYTE PTR [ebp+0xb]
           shl    ax,0x10
           sub    al,BYTE PTR [ebp+0xd]
           add    ah,BYTE PTR [ebp+0xc]
           xor    ax,WORD PTR [ebp+0x12]
           nop
           pop    ebp
           ret   
       se ejecuta paso a paso y la bandera es 
       0x669B
       

```

# Notas 
https://carlosrafaelgn.com.br/Asm86/
