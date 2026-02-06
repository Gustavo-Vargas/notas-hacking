
# Referencia de comandos de Linux

## 1. Sistema de archivos

![[Pasted image 20260205110708.png]]

| Directorio | Contenido                                               |
| ---------- | ------------------------------------------------------- |
| `/`        | Raíz del sistema                                        |
| `/root`    | Directorio home del usuario root                        |
| `/bin`     | Donde residen los archivos binarios de las aplicaciones |
| `/boot`    | Archivos de arranque y kernel (grub)                    |
| `/dev`     | Dispositivos de hardware (como archivos)                |
| `/etc`     | Archivos de configuración                               |
| `/home`    | Directorios de usuarios                                 |
| `/lib`     | Donde se encuentran las librerias                       |
| `/media`   | Puntos de montaje (CD, USB)                             |
| `/mnt`     | Otros sistemas de archivos montados                     |
| `/opt`     | Software extra y de terceros                            |
| `/sbin`    | Binarios de sistema y administración                    |
| `/tmp`     | Temporal (se limpia al reiniciar)                       |
| `/usr`     | Programas, librerías y documentación de usuario         |
| `/var`     | Archivos variables y temporales                         |

---

## 2. Accesos rápidos en terminal

| Teclas                          | Acción                               |
| ------------------------------- | ------------------------------------ |
| `Ctrl + Shift + T`              | Nueva pestaña                        |
| `Ctrl + +` / `Ctrl + -`         | Aumentar / reducir fuente            |
| `Ctrl + 0`                      | Tamaño de fuente por defecto         |
| `Ctrl + L`                      | Borrar pantalla                      |
| `Ctrl + A`                      | Cursor al inicio de la línea         |
| `Ctrl + E`                      | Cursor al final de la línea          |
| `Alt + F`                       | Cursor una palabra a la derecha      |
| `Alt + B`                       | Cursor una palabra a la izquierda    |
| `Ctrl + C`                      | Detener comando actual               |
| `Ctrl + Z`                      | Pausar comando (reanudar con `bg`)   |
| `Ctrl + D`                      | Salir de la sesión (como `exit`)     |
| `Ctrl + U`                      | Borrar del cursor al inicio de línea |
| `Ctrl + K`                      | Borrar del cursor al final de línea  |
| `Ctrl + W`                      | Borrar palabra a la izquierda        |
| `Esc + D`                       | Borrar palabra a la derecha          |
| `Ctrl + Shift + C`              | Copiar selección                     |
| `Ctrl + Shift + V`              | Pegar                                |
| `Tab`                           | Autocompletar                        |
| `Ctrl + R`                      | Buscar en historial                  |
| `!!`                            | Repetir último comando               |
| `Shift + PgUp` / `Shift + PgDn` | Scroll en la terminal                |
| `man comando`                   | Ayuda ampliada                       |
| `comando --help` / `comando -h` | Ayuda resumida                       |

---

## 3. Comandos sobre el sistema de archivos

| Comando | Acción |
|---------|--------|
| `ls` | Listar archivos |
| `ls -la` | Listar con formato largo e incluir ocultos |
| `cd dirname` | Cambiar de directorio |
| `cd -` | Ir al directorio anterior |
| `cd` | Ir al directorio home |
| `cd ..` | Subir al directorio padre |
| `cd /` | Ir al directorio raíz |
| `pwd` | Mostrar ruta actual |
| `mkdir dir` | Crear directorio |
| `rm file` | Borrar archivo |
| `rm -r dir` | Borrar directorio |
| `rm -f file` | Borrar archivo forzado |
| `rm -rf dir` | Borrar directorio forzado |
| `cp file1 file2` | Copiar archivo |
| `cp -r dir1 dir2` | Copiar directorio (crea dir2 si no existe) |
| `mv file1 file2` | Mover o renombrar |
| `touch file` | Crear o actualizar archivo |
| `ln -s file link` | Crear enlace simbólico |
| `cat > file` | Redirigir salida a archivo (Ctrl+D termina) |
| `cat file` | Mostrar contenido |
| `more file` | Mostrar por páginas |
| `less file` | Mostrar por páginas (navegable) |
| `head file` | Primeras 10 líneas |
| `tail file` | Últimas 10 líneas |
| `file file` | Tipo de archivo |
| `find file` | Buscar archivo |

---

## 4. Permisos sobre archivos

**Simbólicos:** `r` lectura, `w` escritura, `x` ejecución  
**Grupos:** Usuario | Grupo | Otros → `rwx rwx rwx`

**Octal:** Lectura=4, Escritura=2, Ejecución=1

| Modo | chmod |
|------|--------|
| rwx rwx rwx | `chmod 777 file` |
| rwx rwx r-x | `chmod 775 file` |
| rwx r-x r-x | `chmod 755 file` |
| rw- rw- r-- | `chmod 664 file` |
| rw- r-- r-- | `chmod 644 file` |

---

## 5. Información del sistema

| Comando | Acción |
|---------|--------|
| `date` | Fecha y hora actual |
| `cal` | Calendario del mes |
| `uptime` | Tiempo encendido del sistema |
| `w` | Quién está en línea |
| `whoami` | Usuario actual |
| `finger user` | Info del usuario |
| `uname -a` | Info del sistema |
| `uname -r` | Versión del kernel |
| `hostname` | Nombre del host |
| `cat /proc/cpuinfo` | Info de CPU |
| `cat /proc/meminfo` | Info de memoria |
| `df` | Uso de disco |
| `du` | Uso por directorios |
| `free` | Memoria y swap |
| `dmesg` | Mensajes del kernel |
| `lsusb -tv` | Dispositivos USB |
| `lspci -tv` | Dispositivos PCI |
| `locate recurso` | Buscar archivo/directorio |
| `updatedb` | Actualizar base de locate |
| `whereis app` | Ubicación de app |
| `which app` | Qué app se ejecuta por defecto |

---

## 6. Manejo de procesos

| Comando | Acción |
|---------|--------|
| `ps` | Procesos de la terminal |
| `ps -all` | Todos los procesos del usuario |
| `ps aux` | Todos los procesos del sistema |
| `proceso &` | Ejecutar en segundo plano |
| `kill pid` | Terminar proceso por PID |
| `kill -9 pid` | Terminar forzado |
| `killall proc` | Terminar todos los procesos llamados proc |
| `pkill proc` | Terminar proceso por nombre |
| `bg` | Listar trabajos en segundo plano |
| `fg` | Traer el más reciente al frente |
| `fg n` | Traer el trabajo n al frente |
| `top` | Gestor de procesos (Ctrl+C salir) |

