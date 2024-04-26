
# Objetivo 
¿Qué devuelve asm1(0x8be)? Envíe la marca como un valor hexadecimal (que comience con '0x'). NOTA: Su envío para esta pregunta NO estará en el formato de bandera normal. [Fuente](https://jupiter.challenges.picoctf.org/static/66c927e32f3d7be7a62d13a7c2250943/test.S) 

# Solución 
```
[      ] < esp
[      ] < ebp - 0xc
[ 0xb  ] < ebp - 0x8
[ 0x2f ] < ebp - 0x4
[ ebp  ] < ebp 
[ ret  ] < ebp + 0x4
[ 0xb  ] < ebp + 0x8
[ 0x2e ] < ebp + 0xc

registers 
[ 0xb  ]
asm2: (0xb,0x2e)    
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   sub    esp,0x10
        <+6>:   mov    eax,DWORD PTR [ebp+0xc]
        <+9>:   mov    DWORD PTR [ebp-0x4],eax
        <+12>:  mov    eax,DWORD PTR [ebp+0x8]
        <+15>:  mov    DWORD PTR [ebp-0x8],eax
        <+18>:  jmp    0x509 <asm2+28>
        <+20>:  add    DWORD PTR [ebp-0x4],0x1
        <+24>:  sub    DWORD PTR [ebp-0x8],0xffffff80
        <+28>:  cmp    DWORD PTR [ebp-0x8],0x63f3
        <+35>:  jle    0x501 <asm2+20>
        <+37>:  mov    eax,DWORD PTR [ebp-0x4]
        <+40>:  leave  
        <+41>:  ret    


```

# Notas 

