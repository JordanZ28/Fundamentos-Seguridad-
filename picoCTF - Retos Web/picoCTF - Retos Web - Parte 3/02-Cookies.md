
# Objetivo 
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:6418/](http://mercury.picoctf.net:6418/)


# Solución 
```
jordanz28@LAPTOP-UM00GHQE:~$ curl http://mercury.picoctf.net:6418/check "cookie: name=1"
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 3.2 Final//EN">
<title>Redirecting...</title>
<h1>Redirecting...</h1>
<p>You should be redirected automatically to target URL: <a href="/">/</a>.  If not click the link.curl: (3) URL using bad/illegal format or missing URL
jordanz28@LAPTOP-UM00GHQE:~$ curl -I http://mercury.picoctf.net:53554/ -H "Cookie:name=5"| greep"I love"
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
greepI love: command not found
jordanz28@LAPTOP-UM00GHQE:~$ for i in (0..20) do  curl -s  http://mercury.picoctf.net:53554/ -H "Cookie:name=5"| greep"I love"
-bash: syntax error near unexpected token `('
jordanz28@LAPTOP-UM00GHQE:~$ for i in (0..20) do  curl -s  http://mercury.picoctf.net:53554/ -H "Cookie:name=$i"| greep"I love"
-bash: syntax error near unexpected token `('
jordanz28@LAPTOP-UM00GHQE:~$ for i in (0..20) do  curl -s  http://mercury.picoctf.net:53554/ -H "Cookie:name=$i"; done | greep"I love"
-bash: syntax error near unexpected token `('
jordanz28@LAPTOP-UM00GHQE:~$ for i in 0..20 do  curl -s  http://mercury.picoctf.net:53554/ -H "Cookie:name=$i"; done | greep"I love"
-bash: syntax error near unexpected token `done'
jordanz28@LAPTOP-UM00GHQE:~$ for i in 0..20; do  curl -s  http://mercury.picoctf.net:53554/ -H "Cookie:name=$i"; done | greep"I love"
greepI love: command not found
jordanz28@LAPTOP-UM00GHQE:~$ for i in 0..20; do  curl -s  http://mercury.picoctf.net:53554/ -H "Cookie:name=$i"; done | grep"I love"
grepI love: command not found
jordanz28@LAPTOP-UM00GHQE:~$ for i in 0..20; do  curl -s  http://mercury.picoctf.net:53554/ -H "Cookie:name=$i"; done | grep "I love"
jordanz28@LAPTOP-UM00GHQE:~$ curl -s http://mercury.picoctf.net:6418/check -H "Cookie: name=18" | grep "pico"
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_88acab36}</code></p>
jordanz28@LAPTOP-UM00GHQE:~$
```

# Notas 
Utilizando un ciclo for para poder obtener la bandera  utilizando el comando  for i in 0..20; do  curl -s  http://mercury.picoctf.net:53554/ -H "Cookie:name=$i"; done | grep "I love"

