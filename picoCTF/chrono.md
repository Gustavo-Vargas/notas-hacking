
## Description
How to automate tasks to run at intervals on linux servers?
Use ssh to connect to this server:
- Server: saturn.picoctf.net
- Port: 57211
- Username: picoplayer 
- Password: bLgSMmbY6X

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Ingresamos al servicio con SSH y los datos que nos porporcionan
```
	ssh -p 57211 picoplayer@saturn.picoctf.net
```

Dentro del usuario debemos de buscar algo relacionado con `cron` para esto debemos de saber donde se configura:
- **crontab -l** → lista la crontab del usuario actual (ya lo hiciste).
- **/etc/crontab** → crontab del sistema (común en documentación y retos)
- **/etc/cron.d/ →** archivos adicionales de cron (cada archivo = posibles tareas).
- **/etc/cron.hourly/, /etc/cron.daily/** → scripts que se ejecutan cada hora/día.

Probamos con ` crontab -l `
```
picoplayer@challenge:~$ crontab -l
no crontab for picoplayer
```

Como no nos muestra nada, vamos a porbar con cat /etc/crontab
```
picoplayer@challenge:~$ cat /etc/crontab
	# picoCTF{Sch3DUL7NG_T45K3_L1NUX_1b4d8744}
```

Este si nos mostro la bandera
```
	picoCTF{Sch3DUL7NG_T45K3_L1NUX_1b4d8744}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/
