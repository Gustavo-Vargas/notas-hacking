
## Description
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/161/challenge.zip)

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Descargamos el .zip que nos dan y lo descomprimimos para saber que pista encontramos
```
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c_titan/161/challenge.zip
user-picoctf@webshell:~$ ls
challenge.zip
user-picoctf@webshell:~$ unzip challenge.zip 
```

Entramos a la carpeta que se descomprimió y leemos el mensaje para ver que pista nos deja
```
user-picoctf@webshell:~$ cd drop-in/
user-picoctf@webshell:~/drop-in$ ls
message.txt
user-picoctf@webshell:~/drop-in$ cat message.txt 
This is what I was working on, but I'd need to look at my commit history to know why...gushaki-picoctf@webshell:~/drop-in$ 
```

Hacemos un `git log` para ver el historial y ver si existe alguna nota
```
commit 10228f3d6437701ef5aaac04213757031f30ebec (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:24 2024 +0000

    picoCTF{t1m3m@ch1n3_8defe16a}
(END)
```

Si encontramos un archivo y hacemos un `git show HEAD`
```
commit 10228f3d6437701ef5aaac04213757031f30ebec (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:24 2024 +0000

    picoCTF{t1m3m@ch1n3_8defe16a}

diff --git a/message.txt b/message.txt
new file mode 100644
index 0000000..4324621
--- /dev/null
+++ b/message.txt
@@ -0,0 +1 @@
+This is what I was working on, but I'd need to look at my commit history to know why...
\ No newline at end of file
```

Este nos mostro la bandera
```
	picoCTF{t1m3m@ch1n3_8defe16a}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/




