

## Description
I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/139/challenge.zip)

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Descargamos el .zip que nos dan y lo descomprimimos para saber que pista encontramos
```
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c_titan/139/challenge.zip
user-picoctf@webshell:~$ ls
README.txt  challenge.zip
user-picoctf@webshell:~$ unzip challenge.zip 
```

Ahora intentaremos recuperar el archivo borrado, entrando a ver el historial con `cd drop-in` para ingresar a la carpeta y `git log` para ver historial
```
user-picoctf@webshell:~$ cd drop-in/
user-picoctf@webshell:~/drop-in$ git log
```

```
commit 144fdc44b09058d7ea7f224121dfa5babadddbb9 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:25 2024 +0000

    remove sensitive info

commit 7d3aa557ff7ba7d116badaf5307761efb3622249
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:25 2024 +0000
```

Ahora entramos a ver el ultimo commit con `git show HEAD`
```
commit 144fdc44b09058d7ea7f224121dfa5babadddbb9 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:25 2024 +0000

    remove sensitive info

diff --git a/message.txt b/message.txt
index 3a71673..d552d1e 100644
--- a/message.txt
+++ b/message.txt
@@ -1 +1 @@
-picoCTF{s@n1t1z3_be3dd3da}
+TOP SECRET
```


Este si nos mostro la bandera
```
	picoCTF{s@n1t1z3_be3dd3da}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/




