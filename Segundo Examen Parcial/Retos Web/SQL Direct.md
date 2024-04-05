
# Objetivo 

Connect to this PostgreSQL server and find the flag!
Additional details will be available after launching your challenge instance.
# Solución 
```
en este reto nos conectaremos al siguiente 

Connect to this PostgreSQL server and find the flag!`psql -h saturn.picoctf.net -p 63464 -U postgres pico`Password is `postgres`

donde utilizaremos nuestra terminal de linux 
utilizamos los comandos \dt que nos muestran una tabla y una sentencia para mostra la bandera que sera 
select *from public.flags; 

```
# Notas 

