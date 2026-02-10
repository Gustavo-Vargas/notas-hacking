## Description
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable

### Comandos 
[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html) , [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html) , [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html) , [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html) , [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html) , [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html)
## Solución 

Iniciamos sesión con `bandit5` y la contraseña que nos dio el nivel `Level 4 → Level 5`.

Después listamos para ver el archivo dentro de home con el comando ` ls ` 
```
bandit5@bandit:~$ ls
	inhere
```

Entramos al directorio inhere con el comando de `cd inhere` y listamos `ls` para ver los archivos del directorio.

```
bandit5@bandit:~/inhere$ ls
	maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  
	maybehere18  maybehere01  maybehere04  maybehere07  maybehere10  maybehere13
	maybehere16  maybehere19  maybehere02  maybehere05  maybehere08  maybehere11
	maybehere14  maybehere17
```

Ahora necesitamos ver el tamaño de los directorios y ver cual es el que tiene los archivos por lo que aplicaremos el pigeonite comando para ver donde esta el archivo que estamos buscando
```
bandit5@bandit:~/inhere$ find . -type f -size 1033c
	./maybehere07/.file2
```

Teniendo al ruta donde esta el archivo hacernos un `cat` para poder leer lo que esta dentro
```
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
	HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

Que nos data la contraseña para el siguiente nivel

```
	HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)


