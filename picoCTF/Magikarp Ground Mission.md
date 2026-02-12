
## Description
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin.Login via `ssh` as `ctf-player` with the password, `8c606eb1` on the host `wily-courier.picoctf.net` and port `53868`.

#### Comandos 

| Comando                                      | Acción                     |
| -------------------------------------------- | -------------------------- |
| `ssh picoplayer@saturn.picoctf.net -p 52763` | Inicio con ssh al servicio |
| `ls`                                         | Lista los archivos         |


## Solución 

Para este reto necesitamos conectarnos mediante ssh con los datos que no están dando.
```
ssh ctf-player@wily-courier.picoctf.net -p 53868
```

Accedemos con la contraseña `8c606eb1` y listamos `ls`
```
ctf-player@pico-chall$ ls
	1of3.flag.txt  instructions-to-2of3.txt
```

Hago un `cat` para cada archivo y ver que tiene
```
ctf-player@pico-chall$ cat 1of3.flag.txt 
	picoCTF{xxsh_
ctf-player@pico-chall$ cat instructions-to-2of3.txt 
	Next, go to the root of all things, more succinctly `/`
```

Tenemos la primera parte de la bandera y el otro nos dice que vayamos a la ruta /
```
ctf-player@pico-chall$ cd /
ctf-player@pico-chall$ ls
2of3.flag.txt  boot       dev  home                      lib    media  opt   root  sbin  sys  usr
bin            challenge  etc  instructions-to-3of3.txt  lib64  mnt    proc  run   srv   tmp  var
```

Nos muestra los archivos y el que dice  2of3.flag.txt contiene la segunda parte de la bandera
```
ctf-player@pico-chall$ cat 2of3.flag.txt 
0ut_0f_//4t3r_
```

Después hacemos un `cat` al archivo de `instructions-to-3of3.txt` para saber que hacer
```
ctf-player@pico-chall$ cat instructions-to-3of3.txt 
	Lastly, ctf-player, go home... more succinctly `~`
```

Ahora vamos al directorio home y hacemos un `ls`
```
ctf-player@pico-chall$ ls
ctf-player
```

Entramos al directorio `ctf-player` y hacemos un `ls`
```
ctf-player@pico-chall$ cd ctf-player/
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
```

Hacemos un cat en `3of3.flag.txt` que es la ultima parte de la bandera
```
ctf-player@pico-chall$ cat 3of3.flag.txt 
0b24fc4f}
```


Para al final completar todas las partes de la bandera
```
picoCTF{xxsh_0ut_0f_//4t3r_0b24fc4f}
```

## Notas 

## Referencias
- https://play.picoctf.org/practice?page=1&search=Magikarp%20Ground%20Mission