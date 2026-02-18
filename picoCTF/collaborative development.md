

## Description
I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/139/challenge.zip)

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Descargamos el .zip que nos dan y lo descomprimimos para saber que pista encontramos
```
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c_titan/178/challenge.zip
user-picoctf@webshell:~$ ls
	challenge.zip
user-picoctf@webshell:~$ unzip challenge.zip 
```

Necesitamos buscar el programa que imprime la flag y varias personas anadieron funcionalidades en ramas  o cambios.

Ingresamos a la carpeta y y hacemos un `ls` para ver que archivos encontramos
```
user-picoctf@webshell:~$ cd drop-in/
user-picoctf@webshell:~/drop-in$ ls
flag.py
```

Hacemos un `git branch -a` para ver cuales son las ramas que hay
```
  feature/part-1
  feature/part-2
  feature/part-3
* main
```

Ahora hay que ver que hay en cada rama con `git show feature/part-1` y nos sale los cambios
```
commit 8eea0627726fc363246015cb4c7e927e70286e87 (feature/part-1)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:54 2024 +0000

    add part 1

diff --git a/flag.py b/flag.py
index 77d6cec..6e17fb3 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,2 @@
 print("Printing the flag...")
+print("picoCTF{t3@mw0rk_", end='')
\ No newline at end of file
```

Ahora hay que ver que hay en cada rama con `git show feature/part-2` y nos sale los cambios
```
commit 05db9e274ff691e0f9fb492403b570629eb80aa9 (feature/part-2)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:54 2024 +0000

    add part 2

diff --git a/flag.py b/flag.py
index 77d6cec..7ab4e25 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,3 @@
 print("Printing the flag...")
+
+print("m@k3s_th3_dr3@m_", end='')
\ No newline at end of file
```

Ahora hay que ver que hay en cada rama con `git show feature/part-3` y nos sale los cambios
```

commit 655c7bfebe9c221369ab00ac7374d0d4bd4d62a9 (feature/part-3)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:54 2024 +0000

    add part 3

diff --git a/flag.py b/flag.py
index 77d6cec..4f136da 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,3 @@
 print("Printing the flag...")
+
+print("w0rk_6c06cec1}")
```

cada rama nos da una parte de la bandera, por lo que hacemos la union y nos da
```
	picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_6c06cec1}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/




