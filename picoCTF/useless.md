
## Description
There's an interesting script in the user's home directoryThe work computer is running SSH. We've been given a script which performs some basic calculations, explore the script and find a flag.

```
Hostname: saturn.picoctf.net
Port:     52763
Username: picoplayer
Password: password
```

#### Comandos 

| Comando                                      | Acción                     |
| -------------------------------------------- | -------------------------- |
| `ssh picoplayer@saturn.picoctf.net -p 52763` | Inicio con ssh al servicio |
| `man`                                        | ayuda ampliada             |

## Solución 

Para este reto nos dan algunos parámetros para acceder a un servicio mediante SSH, por lo que vamos a hacer el siguiente comando para acceder a el. Nos pedirá la contraseña la cual usaremos la que nos proporcionaron `password`

```
user-picoctf@webshell:~$ ssh picoplayer@saturn.picoctf.net -p 52763
The authenticity of host '[saturn.picoctf.net]:52763 ([13.59.203.175]:52763)' can't be established.
ED25519 key fingerprint is SHA256:DiJcS90U9QussLS8HLR6l6BGJb5eCA0vRmA18IvDvw8.
This key is not known by any other names
```

Hacemos un `ls` para ver que archivo tenemos
```
picoplayer@challenge:~$ ls
	useless
```

Leemos el archivo con `cat` para ver que tiene
```
picoplayer@challenge:~$ cat useless
#!/bin/bash
# Basic mathematical operations via command-line arguments

if [ $# != 3 ]
then
  echo "Read the code first"
else
        if [[ "$1" == "add" ]]
        then 
          sum=$(( $2 + $3 ))
          echo "The Sum is: $sum"  

        elif [[ "$1" == "sub" ]]
        then 
          sub=$(( $2 - $3 ))
          echo "The Substract is: $sub" 

        elif [[ "$1" == "div" ]]
        then 
          div=$(( $2 / $3 ))
          echo "The quotient is: $div" 

        elif [[ "$1" == "mul" ]]
        then
          mul=$(( $2 * $3 ))
          echo "The product is: $mul" 

        else
          echo "Read the manual"
         
        fi
fi
```

Vemos texto que nos pueden ayudar a entender que hacer
```
 echo "Read the code first"
 echo "Read the manual"
```

En este caso vamos a aplicar el comando de `man` ya que dice que leamos el manual
```
picoplayer@challenge:~$ man useless

useless
     useless, -- This is a simple calculator script

SYNOPSIS
     useless, [add sub mul div] number1 number2

DESCRIPTION
     Use the useless, macro to make simple calulations like addition,subtraction,
     multiplication and division.

Examples
     ./useless add 1 2
       This will add 1 and 2 and return 3

     ./useless mul 2 3
       This will return 6 as a product of 2 and 3

     ./useless div 6 3
       This will return 2 as a quotient of 6 and 3

     ./useless sub 6 5
       This will return 1 as a remainder of substraction of 5 from 6

Authors
     This script was designed and developed by Cylab Africa

     picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_3823}
```

Al final nos muestra la bandera para completar el desafio
```
picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_3823}
```

## Notas 

## Referencias
-  https://play.picoctf.org/practice/challenge/37?page=1&search=strings%20it
