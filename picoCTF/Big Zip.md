## Description
Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/504/big-zip-files.zip)

#### Comandos 

| Comando       | Acción                         |
| ------------- | ------------------------------ |
| `wgep enlace` | Subir archivo a terminal       |
| `grep`        | Busca texto dentro de archivos |
| `unzip`       | descomprimir archivo           |


## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Hacemos la descarga del zip que nos mandan con `wget enlace`
```
user-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/504/big-zip-files.zip
--2026-02-12 02:55:24--  https://artifacts.picoctf.net/c/504/big-zip-files.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.18, 3.170.131.33, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3182988 (3.0M) [application/octet-stream]
Saving to: 'big-zip-files.zip'

big-zip-files.zip           100%[=========================================>]   3.04M  1.83MB/s    in 1.7s    

2026-02-12 02:55:26 (1.83 MB/s) - 'big-zip-files.zip' saved [3182988/3182988]

```

Vemos que es un zip, entonces hacemos un `unzip` para descomprimir el zip
```
gushaki-picoctf@webshell:~$ ls
Addadshashanammu.zip  README.txt  big-zip-files.zip  enc_flag  ltdis.sh  salida.txt  static  strings  warm
```

Es muy grande por lo que se buscara con el siguieten coamdno
```
	grep -r "picoCTF" .
```

- `grep`   -> Busca texto dentro de archivos.
- `-r`  -> Busca de forma recursiva (entra a todas las carpetas).
- `"picoCTF"`  -> Texto que estás buscando (la flag).
- `.` -> Significa "buscar desde la carpeta actual".

```
user-picoctf@webshell:~/big-zip-files$ grep -r "picoCTF" .
./folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
```

Bandera del nivel
```
	picoCTF{gr3p_15_m4g1c_ef8790dc}
```

## Notas 

## Referencias
-  [https://play.picoctf.org/practice/challenge/37?page=1&search=strings%20it](https://play.picoctf.org/practice/challenge/322?page=1&search=Big%20zip)
