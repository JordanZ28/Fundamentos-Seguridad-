
# Objetivo 
This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/28921/` ([link](https://jupiter.challenges.picoctf.org/problem/28921/)) or http://jupiter.challenges.picoctf.org:28921

# Solución 
abrir el inspector ver la bandera y edintificar el user 

```
jordanz28@LAPTOP-UM00GHQE:~$ curl https://jupiter.challenges.picoctf.org/problem/28921/flag -H "User-Agent:picobrowser" | grep pico
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  2115  100  2115    0     0   2816      0 --:--:-- --:--:-- --:--:--  2812
         <!-- <strong>Title</strong> --> picobrowser!
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}</code></p>
jordanz28@LAPTOP-UM00GHQE:~$

Notas 

```
# Notas 
