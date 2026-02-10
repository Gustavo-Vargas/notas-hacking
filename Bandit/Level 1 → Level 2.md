## Description
The password for the next level is stored in a file called **-** located in the home directory

### Comandos 
[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html) , [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html) , [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html) , [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html) , [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html) , [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html)

| Comando      | Acción                |
| ------------ | --------------------- |
| `ls`         | Listar archivos       |
| `cd dirname` | Cambiar de directorio |
| `cat file`   | Mostrar contenido     |
| `du`         | Uso por directorios   |
| `find file`  | Buscar archivo        |

## Solución 
Iniciamos sesión con bandit1 y la contraseña que nos dio el nivel `Level 0 → Level 1`.

Después listamos para ver el archivo dentro de home con el comando

```
	cat ./-
```

Que nos data la contraseña para el siguiente nivel

```
	263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```


## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)
