
# Objetivo 

I wonder what this really is... [enc](https://mercury.picoctf.net/static/dd6004f51362ff76f98cb8c699510f23/enc) `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`
# Solución 

```
┌──(jordan㉿kali)-[~/Pico/Examen3/R11]
└─$ ls 
enc
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Examen3/R11]
└─$ cat enc          
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸弰摤捤㤷慽                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Examen3/R11]
└─$ python3       
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> enc=open("enc").read()
>>> print(enc)
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸弰摤捤㤷慽
>>> print(hex(ord(enc[0])))
0x7069
>>> for c in enc:
... print(hex(ord(c)).lstrip("0x"),end='')
  File "<stdin>", line 2
    print(hex(ord(c)).lstrip("0x"),end='')
    ^
IndentationError: expected an indented block after 'for' statement on line 1
>>> print(hex(ord(c)).lstrip("0x"),end='')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'c' is not defined
>>> for c in enc:
...     print(hex(ord(c)).lstrip("0x"),end='')
... 
7069636f4354467b31365f62697
```
# Notas 
picoCTF{16_bits_inst34d_of_8_0ddcd97a}

