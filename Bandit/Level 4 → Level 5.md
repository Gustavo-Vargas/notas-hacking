## Description
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.
### Comandos 
[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html) , [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html) , [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html) , [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html) , [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html) , [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html)
## Solución 
Iniciamos sesión con bandit4 y la contraseña que nos dio el nivel `Level 3 → Level 4`.

Después listamos para ver el archivo dentro de home con el comando ` ls ` 

```
bandit4@bandit:~$ ls
	inhere
```

Entramos al directorio inhere con el comando de `cd inhere` y listamos `ls` para ver los archivos del directorio.

```
bandit4@bandit:~/inhere$ ls
	-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
```

Si entramos a algún archivo tendremos texto no legible, por esto seria bueno hacer el comando de para saber el tipo de archivo del listado que apareció para que nos muestre el que si es legible

```
bandit4@bandit:~/inhere$ file ./-file*
	./-file00: data
	./-file01: data
	./-file02: data
	./-file03: data
	./-file04: data
	./-file05: data
	./-file06: data
	./-file07: ASCII text
	./-file08: data
	./-file09: data
```


Solo uno es texto ASCCI por lo cual es el que ingresamos con `cat ./nombre-archivo`

```
bandit4@bandit:~/inhere$ cat ./-file07
	4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

Que nos data la contraseña para el siguiente nivel

```
	4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```


## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)


