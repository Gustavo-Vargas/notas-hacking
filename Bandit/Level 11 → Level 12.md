## Description
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

#### Comandos 

| Comando          | Acción                               |
| ---------------- | ------------------------------------ |
| `ls`             | Listar archivos                      |
| `cat archivo`    | Mostrar contenido del archivo        |
| `cat data.txt`   | Muestra el contenido del archivo.    |
| `\|`             | Pasa el texto al siguiente comando   |
| `tr`             | Sirve para reemplazar caracteres     |
| `'A-Za-z'`       | Indica todas las letras.             |
| `'N-ZA-Mn-za-m'` | Es el alfabeto rotado 13 posiciones. |

## Solución 

Iniciamos sesión con `bandit11` y la contraseña que nos dio el nivel `Level 10 → Level 11`.

Hacemos un listado con `ls` para ver que archivo tenemos 
```
bandit11@bandit:~$ ls
	data.txt
```

Hacemos un `cat` para acceder al archivo y poder ver el texto el caul debemos de regresar a su estado original
```
bandit11@bandit:~$ cat data.txt
	Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4
```

Tenemos que regresar la rotación de las letras con `tr` para poder acceder a la siguiente contraseña con:
```
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

- `cat data.txt`  -> Muestra el contenido del archivo.
-  `|`  -> Pasa el texto al siguiente comando.
-  `tr`  -> Sirve para reemplazar caracteres.
-  `'A-Za-z'`  -> Indica todas las letras.
-  `'N-ZA-Mn-za-m'`  -> Es el alfabeto rotado 13 posiciones.

El resultado nos dara la contraseña del siguiente nivel
```
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
	The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```

## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)




