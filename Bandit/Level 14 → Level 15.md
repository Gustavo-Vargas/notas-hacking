## Description
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

#### Comandos 

| Comando | Acción          |
| ------- | --------------- |
| `nc`    | Listar archivos |

## Solución 

Iniciamos sesión con `bandit14` y la contraseña que nos dio el nivel `Level 13 → Level 14`.

Nos conectamos al puerto 30000 con `nc`, ingresamos la contraseña que habíamos obtenido en el nivel anterior 
```
bandit14@bandit:~$ nc localhost 30000
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

El resultado nos dará la contraseña del siguiente nivel
```
	 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```


## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)




