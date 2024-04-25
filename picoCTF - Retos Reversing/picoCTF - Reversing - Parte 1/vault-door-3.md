
# Objetivo 
This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/a4018cec1446761cb2e8cce05db925fa/VaultDoor3.java)

# Solución 
```
allow pasting  

Uncaught SyntaxError: unexpected token: identifier

debugger eval code:1:6  

var password = 'jU5t_a_sna_3lom12g94c_u_4_mm7ra41';  

undefined  

var buffer = Array (32);  

undefined  

for (i=0; i<8; i++) { buffer[i] = password.charAt(i); } for (; i<16; i++) { buffer[i] = password.charAt(23-i);…  

"g"  

buffer.join ('')

"jU5t_a_s1mpl3_an4gr4m_4_u_c79a21"
```

# Notas 

