## Description
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

### Comandos 
[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html) , [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html) , [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html) , [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html) , [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html) , [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html)

| Comando           | Acción                                      |
| ----------------- | ------------------------------------------- |
| `ls`              | Listar archivos                             |
| `cd dirname`      | Cambiar de directorio                       |
| `cat file`        | Mostrar contenido                           |
| `du`              | Uso por directorios                         |
| `find file`       | Buscar archivo                              |


## Solución 
Entrar al archivo de readme con el comando: 
```
	cat readme
```

Que nos dará la contraseña para iniciar sesión con el usuario bandit1 mediante SSH.
```
	The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

Iniciamos sesión con bandit1 y la contraseña que nos dio para continuar con la pagina de `Level 1 → Level 2`


## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)
