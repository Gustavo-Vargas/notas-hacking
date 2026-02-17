
## Description
Find the flag in the Python script! [Download Python script](https://artifacts.picoctf.net/c/37/serpentine.py)

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Descargamos los dos archivos que nos dan con `wget`
```
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/37/serpentine.py
user-picoctf@webshell:~$ ls
	serpentine.py
```


Entramos con `python serpentine.py` para ver que hacer
```
Welcome to the serpentine encourager!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) 
```

Damos en `b` 
```
What would you like to do? (a/b/c) b

Oops! I must have misplaced the print_flag function! Check my source code!
```

Entonces entramos con `nano serpentine.py` para ver el código y saber como encontrar la bandera. Entramos lo que puede ser la bandera
```
flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5>
```

Vemos que hay un `>` al final de chr(0x5, eso significa que falta mas código a la derecha y esta largo, entonces debemos importar toda la `flag_enc` para poder acceder a la bandera con
```
user-picoctf@webshell:~$ python3 -c "import serpentine; serpentine.print_flag()"
	picoCTF{7h3_r04d_l355_7r4v3l3d_8e47d128}
```

Una ves completado el reto nos dará la bandera
```
	picoCTF{7h3_r04d_l355_7r4v3l3d_8e47d128}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/
