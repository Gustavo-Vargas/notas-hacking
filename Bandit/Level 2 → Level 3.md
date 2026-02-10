## Description
The password for the next level is stored in a file called `--spaces in this filename--` located in the home directory

### Comandos 
[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html) , [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html) , [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html) , [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html) , [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html) , [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html)
## Solución 
Iniciamos sesión con bandit2 y la contraseña que nos dio el nivel `Level 1 → Level 2`.

Después listamos para ver el archivo dentro de home con el comando ` ls `

```
bandit2@bandit:~$ ls
	--spaces in this filename--
```

Como el archivo tiene un ` - `   vamos a tener que usar el comando de `cat ./-` para acceder al archivo que nos dará la contraseña del siguiente nivel

```
	cat ./"--spaces in this filename--"
```

Que nos data la contraseña para el siguiente nivel

```
	MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```


## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)


