
## Description
Using a Secure Shell (SSH) is going to be pretty important.Can you `ssh` as `ctf-player` to `titan.picoctf.net` at port `54630` to get the flag?You'll also need the password `6dd28e9b`. If asked, accept the fingerprint with `yes`.If your device doesn't have a shell, you can use: [https://webshell.picoctf.org](https://webshell.picoctf.org/)If you're not sure what a shell is, check out our Primer: [https://primer.picoctf.com/#_the_shell](https://primer.picoctf.com/#_the_shell)

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Ingresamos al servicio con SSH y los datos que nos porporcionan
```
	ssh ctf-player@titan.picoctf.net -p 54630 
```

Al ingresar la contraseña que nos dieron, nos mostrara la bandera en la terminal
```
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_5d09a462}
Connection to titan.picoctf.net closed.
```

Una ves completado el reto nos dara la bandera
```
picoCTF{s3cur3_c0nn3ct10n_5d09a462}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/
