
## Description
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.

## Solución 
- Usar la terminal de WebShell que esta en picoCTF


Descargamos los dos archivos que nos dan con `wget`
```
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/13/level2.py
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
```

ahora hacemos un `nano level2.py` para saber como esta el código de python y encontramos la contraseña encriptada.
```
def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ):
```


Como esta la contraseña en char() entonces hacemos un `python3 -c "print()"` para que nos de la contraseña desencriptada
```
user-picoctf@webshell:~$ python3 -c "print(chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36))"
	de76
```


Corremos con `python` y agregamos la contraseña desencriptada que obtuvimos
```
user-picoctf@webshell:~$ python level2.py 
Please enter correct password for flag: de76
Welcome back... your flag, user:
	picoCTF{tr45h_51ng1ng_489dea9a}
```

Una ves completado el reto nos dará la bandera
```
	picoCTF{tr45h_51ng1ng_489dea9a}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/
