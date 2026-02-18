
## Description
Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/159/challenge.zip)

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Descargamos el .zip que nos dan y lo descomprimimos para saber que pista encontramos
```
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c_titan/159/challenge.zip
user-picoctf@webshell:~$ ls
challenge.zip
user-picoctf@webshell:~$ unzip challenge.zip 
```

Entramos a la carpeta que se descomprimió y leemos el mensaje para ver que pista nos deja
```
user-picoctf@webshell:~$ cd drop-in/
user-picoctf@webshell:~/drop-in$ ls
	message.py
user-picoctf@webshell:~/drop-in$ cat message.py 
	print("Hello, World!"
```

debemos de buscar quien cambio el código y lo dejo mal, podemos ir probando con `git show HEAD:message.py` y de ahi para abajo para ver donde el correcto
Pero podemos hacer un `git log -p` para ver los cambios y ver donde esta el correcto y encontrar a donde esta el commit correcto
```
commit 23e9d4ce78b3cea725992a0ce6f5eea0bf0bcdd4
Author: picoCTF{@sk_th3_1nt3rn_81e716ff} <ops@picoctf.com>
Date:   Tue Mar 12 00:07:15 2024 +0000

    optimize file size of prod code

diff --git a/message.py b/message.py
index 7df869a..326544a 100644
--- a/message.py
+++ b/message.py
@@ -1 +1 @@
-print("Hello, World!")
+print("Hello, World!"

commit 3ce5c692e2f9682a866c59ac1aeae38d35d19771
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:15 2024 +0000

    create top secret project

diff --git a/message.py b/message.py
new file mode 100644
index 0000000..7df869a
--- /dev/null
+++ b/message.py
@@ -0,0 +1 @@
+print("Hello, World!")
```

El autor que rompe el código es donde esta la bandera por lo cual es
```
	picoCTF{@sk_th3_1nt3rn_81e716ff}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/




