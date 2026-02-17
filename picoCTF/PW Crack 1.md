
## Description
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/12/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) in the same directory too.

## Solución 
- Usar la terminal de WebShell que esta en picoCTF


Descargamos los dos archivos que nos dan con `wget`
```
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/12/level1.py
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
```

hacemos un `file *` para poder saber el tipo de archivo que descargamos
```
user-picoctf@webshell:~$ file *      
level1.flag.txt.enc: data
level1.py:           ASCII text, with CRLF line terminators
```

Ahora abrimos el archivo con `nano` para saber cual es el proceso de descripción, Para encontrar un password y correr el archivo de `level1.flag.txt.enc`
```
def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "8713"):
        print("Welcome back... your flag, user:")
```

Ahora corremos el archivo con `python level1.py` y ponemos la contraseña que vimos.
```
user-picoctf@webshell:~$ python level1.py
Please enter correct password for flag: 8713
Welcome back... your flag, user:
	picoCTF{545h_r1ng1ng_1b2fd683}
```

Una ves completado el reto nos dara la bandera
```
	picoCTF{545h_r1ng1ng_1b2fd683}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/
