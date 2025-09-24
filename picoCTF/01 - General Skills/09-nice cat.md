# Descripción
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 7449`, but it doesn't speak English...

# Solución 
primero ejecute el comando
``` 
┌──(BenduOlo253㉿LaBenduPC)-[~]
└─$ nc mercury.picoctf.net 7449
112
105
99
111
67
84
70
123
103
48
48
100
95
107
49
116
116
121
33
95
110
49
99
51
95
107
49
116
116
121
33
95
102
50
100
55
99
97
102
97
125
10
``` 
Despues lo decifre con una combinacion de comandos de la terminal con ayuda de chat GPT.
``` 
nc mercury.picoctf.net 7449 | grep -oE '[0-9]+' | while read n; do printf "\\$(printf '%03o' $n)"; done; echo
picoCTF{g00d_k1tty!_n1c3_k1tty!_f2d7cafa}
``` 
Solucion : picoCTF{g00d_k1tty!_n1c3_k1tty!_f2d7cafa}

# Notas adicionales 
## `grep -oE '[0-9]+'`

- `grep` = busca patrones en texto.
    
- `-E` = activa **expresiones regulares extendidas**.
    
- `-o` = solo imprime las coincidencias encontradas, **una por línea**.
    
- `'[0-9]+'` = patrón:
    
    - `[0-9]` → cualquier dígito decimal.
        
    - `+` → uno o más dígitos seguidos.

## `while read n; do ... done`

- `while read n` = **bucle que lee línea por línea** de la entrada estándar.
    
- Cada línea se almacena en la variable `n`.
    
- `do ... done` = cuerpo del bucle que se ejecuta para cada número.

## `printf "\\$(printf '%03o' $n)"`

Este es el **truco para convertir decimal → ASCII**:

1. `printf '%03o' $n`
    
    - Convierte el número decimal `$n` a **octal de 3 dígitos** (porque `printf` en Bash usa `\NNN` en octal para caracteres).
        
    - Ejemplo: `$n=72` → `110` (octal).
        
2. `"\\$(...)"`
    
    - Construye el escape de octal para `printf`.
        
    - `"\\110"` = carácter ASCII 72 → `H`.
        
3. `printf "\\$(...)"`
    
    - Imprime el carácter real correspondiente al número ASCII.

# Referencias 
chatGPT