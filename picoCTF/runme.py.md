
## Description
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)
## Solución 
- Usar la terminal de WebShell que esta en picoCTF

En la terminal descargamos el archivo que nos dan con el enlace que nos dan
```
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/34/runme.py
```

Corremos el archivo de runme.py para que nso den la bandera
```
user-picoctf@webshell:~$ cat runme.py
#!/usr/bin/python3
################################################################################
# Python script which just prints the flag
################################################################################

flag ='picoCTF{run_s4n1ty_run}'
print(flag)

```

Como esta en python hacemos un `python3` para correrlo y nos den la bandera
```
user-picoctf@webshell:~$ python3 runme.py
picoCTF{run_s4n1ty_run}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/
