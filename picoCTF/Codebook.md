
## Description
Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/3/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/3/codebook.txt)

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Descargamos los dos archivos que nos dan con `wget`
```
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/3/code.py
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/3/codebook.txt
```

Abrimos el archivo de `file code.py`, aquí nos da la bandera
```
user-picoctf@webshell:~$ python code.py
	picoCTF{c0d3b00k_455157_197a982c}
```

Pero podemos hacer un `nano code.py` y ver si podemos buscar otra forma de sacar la bandera, como vemos que la bandera se debe de hacer una transformación por eso es el programa y lo haga
```
flag_enc = chr(0x13) + chr(0x01) + chr(0x17) + chr(0x07) + chr(0x2c) + chr(0x3a) + chr(0x2f) + chr(0x1a) + chr(0x0d) + chr(0x53) + chr(0x0c) + chr(0x47) + chr(0x0a) + chr(0x5f) + chr(0x5e) + chr(0x02) + chr(0x3e) + chr(0x5a) + chr(0x56>

```

Una ves completado el reto nos dara la bandera
```
	picoCTF{c0d3b00k_455157_197a982c}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/
