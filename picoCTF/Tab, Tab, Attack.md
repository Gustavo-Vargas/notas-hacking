
## Description
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames.[Addadshashanammu.zip](https://challenge-files.picoctf.net/c_wily_courier/56f53a4189949d066fe969e998769a4e0390123be59782c06e6c0a52c78403e2/Addadshashanammu.zip)

#### Comandos 

| Comando                | Acción                            |
| ---------------------- | --------------------------------- |
| `unzip`                | Extraer zip                       |
| `cd`                   | Cambiar de directorio             |

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Debemos de subir el archivo que nos dan a la termina de Webshell con  con `wget enlace-archivo` 

```
user-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/56f53a4189949d066fe969e998769a4e0390123be59782c06e6c0a52c78403e2/Addadshashanammu.zip
--2026-02-12 00:45:30--  https://challenge-files.picoctf.net/c_wily_courier/56f53a4189949d066fe969e998769a4e0390123be59782c06e6c0a52c78403e2/Addadshashanammu.zip
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.64, 3.160.5.95, 3.160.5.18, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 5166 (5.0K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip        100%[=========================================>]   5.04K  --.-KB/s    in 0s      

2026-02-12 00:45:30 (3.41 GB/s) - 'Addadshashanammu.zip' saved [5166/5166]
```


Listamos para ver que se subió el archivo correctamente
```
user-picoctf@webshell:~$ ls
	Addadshashanammu.zip  README.txt 
```

Como agregamos un zip ahora necesitamos descomprimir el zip usando `unzip archivo`
```
user-picoctf@webshell:~$ unzip Addadshashanammu.zip 
user-picoctf@webshell:~$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
 extracting: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet.c  
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  

```

Ahora vamos a entrar a carpeta usando tap pero con `cd Addda` hasta llegar a la carpeta final
```
user-picoctf@webshell:~$ cd Addadshashanammu/
user-picoctf@webshell:~/Addadshashanammu$ cd Almurbalarammi/
user-picoctf@webshell:~/Addadshashanammu/Almurbalarammi$ cd Ashalmimilkala/
user-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala$ cd Assurnabitashpi/
user-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi$ cd Maelkashishi 
gushaki-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi$ cd Onnissiralis/
gushaki-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissi
ralis$ cd Ularradallaku/
user-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissi
```

Listamos para ver que archivo vamos a buscar la bandera
```
user-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissi
ralis/Ularradallaku$ ls
fang-of-haynekhtnamet  fang-of-haynekhtnamet.c
```


Buscamos la palabra picoCTF con el `strings y picoCTF`  para que nos de la bandera
```
user-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissi
ralis/Ularradallaku$ strings fang-of-haynekhtnamet | grep  picoCTF
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_fc588427}
```

## Notas 

## Referencias
-  https://play.picoctf.org/practice/challenge/37?page=1&search=strings%20it
