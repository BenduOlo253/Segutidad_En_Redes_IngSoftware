# Descripción
This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag).

# Solución 
```
┌──(BenduOlo253㉿LaBenduPC)-[/mnt/c/Users/jmanu/Downloads]
└─$ wget https://mercury.picoctf.net/static/0e428b2db9788d31189329bed089ce98/flag
--2025-09-21 23:57:02--  https://mercury.picoctf.net/static/0e428b2db9788d31189329bed089ce98/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: ‘flag.1’

flag.1                               100%[======================================================================>]      34  --.-KB/s    in 0s

2025-09-21 23:57:02 (20.0 MB/s) - ‘flag.1’ saved [34/34]

┌──(BenduOlo253㉿LaBenduPC)-[/mnt/c/Users/jmanu/Downloads]
└─$ cat flag
picoCTF{s4n1ty_v3r1f13d_2fd6ed29}
```
picoCTF{s4n1ty_v3r1f13d_2fd6ed29}
# Notas adicionales 
usamos cat para ver contenido del archivo 

# Referencias 