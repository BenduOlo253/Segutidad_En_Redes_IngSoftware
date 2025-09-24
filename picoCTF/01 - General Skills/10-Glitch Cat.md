# Descripción
Our flag printing service has started glitching!`$ nc saturn.picoctf.net 51295

# Solución 
1. Nos conectamos al servicio usando `nc saturn.picoctf.net 51295`.

2. La salida recibida fue: 
   `┌──(BenduOlo253㉿LaBenduPC)-[~]
└─$ nc saturn.picoctf.net 51295
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'`

3. Ya que una de las pistas fue que la salida era ejecutable en python, decidi imprimir la salida con un print en python
```
>>> print('picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}')
picoCTF{gl17ch_m3_n07_9c42a45d}
```

solucion : picoCTF{gl17ch_m3_n07_9c42a45d}



# Notas adicionales 
- Esta técnica de “glitching” es común en CTFs donde la salida no está en texto plano, sino codificada o fragmentada.

- Python ayuda a reconstruir la información fácilmente usando `chr()` y concatenación.
# Referencias 