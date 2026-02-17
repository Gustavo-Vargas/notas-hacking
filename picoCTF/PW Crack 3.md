
## Description
Can you crack the password to get the flag?
Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too.
There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.
## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Descargamos los dos archivos que nos dan con `wget`
```
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/17/level3.py
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/17/level3.hash.bin

user-picoctf@webshell:~$ ls
	level3.flag.txt.enc  level3.hash.bin  level3.py
```

Entramos con `nano level3.py` para ver como acceder a la contraseña y encotnramos 7 posibles contraseñas
```
["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]
```

Probamos las contraseñas y la correcta fue `87ab`, que nos dara la badnera
```
user-picoctf@webshell:~$ python level3.py
Please enter correct password for flag: 87ab
Welcome back... your flag, user:
	picoCTF{m45h_fl1ng1ng_cd6ed2eb}
```

Una ves completado el reto nos dará la bandera
```
	picoCTF{m45h_fl1ng1ng_cd6ed2eb}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/
