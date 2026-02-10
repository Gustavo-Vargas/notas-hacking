## Description
The password for the next level is stored in the file **data.txt** next to the word **millionth**

### Comandos 
[man](https://manpages.ubuntu.com/manpages/noble/man1/man.1.html), grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd
## Solución 

Iniciamos sesión con `bandit7` y la contraseña que nos dio el nivel `Level 6 → Level 7`.

hacemos un listado con `ls` para ver que archivo tenemos 
```
bandit7@bandit:~$ ls
	data.txt
```

Para acceder al archivo buscando una palabra es con `grep palabra nombre-archivo.txt`
```
bandit7@bandit:~$ grep millionth data.txt
	millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

Que nos data la contraseña para el siguiente nivel

```
	dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)



