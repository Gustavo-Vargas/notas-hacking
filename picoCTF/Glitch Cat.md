
## Description
Our flag printing service has started glitching!`$ nc saturn.picoctf.net 56487`

## Solución 

- Usar la terminal de WebShell que esta en picoCTF
- Entrar al servicio de `nc saturn.picoctf.net 56487` que nos da ` 'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}' `
- Hacer el comando de ` python3 -c "print('picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}')" ` para que nos de la bandera


```
  picoCTF{gl17ch_m3_n07_bda68f75}
```

## Notas 

## Referencias

