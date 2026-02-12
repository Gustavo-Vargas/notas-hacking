## Description

Unzip this archive and find the file named 'uber-secret.txt'
- [Download zip file](https://artifacts.picoctf.net/c/500/files.zip)

#### Comandos 

| Comando       | Acción                   |
| ------------- | ------------------------ |
| `wgep enlace` | Subir archivo a terminal |
| `find`        | Busca archivos           |
| `unzip`       | descomprimir archivo     |


## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Hacemos la descarga del zip que nos mandan con `wget enlace`
```
user-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/500/files.zip
--2026-02-12 03:10:11--  https://artifacts.picoctf.net/c/500/files.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.72, 3.170.131.77, 3.170.131.33, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.72|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3995553 (3.8M) [application/octet-stream]
Saving to: 'files.zip'

files.zip                   100%[=========================================>]   3.81M  1.82MB/s    in 2.1s    

2026-02-12 03:10:14 (1.82 MB/s) - 'files.zip' saved [3995553/3995553]
```

Listamos para comprobar que fue correcto
```
user-picoctf@webshell:~$ ls
Addadshashanammu.zip  big-zip-files.zip  files.zip  salida.txt  strings
README.txt            enc_flag           ltdis.sh   static      warm
```

Descomprimimos el archivo zip
```
user-picoctf@webshell:~$ unzip files.zip 
Archive:  files.zip
   creating: files/
   creating: files/satisfactory_books/
   creating: files/satisfactory_books/more_books/
  inflating: files/satisfactory_books/more_books/37121.txt.utf-8  
  inflating: files/satisfactory_books/23765.txt.utf-8  
  inflating: files/satisfactory_books/16021.txt.utf-8  
  inflating: files/13771.txt.utf-8   
   creating: files/adequate_books/
   creating: files/adequate_books/more_books/
   creating: files/adequate_books/more_books/.secret/
   creating: files/adequate_books/more_books/.secret/deeper_secrets/
   creating: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/
 extracting: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt  
  inflating: files/adequate_books/more_books/1023.txt.utf-8  
  inflating: files/adequate_books/46804-0.txt  
  inflating: files/adequate_books/44578.txt.utf-8  
   creating: files/acceptable_books/
   creating: files/acceptable_books/more_books/
  inflating: files/acceptable_books/more_books/40723.txt.utf-8  
  inflating: files/acceptable_books/17880.txt.utf-8  
  inflating: files/acceptable_books/17879.txt.utf-8  
  inflating: files/14789.txt.utf-8   
```

Como vemos que es un directorio y probablemente sea muy grande hacemos una búsqueda con 
```
	find . -name "uber-secret.txt" 
```
- `find` → Busca archivos  
- `.` → Busca desde la carpeta actual  
- `-name` → Busca por nombre exacto

Nos dará la ruta donde se encuentra el archivo
```
user-picoctf@webshell:~$ find . -name "uber-secret.txt"
./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
```

Accedemos a la ruta y abrimos el archivo para encontrar la bandera
```
user-picoctf@webshell:~/files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets$ cat uber-secret.txt 
picoCTF{f1nd_15_f457_ab443fd1}
```

Bandera del nivel
```
	picoCTF{f1nd_15_f457_ab443fd1}
```

## Notas 

## Referencias
- https://play.picoctf.org/practice/challenge/320?page=1&search=First%20Find

