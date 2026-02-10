## Description
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is **bandit.labs.overthewire.org**, on port 2220. The username is **bandit0** and the password is **bandit0**. Once logged in, go to the [Level 1](https://overthewire.org/wargames/bandit/bandit1.html) page to find out how to beat Level 1.
## Solución 
Conectarme al servidor de **`bandit.labs.overthewire.org`** mediante SSH, para esto debemos de hacer el comando de
```
	ssh -p port_number user@IP
```

Remplazando el puerto, usuario y dirección con los siguientes datos:
- **port_number:** 2220
- **user:** bandit0
- **IP:** **bandit.labs.overthewire.org**

```
	ssh -p 2220 bandit0@bandit.labs.overthewire.org
```

Para acceder debemos ingresar la contraseña **bandit0** 

- Una vez iniciada la sesión, ve a la página de Level 0 → Level 1 Nivel 1 para descubrir cómo superarlo.
## Notas 

## Referencias
-  [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)

