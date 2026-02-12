
## Description
Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...[warm](https://challenge-files.picoctf.net/c_wily_courier/c293351e09ee53217c6a868e7f98a0a2ba0cf9cdc4e4ed0e18f685d47111c216/warm)

#### Comandos 

| Comando                     | Acción                   |
| --------------------------- | ------------------------ |
| `file`                      | Que clase de archivo es  |
| `wget`                      | Descargar archivo        |
| `strings`                   | Saca texto de un archivo |
| `cat`                       | Mostrar contenido        |
| `chmod +x "nombre-archivo"` | Dar permiso al archivo   |

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Necesitamos subir el archivo a Webshell con `wget enlace-archivo` 

```
user-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/c293351e09ee53217c6a868e7f98a0a2ba0cf9cdc4e4ed0e18f685d47111c216/warm
--2026-02-11 22:59:52--  https://challenge-files.picoctf.net/c_wily_courier/c293351e09ee53217c6a868e7f98a0a2ba0cf9cdc4e4ed0e18f685d47111c216/warm
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.64, 3.160.5.18, 3.160.5.40, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 19312 (19K) [application/octet-stream]
Saving to: 'warm'

warm                            100%[=======================================================>]  18.86K  --.-KB/s    in 0.01s   

2026-02-11 22:59:52 (1.92 MB/s) - 'warm' saved [19312/19312]
```

Verificamos la clase de archivo que es con un `file "nombre"`

```
user-picoctf@webshell:~$ file warm
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=9e46ec8729d2f2aa8ffc4b1cdc058081bddcfe67, for GNU/Linux 3.2.0, with debug_info, not stripped
```

Vemos que es un binario ELF, entonces intentaremos aplicar `--help`, para saber si podemos hacer algo
```
user-picoctf@webshell:~$ ./warm --help
-bash: ./warm: Permission denied
```

Necesitamos darle permisos al archivo mediante `chmod +x archivo`

```
user-picoctf@webshell:~$ chmod +x warm
```

Ahora si aplicamos `--help`
```
gushaki-picoctf@webshell:~$ ./warm --help
I don't know what '--help' means! I do know what -h means though!
```

Vemos que no reconoce el comando y nos sugiere usar `-h`
```
gushaki-picoctf@webshell:~$ ./warm -h   
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}
```

Bandera del reto
```
picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}
```


## Notas 

## Referencias
-  https://play.picoctf.org/practice/challenge/37?page=1&search=strings%20it
