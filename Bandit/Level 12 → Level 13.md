## Description
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

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

Iniciamos sesión con `bandit12` y la contraseña que nos dio el nivel `Level 11 → Level 12`.

Hacemos un listado con `ls` para ver que archivo tenemos 
```
bandit12@bandit:~$ ls
	data.txt
```

Como el archivo es un hexadump por lo que esta comprimido muchas veces, por lo que debemos de reconstruirlo y descomprimir capa por capa.

Vamos a crear una carpeta temporal con `mktemp -d`
```
bandit12@bandit:~$ mktemp -d
/tmp/tmp.PmneaGT5y9
```

Accedemos a la ruta que se creo
```
bandit12@bandit:~$ cd /tmp/tmp.PmneaGT5y9
bandit12@bandit:/tmp/tmp.PmneaGT5y9$
```

Copiamos el archivo `data.txt` a la ruta que se creo
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ cp ~/data.txt .
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ ls
	data.txt
```

- `cp` ->  copia archivos 
- `~` -> significa tu carpeta personal  
- `.` ->  significa carpeta actual

Convertimos el hexdump a archivo real
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ xxd -r data.txt > data
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ ls
	data  data.txt
```

-  `xxd`  -> Convierte entre hexdump y binario.
-  `-r`  -> Significa **reverse** (regresar al archivo original).
-  `> data`  -> Guarda el resultado en un archivo llamado `data`.

Revisamos el tipo de archivo que se creo
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ file data
data: gzip compressed data, was "data2.bin", last modified: Tue Oct 14 09:26:00 2025, max compression, from Unix, original size modulo 2^32 572
```

Descomprimimos con `mv data data.gz`   y `gunzip data.gz` porque es un `gzip compressed data`
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ mv data data.gz
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ ls
data.gz  data.txt
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ gunzip data.gz
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ ls
data  data.txt
```

Hacemos otro `file data` para saber que tipo de archivo quedo
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ file data
data: gzip compressed data, was "data4.bin", last modified: Tue Oct 14 09:26:00 2025, max compression, from Unix, original size modulo 2^32 20480
```

Como nos marca `bzip` ahora debemos de hacer `mv data data.bz2` y `bunzip2 data.bz2` para volver a descomprimir
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ mv data data.bz2
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ ls
	data.bz2  data.txt
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ bunzip2 data.bz2
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ ls
	data  data.txt
```

Hacemos otro `file data` para saber que tipo de archivo quedo
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ file data
data: gzip compressed data, was "data4.bin", last modified: Tue Oct 14 09:26:00 2025, max compression, from Unix, original size modulo 2^32 20480
```

Volvemos a hacer los comandos de  `mv data data.gz` y `gunzip data.gz` para volver a descomprimir
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ mv data data.gz
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ gunzip data.gz
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ ls
data  data.txt
```

Volvemos a verificar el tipo de archivo con `file data`
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ file data
	data: POSIX tar archive (GNU)
```

Como es un archivo `tar archive` usamos el comando de `tar -xf data`
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ tar -xf data
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ ls
	data  data5.bin  data.txt
```

Se creo el archivo `data5.bin`, hacemos un `file data5.bin` para saber que tipo de archivo es 
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ file data5.bin
	data5.bin: POSIX tar archive (GNU)
```

Como es un `tar archive`, hacemos el comando de `tar -xf data`
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ tar -xf data5.bin
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ ls
data  data5.bin  data6.bin  data.txt
```

Volvemos a verificar el tipo de archivo con `file data6.bin`
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
```

Como nos marca `bzip` ahora debemos de hacer `mv data6.bin  data2.bz2` y `bunzip2 data2.bz2` para volver a descomprimir
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ mv data6.bin  data2.bz2
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ bunzip2 data2.bz2
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ ls
	data  data2  data5.bin  data.txt
```

Volvemos a verificar el tipo de archivo con `file data2`
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ file data2
	data2: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ tar -xf data2
```

Como es un archivo `tar archive` usamos el comando de `tar -xf data2`
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ tar -xf data2
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ ls
	data  data2  data5.bin  data8.bin  data.txt
```

Volvemos a verificar el tipo de archivo con `file data8.bin`
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Tue Oct 14 09:26:00 2025, max compression, from Unix, original size modulo 2^32 49
```

Descomprimimos con `mv data8.bin data3.gz`   y `gunzip data.gz` porque es un `gzip compressed data`
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ mv data8.bin data3.gz
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ gunzip data3.gz
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ ls
	data  data2  data3  data5.bin  data.txt
```

Hacemos un ultimo `file data3`
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ file data3
	data3: ASCII text
```

El resultado nos dara la contraseña del siguiente nivel
```
bandit12@bandit:/tmp/tmp.PmneaGT5y9$ cat data3
	The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```


## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)




