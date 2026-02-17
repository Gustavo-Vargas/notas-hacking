
## Description
Fix the syntax error in this Python script to print the flag.
[Download Python script](https://artifacts.picoctf.net/c/27/fixme1.py)

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Descargamos los dos archivos que nos dan con `wget`
```
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/27/fixme1.py
user-picoctf@webshell:~$ ls
	fixme1.py
```

Entramos al archivo con `nano` y vemos que debemos de arreglar
```
user-picoctf@webshell:~$ nano fixme1.py
```

AL arreglar el código que era erro de indentación, probamos con `python archivo` 
```
user-picoctf@webshell:~$ python fixme1.py 
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}
```


Una ves completado el reto nos dará la bandera
```
	picoCTF{1nd3nt1ty_cr1515_182342f7}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/




