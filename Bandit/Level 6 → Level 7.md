## Description
The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

### Comandos 
[ls](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html) , [cd](https://manpages.ubuntu.com/manpages/noble/man1/cd.1posix.html) , [cat](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html) , [file](https://manpages.ubuntu.com/manpages/noble/man1/file.1.html) , [du](https://manpages.ubuntu.com/manpages/noble/man1/du.1.html) , [find](https://manpages.ubuntu.com/manpages/noble/man1/find.1.html), grep
## Solución 

Iniciamos sesión con `bandit6` y la contraseña que nos dio el nivel `Level 5 → Level 6`.

Vamos a buscar el archivo con algunas las propiedades de:

- **/** = desde la raíz (todo el servidor). Si prefieres solo tu home: find ~ -type f ...
- **-type f** = solo archivos
- **-user bandit7** = dueño bandit7
- **-group bandit6** = grupo bandit6
- **-size 33c** = 33 bytes
- **2>/dev/null** = oculta los "Permission denied" al intentar leer carpetas sin permiso

```
bandit6@bandit:~$ find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
	/var/lib/dpkg/info/bandit7.password
```

Accedemos al archivo con la ruta que nos dio
```
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
	morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

Que nos data la contraseña para el siguiente nivel

```
	morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)


