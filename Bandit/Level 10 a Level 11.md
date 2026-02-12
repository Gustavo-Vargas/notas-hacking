## Description
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

#### Comandos 

| Comando       | Acción                        |
| ------------- | ----------------------------- |
| `ls`          | Listar archivos               |
| `cat archivo` | Mostrar contenido del archivo |


## Solución 

Iniciamos sesión con `bandit10` y la contraseña que nos dio el nivel `Level 9 → Level 10`.

Hacemos un listado con `ls` para ver que archivo tenemos 
```
bandit10@bandit:~$ ls
	data.txt
```

Hacemos un `cat` para acceder al archivo y poder ver el texto en base64 para poder transformarlo a texto.
```
bandit10@bandit:~$ cat data.txt
	VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==
```

A transformarlo a texto nos da que es la contraseña del siguiente nivel
```
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)
- https://gchq.github.io/CyberChef/



