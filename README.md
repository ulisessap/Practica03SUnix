# Practica03SUnix

# Asegurar el bootloader 

## Bootloader
El bootloader, o cargador de arranque, es un programa esencial en el proceso de inicio de una computadora. Su función principal es cargar el sistema operativo en la memoria del sistema y transferirle el control para que pueda comenzar a ejecutarse.

## Carga el kernel y el initrd en memoria:
El bootloader es el primer software que se ejecuta al iniciar una computadora. Su función principal es cargar el núcleo del sistema operativo (el kernel) y el disco inicial (initrd) en la memoria. El kernel es el componente central del sistema operativo que gestiona el hardware y proporciona servicios a las aplicaciones, mientras que el initrd es un sistema de archivos en memoria utilizado para preparar el entorno antes de que el sistema operativo principal se inicie.

## Establece parámetros de inicio en el kernel:
Antes de cargar el kernel, el bootloader puede establecer parámetros de inicio que configuran cómo se debe iniciar el sistema. Estos parámetros pueden influir en el comportamiento del kernel y del sistema operativo durante el arranque.

## Una vez cargado en memoria ejecuta el kernel y transfiere el control del equipo:
Después de cargar el kernel y el initrd en la memoria, el bootloader transfiere el control al kernel. En este punto, el kernel toma el control del proceso de arranque y comienza a inicializar el sistema operativo.

## Es posible cambiar los parámetros de inicio para manipular el sistema:
Los parámetros de inicio pueden modificarse para influir en cómo el kernel y el sistema operativo se comportan durante el arranque. Esto puede ser útil para solucionar problemas, hacer pruebas o cambiar configuraciones específicas.

# Shell de root desde el bootloader

Es posible obtener un shell de root modificando los parametros de inicio del kernel: Al modificar los parámetros de inicio del kernel desde el bootloader, puedes obtener acceso a una línea de comandos (shell) como usuario root. Esto es útil para realizar tareas administrativas, solucionar problemas o cambiar configuraciones sin necesidad de iniciar el sistema operativo normalmente.

# Instrucciones

Al iniciar nuestra maquina de debian, si presionamos e accederemos al menu de las entradas del grub.

![image](https://github.com/user-attachments/assets/778a9da0-2bfd-4c30-9c29-0347c3695868)

Le podemos decir al kernel que, en lugar de iniciar el sistema normalmente, cargue una shell /bin/sh. Este método se utiliza frecuentemente para entrar en un modo de recuperación o para realizar tareas de mantenimiento, ya que carga un entorno mínimo con acceso a la shell.
![image](https://github.com/user-attachments/assets/f04b56e2-bfcf-4e5d-bdb3-5bd1f0bb967a)

Y luego presionamos CTRl x

![image](https://github.com/user-attachments/assets/89cc5d95-8b29-48be-b832-4f59a25d20b4)

- mount:
El comando mount se utiliza para montar sistemas de archivos en Linux. Esto significa que se asocia un sistema de archivos con un punto de montaje en el árbol de directorios, lo que permite acceder a su contenido. Sin argumentos, mount muestra una lista de todos los sistemas de archivos montados en ese momento.

![image](https://github.com/user-attachments/assets/d9b87108-bc50-405c-9db8-9b3050f67344)

- mount -o remount,rw /:
Este comando vuelve a montar el sistema de archivos raíz / con permisos de lectura y escritura. Por defecto, algunos sistemas pueden arrancar con el sistema de archivos raíz montado en modo de solo lectura para realizar chequeos o reparaciones antes de permitir modificaciones. Este comando cambia ese estado a lectura-escritura (rw), lo que permite modificar archivos en el sistema de archivos raíz.

![image](https://github.com/user-attachments/assets/f6353da7-30b8-420f-9785-c47a32b23d3f)

- passwd
  
![image](https://github.com/user-attachments/assets/69953642-603b-45fd-8aed-d6b527fb02d2)

Ahora reiniciamos la maquina

Y para mas comodo, nos conectamos por ssh a la maquina 

Modificaremos opciones avanzadas, sudo nano /etc/grub.d/10_linux

Este archivo es parte de la configuración de GRUB (GRand Unified Bootloader) en sistemas Linux. Específicamente, el archivo 10_linux se encarga de detectar y generar entradas en el menú de GRUB para los sistemas operativos Linux instalados en la máquina. Cuando ejecutas sudo update-grub, el contenido de este archivo se utiliza para construir el archivo de configuración principal de GRUB.

![image](https://github.com/user-attachments/assets/aa876e43-1239-40a8-b490-9d00aba938ac)

Nos dirigimos a estas lienas 

![image](https://github.com/user-attachments/assets/c10ba963-fcda-4378-8957-54b5b88613f4)









