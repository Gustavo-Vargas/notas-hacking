
## Description
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337?
Connect with nc fickle-tempest.picoctf.net 59608.

## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Ingresamos al servicio en el puerto que nos habilitaron
```
	nc fickle-tempest.picoctf.net 59608
```

Nos pedirá que escribamos la palabra con los binarios que nos dan, vamos a CyberChef y hacer la transformación del binario a palabra
```
Please give the 01100011 01101000 01100001 01101001 01110010 as a word...
you have 45 seconds.....

Input:
	chair
```

Al ingresar correctamente nos dará dígitos en octal que debemos transformar a palabra
```
Please give me the  o164 o145 o163 o164 as a word.
Input:
	test
```

Por ultimo nos dará un numero en hexadecimal que debemos transformar a palabra
```
Please give me the 636f6e7461696e6572 as a word.
Input:
	container
```

Una ves completado el reto nos dara la bandera
```
You've beaten the challenge
	Flag: picoCTF{learning_about_converting_values_acdCcfCa}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/
