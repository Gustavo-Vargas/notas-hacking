
## Description
Can you find the flag in [file](https://challenge-files.picoctf.net/c_fickle_tempest/563d66bbed3925c75ed71efa974bfafab26460ae99938d699a8881cd173fca60/strings) without running it?

#### Comandos 

| Comando   | Acción                   |
| --------- | ------------------------ |
| `wget`    | Descargar archivo        |
| `strings` | Saca texto de un archivo |
| `grep`    | Mostrar contenido        |
## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Necesitamos encontrar la bandera sin correr el archivo, entonces necesitamos subir el archivo al WebShell para poder extraer la bandera sin necesidad de abrir el archivo.

Ingresamos a la terminal de WbeShell y hacemos un `wget ruta-archivo` que podemos dar click derecho al archivo y copiar la direccion de enlace

```
user-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_fickle_tempest/563d66bbed3925c75ed71efa974bfafab26460ae99938d699a8881cd173fca60/strings

Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 784424 (766K) [application/octet-stream]
Saving to: 'strings'

strings                         100%[=======================================================>] 766.04K  1.83MB/s    in 0.4s    

2026-02-11 21:48:21 (1.83 MB/s) - 'strings' saved [784424/784424]

```

Listamos para corroborar que se subió correctamente el archivo

```
gushaki-picoctf@webshell:~$ ls
README.txt  salida.txt  strings
```

Ahora aplicamos el comando de `strings` con n `grep` para que nos busque la palabra picoCTF
```
gushaki-picoctf@webshell:~$ strings "strings" | grep -i picoCTF  
picoCTF{5tRIng5_1T_dB2CEA76}
```


Una ves completado el reto nos dará la bandera
```
You've beaten the challenge
	Flag: picoCTF{learning_about_converting_values_acdCcfCa}
```

## Notas 

## Referencias
-  https://play.picoctf.org/practice/challenge/37?page=1&search=strings%20it
