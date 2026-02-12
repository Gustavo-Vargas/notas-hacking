## Description
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

### Comandos 
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

## Solución 

Iniciamos sesión con `bandit9` y la contraseña que nos dio el nivel `Level 8 → Level 9`.

hacemos un listado con `ls` para ver que archivo tenemos 
```
bandit9@bandit:~$ ls
	data.txt
```

Vamos a buscar la contraseña con algunas propiedades:
- **strings data.txt** → muestra solo secuencias de caracteres imprimibles (lo “legible”), ignorando el resto.
- `grep '==='`  → se queda con las líneas que contienen al menos cuatro = seguidos.

```
bandit9@bandit:~$ strings data.txt | grep '==='
========== the
========== password
E========== is
5========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

Que nos data la contraseña para el siguiente nivel

```
	FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)



