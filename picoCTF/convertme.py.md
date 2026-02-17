
## Description
Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/22/convertme.py)

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Descargamos los dos archivos que nos dan con `wget`
```
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/22/convertme.py
```

Corremos el archivo con `python archivo`
```
user-picoctf@webshell:~$ python convertme.py 
```

Nos hara preguntas de conversion y debemos de hacer la conversion para que nos de la bandera
```
user-picoctf@webshell:~$ python convertme.py 
If 98 is in decimal base, what is it in binary base?
Answer: 01100010
	That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_762f748e}
```

Una ves completado el reto nos dará la bandera
```
	picoCTF{4ll_y0ur_b4535_762f748e}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/
