## Description
The password for the next level is stored in **/etc/bandit_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Look at the commands that logged you into previous bandit levels, and find out how to use the key for this level.
#### Comandos 

## Solución 

Iniciamos sesión con `bandit13` y la contraseña que nos dio el nivel `Level 12 → Level 13`.

Hacemos un listado con `ls` para ver que archivo tenemos 
```
bandit13@bandit:~$ ls
sshkey.private
```

Descargamos el archivo SSH para poder acceder a bandit14, para esto necesitamos salir del servicio de bandit13 y ejecutar
```
scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .
```

- `scp`  -> Copia archivos desde un servidor remoto.
-  `-P 2220`  -> Puerto SSH de Bandit.
-  `bandit13@bandit.labs.overthewire.org:sshkey.private`  -> Archivo que quieres descargar.
-  `.`  -> Lo guarda en tu carpeta actual.

Ahora nos conectamos con la clave ssh
```
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
```

Una ves adentro navegamos a donde esta la contraseña del usuario `bandit14` y usamos `cat` para que muestre el texto del archivo
```
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)




