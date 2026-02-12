
## Description
Can you look at the data in this binary? The bash script might help! [static](https://challenge-files.picoctf.net/c_wily_courier/b06384f5fdb3a6e3f0f254d1064d203e7df4bf7e9a5780a95622523367d82bc0/static), [ltdis.sh](https://challenge-files.picoctf.net/c_wily_courier/b06384f5fdb3a6e3f0f254d1064d203e7df4bf7e9a5780a95622523367d82bc0/ltdis.sh)

#### Comandos 

| Comando                     | Acción                            |
| --------------------------- | --------------------------------- |
| `file`                      | Que clase de archivo es           |
| `wget`                      | Descargar archivo                 |
| `strings`                   | Saca texto de un archivo          |
| `cat`                       | Mostrar contenido                 |
| `chmod +x "nombre-archivo"` | Dar permiso al archivo            |
| `grep palabra archivo`      | Buscar en el archivo sin correrlo |

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Debemos de subir los archivos que nos dan a la termina de Webshell con  con `wget enlace-archivo` 

```
user-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/b06384f5fdb3a6e3f0f254d1064d203e7df4bf7e9a5780a95622523367d82bc0/static
--2026-02-11 23:36:06--  https://challenge-files.picoctf.net/c_wily_courier/b06384f5fdb3a6e3f0f254d1064d203e7df4bf7e9a5780a95622523367d82bc0/static
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.18, 3.160.5.95, 3.160.5.40, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16776 (16K) [application/octet-stream]
Saving to: 'static'

static                          100%[=======================================================>]  16.38K  --.-KB/s    in 0.006s  

2026-02-11 23:36:07 (2.53 MB/s) - 'static' saved [16776/16776]

user-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/b06384f5fdb3a6e3f0f254d1064d203e7df4bf7e9a5780a95622523367d82bc0/ltdis.sh
--2026-02-11 23:36:19--  https://challenge-files.picoctf.net/c_wily_courier/b06384f5fdb3a6e3f0f254d1064d203e7df4bf7e9a5780a95622523367d82bc0/ltdis.sh
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.64, 3.160.5.18, 3.160.5.95, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: 'ltdis.sh'

ltdis.sh                        100%[=======================================================>]     785  --.-KB/s    in 0s      

2026-02-11 23:36:19 (416 MB/s) - 'ltdis.sh' saved [785/785]
```

Ahora como nos dan un binario y un script bash para analizarlo
```
static      → binario
ltdis.sh    → script bash para analizarlo
```

Tendremos que ver para que sirve el `ltdis.sh` por lo que aplicamos un `cat`
```
user-picoctf@webshell:~$ cat ltdis.sh
#!/bin/bash


echo "Attempting disassembly of $1 ..."


#This usage of "objdump" disassembles all (-D) of the first file given by 
#invoker, but only prints out the ".text" section (-j .text) (only section
#that matters in almost any compiled program...

objdump -Dj .text $1 > $1.ltdis.x86_64.txt


#Check that $1.ltdis.x86_64.txt is non-empty
#Continue if it is, otherwise print error and eject

if [ -s "$1.ltdis.x86_64.txt" ]
then
        echo "Disassembly successful! Available at: $1.ltdis.x86_64.txt"

        echo "Ripping strings from binary with file offsets..."
        strings -a -t x $1 > $1.ltdis.strings.txt
        echo "Any strings found in $1 have been written to $1.ltdis.strings.txt with file offset"



else
        echo "Disassembly failed!"
        echo "Usage: ltdis.sh <program-file>"
        echo "Bye!"
fi
```

Necesitamos darle permisos a ltdis.sh con `chmod +x archivo ` 
```
user-picoctf@webshell:~$ chmod +x ltdis.sh  
```

Ahora como nos que $1 esto lo debemos de remplazar por el archivo que nos dieron, en este caso es `static`
```
user-picoctf@webshell:~$ ./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
```

Al momento de listar nos mostrara 2 archivos nuevos que se crearon al ejecutar el bash
```
static.ltdis.x86_64.txt
static.ltdis.strings.txt
```

Ahora con el archivo de `static.ltdis.strings.txt` vamos hacer un `grep` para buscar la bandera
```
user-picoctf@webshell:~$ grep picoCTF static.ltdis.strings.txt
   3020 picoCTF{d15a5m_t34s3r_20335e41}
```



## Notas 

## Referencias
-  https://play.picoctf.org/practice/challenge/37?page=1&search=strings%20it
