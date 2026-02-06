
## Description
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to fickle-tempest.picoctf.net 61241.

## Solución 

- Usar la terminal de WebShell que esta en picoCTF
- Crear un archivo del servicio encontrado con el comando de ` nc fickle-tempest.picoctf.net 51079 > salida.txt `
- Abrir el archivo para encontrar la bandera con el comando de ` grep "picoCTF" salida.txt`


```
  picoCTF{digital_plumb3r_1eBfC512}
```

## Notas 


## Referencias





