

## Description

Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/19/challenge.zip)

`ssh -p 49942 ctf-player@atlas.picoctf.net`Using the password `1db87a14`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!


## Solución 
- Usar la terminal de WebShell que esta en picoCTF

Descargamos el .zip que nos dan y lo descomprimimos para saber que pista encontramos
```
user-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c_atlas/19/challenge.zip
user-picoctf@webshell:~$ ls
challenge.zip
```

```
user-picoctf@webshell:~$ unzip challenge.zip 
Archive:  challenge.zip
   creating: home/ctf-player/drop-in/
  inflating: home/ctf-player/drop-in/guessing_game.sh  
user-picoctf@webshell:~$ ls
	challenge.zip  home
```


Para acceder al juego necesitamos conectarnos por SSH
```
user-picoctf@webshell:~$ ssh -p 49942 ctf-player@atlas.picoctf.net
```

debemos de atinar al valor random para que nos de la bandera
```
Congratulations! You guessed the correct number: 570
Here's your flag: picoCTF{g00d_gu355_1597707f}
Connection to atlas.picoctf.net closed.
```


Este si nos mostro la bandera
```
	picoCTF{g00d_gu355_1597707f}
```

## Notas 

## Referencias
-  https://gchq.github.io/CyberChef/




