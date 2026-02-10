## Description
The password for the next level is stored in a hidden file in the **inhere** directory.
### Comandos 
[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html) , [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html) , [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html) , [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html) , [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html) , [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html)
## Solución 
Iniciamos sesión con bandit3 y la contraseña que nos dio el nivel `Level 2 → Level 3`.

Después listamos para ver el archivo dentro de home con el comando ` ls ` 

```
bandit3@bandit:~$ ls
	inhere
```

Entramos al directorio inhere con el comando de `cd inhere` y listamos `ls` para ver los archivos del directorio.
Como esta vacío vamos a lista con `ls -a`
```
bandit3@bandit:~/inhere$ ls -a
.  ..  ...Hiding-From-You
```

Una ves listado los archivos entramos al archivo con ` cat ./"nombre-archivo"` para que nos de la contraseña del siguiente nivel

```
bandit3@bandit:~/inhere$ cat ./"...Hiding-From-You"
```

Como el archivo tiene un ` - `   vamos a tener que usar el comando de `cat ./-` para acceder al archivo que nos dará la contraseña del siguiente nivel

```
	cat ./"--spaces in this filename--"
```

Que nos data la contraseña para el siguiente nivel

```
	2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```


## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)


