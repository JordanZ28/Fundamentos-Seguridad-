
# Objetivo 
Morse code is well known. Can you decrypt this? Download the file [here](https://artifacts.picoctf.net/c/79/morse_chal.wav). Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.
# Solución 
```
┌──(jordan㉿kali)-[~/Pico/Examen3/R2]
└─$ ls    
morse_chal.wav
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Examen3/R2]
└─$ 
┌──(jordan㉿kali)-[~/Pico/Examen3/R2]
└─$ python3
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> "WH47 H47H 90D W20U9H7".lower()
'wh47 h47h 90d w20u9h7'
>>> "WH47 H47H 90D W20U9H7".lower().replace(' ', '_')
'wh47_h47h_90d_w20u9h7'
>>> "picoCTF{WH47 H47H 90D W20U9H7}".lower().replace(' ', '_')
'picoctf{wh47_h47h_90d_w20u9h7}'
>>> 
KeyboardInterrupt
>>> 



```

# Notas 

