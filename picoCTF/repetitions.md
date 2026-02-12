## Description
Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/475/enc_flag).

#### Comandos 

| Comando       | Acción                                |
| ------------- | ------------------------------------- |
| `wgep enlace` | Subir archivo a terminal              |
| `echo`        | Muestra el texto                      |
| ` \| `        | Pasa el resultaod al sigeinte comadno |
| `base64 -d`   | Decodifica texto en Base64            |


## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Subimos el archivo a la terminal de Webshell con `wget enlace-archivo`
 ```
user-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/475/enc_flag
--2026-02-12 02:48:12--  https://artifacts.picoctf.net/c/475/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.72, 3.170.131.18, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.72|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 349 [application/octet-stream]
Saving to: 'enc_flag'

enc_flag                    100%[=========================================>]     349  --.-KB/s    in 0s      

2026-02-12 02:48:12 (15.3 MB/s) - 'enc_flag' saved [349/349]
 ```

Hacemos un ls para ver el nuevo archivo y hacemos un `cat archivo` para saber el siguiente paso.
```
user-picoctf@webshell:~$ ls
Addadshashanammu.zip  README.txt  enc_flag  ltdis.sh  salida.txt  static  strings  warm
user-picoctf@webshell:~$ cat enc_flag 
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZrTTBKVVZXcE9VazFXV2toT1dHUllDbUY2UWpSWk1GWlhWa2RHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
```

Vemos que es una cadena base64 por lo que procedemos a hacer una transformación dentro de la terminal con el comando de 
```
	echo "texto" | base64 -d
```

Como se intento varias veces y seguía saliendo texto se opto por hacer una linea con barias transformaciones para descartar errores humano.
```
user-picoctf@webshell:~$ echo "VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh 
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZrTTBKVVZXcE9VazFXV2toT1dHUllDbUY2UWpSWk1GWlhWa2RHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==" | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d            
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_492767d2}
```

Bandera del nivel
```
	picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_492767d2}
```

## Notas 

## Referencias
-  https://play.picoctf.org/practice/challenge/37?page=1&search=strings%20it
