
## Description
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)
Start your instance to see connection details.
`ssh -p 56954 ctf-player@saturn.picoctf.net`
The password is `af86add3`
## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Ingresamos al servicio con SSH y los datos que nos porporcionan
```
	ssh -p 56954 ctf-player@saturn.picoctf.net
```

SI probamos usar `ls` o algún comando nos estará cambiando el comando por lo que vamos a hacer diferentes formas de escribir comandos sin hacerlo
```
Special$ ${IFS}
	${IFS} 
Special$ $(/bin/ls)
	$(/bin/ls) 
	sh: 1: blargh: not found
Special$ '/bin/ls'
	'/bin/ls' 
	blargh
Special$ $0
	I 
	sh: 1: I: not found
Special$ ls
	Is 
	sh: 1: Is: not found
Special$ bash
	Why go back to an inferior shell?
Special$ sh
	Why go back to an inferior shell?
```

En estos retos también podemos probar `*` para ver si hay algo raro
```
Special$ *
* 
sh: 1: blargh: not found
Special$ */*
*/* 
sh: 1: blargh/flag.txt: Permission denied
Special$ * *         
* * 
```

en la parte de `*/*` nos muestra que no podemos acceder a `blargh/flag.txt` pero ya encontramos el archivo, ahora intentamos acceder con algunos comandos
```
Special$ ?at blargh/flag.txt
At blargh/flag.txt 
sh: 1: At: not found
Special$ ??t blargh/flag.txt             
It blargh/flag.txt 
sh: 1: It: not found
Special$ < blargh/flag.txt
< blargh/flag.txt 
```


Ahora probamos los comandos juntos con `${}` y usarlo con `${parameter=cat < blargh/flag.txt}`
```
Special$ ${parameter=cat < blargh/flag.txt} 
${parameter=cat < blargh/flag.txt} 
cat: '<': No such file or directory
picoCTF{5p311ch3ck_15_7h3_w0r57_6a2763f6}
```

Este si nos mostro la bandera
```
	picoCTF{5p311ch3ck_15_7h3_w0r57_6a2763f6}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/
