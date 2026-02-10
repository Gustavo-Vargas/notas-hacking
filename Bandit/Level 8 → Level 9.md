## Description
The password for the next level is stored in the file **data.txt** next to the word **millionth**

### Comandos 
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd
## Solución 

Iniciamos sesión con `bandit8` y la contraseña que nos dio el nivel `Level 7 → Level 8`.

hacemos un listado con `ls` para ver que archivo tenemos 
```
bandit8@bandit:~$ ls
	data.txt
```

Vamos a buscar la contraseña con algunas propiedades:
- **sort data.txt** → ordena todas las líneas. Así las repetidas quedan juntas.
- **uniq -u** → de esas líneas, imprime solo las que no tienen una igual justo al lado (es decir, las que aparecen una sola vez en el archivo).

```
bandit8@bandit:~$ sort data.txt | uniq -u
	4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

Que nos data la contraseña para el siguiente nivel

```
	4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)



