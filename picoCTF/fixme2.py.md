
## Description
Fix the syntax error in the Python script to print the flag.
[Download Python script](https://artifacts.picoctf.net/c/5/fixme2.py)

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Descargamos los dos archivos que nos dan con `wget`
```
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/5/fixme2.py
user-picoctf@webshell:~$ ls
	fixme2.py
```

Entramos al archivo con `nano` y vemos que debemos de arreglar
```
user-picoctf@webshell:~$ nano fixme2.py
```

AL arreglar el código que era erro de indentación, probamos con `python archivo` 
```
user-picoctf@webshell:~$ python fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
```


Una ves completado el reto nos dará la bandera
```
	picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/




