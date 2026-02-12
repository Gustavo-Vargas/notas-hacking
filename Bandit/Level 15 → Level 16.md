## Description
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL/TLS encryption.

**Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.**

#### Comandos 

| Comando                                  | Acción                                     |
| ---------------------------------------- | ------------------------------------------ |
| `ls`                                     | Listar archivos                            |
| `mktemp -d`                              | Crea carpeta temporal con nombre aleatorio |
| `cp ruta .`                              | Copia archivos                             |
| `xxd -r data.txt > data`                 | Convierte entre hexdump y binaro           |
| `file arhcivo`                           | Ver tipo de archivo                        |
| `mv data data.gz`<br>`gunzip data.gz`    | Descomprimir si es `gzip compressed data`  |
| `mv data data.bz2`<br>`bunzip2 data.bz2` | Descomprimir si es `bzip2 compressed data` |
| `tar -xf data`                           | Descomprimir si es `tar archive`           |
|                                          |                                            |

## Solución 

Iniciamos sesión con `bandit15` y la contraseña que nos dio el nivel `Level 14 → Level 15`.

Vamos a conectarnos mediante SSL con la contraseña obtenida en el nivel anterior
```
bandit15@bandit:~$ openssl s_client -connect localhost:30001
```

Ingresamos la contraseña obtenida en el nivel anterior
```
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
Correct!
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

closed
```


El resultado nos dará la contraseña del siguiente nivel
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ cat data3
	The password is kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```


## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)




