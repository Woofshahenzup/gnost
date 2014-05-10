gnost
=====

Herramienta para clonar particiones EXT, NTFS, FAT

### USO

#### Indice
**[Particiones NTFS](#particiones-ntfs)** 

**[Particiones EXT](#particiones-ext)** 

**[Particiones FAT](#particiones-fat)** 

**[Paquetes](#paquetes)** 

#### Particiones NTFS

Necesitarás otra partición para guardar y respaldar tus archivos de imágen, preferentemente, deberían tener formato
ext2 y el lugar más seguro es una unidad usb externa, sin embargo su "Unidad de Copia de Respaldo" podría ser otra partición 
ext2 en el disco duro, tambien puede utilizar una partición NTFS como su unidad de copias de respaldo si su disco 
duro ya estaba formateado de esa manera (Sin embargo, esta alternativa no ha recibido pruebas extensivas.)

Vaya a la carpeta /usr/local/gnost y copie los dos archivos en su "Disco o unidad de respaldo". Si va a guardar los 
archivos de imagen en una subcarpeta, entonces copie los archivos Gnost allí.

Inicie el equipo con el liveCD o Usb en Ram de Puppy, conecte su unidad de copia de segurida y abra la partición 
que tiene asignada para hacer respaldos.

Haga clic en el script "gnostmenu", y seleccione el nº 1 en el menú. 

Lea las instrucciones iniciales. Seleccione el tipo de operación (crear o restaurar una imagen) y el nombre del 
archivo de imagen. Me gusta usar la extensión ".Gno" para mis archivos de imágenes NTFS. La imagen se 
guardará en la carpeta actual. 

Por lo general, utilizará Gnost para respaldar/restaurar una imagen en la misma partición de Windows. 
Pero es posible que con el tiempo, necesite actualizar su disco duro o reemplazar una unidad que falle. 
En ese caso, usted estará transfiriendo la imagen a una nueva unidad cuya geometría podría ser 
diferente de la original. Así que se requieren algunos pasos adicionales.

Antes de ejecutar Gnost, debe preparar la nueva unidad al hacer una partición NTFS y establecer el 
indicador de arranque (boot flag). Asegúrese de que la nueva partición es al menos tan grande como el original. 

Después que Gnost restaure la imagen, se ampliará el sistema de archivos NTFS para llenar la nueva 
partición, actualice el sector de arranque y escriba un nuevo MBR WinXP.

Si tiene Vista o Win7 y necesita el MBR correspondiente, ejecute el comando ms-sys incluido en el proyecto, de la siguiente
manera.

`ms-sys -i -w /dev/sda`   # Para Vista  
`ms-sys -7 -w /dev/sda`   # Para Win7

Si usted tiene la configuración adecuada de hardware, puede copiar toda la partición de Windows directamente 
desde la unidad antigua a la nueva, sin hacer un archivo de imagen. Ejecuta Gnost 
desde el directorio en Puppy  /usr/local/gnost y seleccione # 2. Tenga mucho cuidado de especificar
la fuente correcta y partición de destino. Si lo hace al revés destruirá su Windows!

Aunque Windows se suele instalar en la primera partición de una unidad, Gnost puede moverlo a 
una partición diferente. Entonces, tendrá que editar el archivo c:\boot.ini y actualizar los números de partición.

#### Particiones EXT

Si usted tiene una instalación Frugal básica, el procedimiento de copia es fácil, ya cuenta con los
archivos nucleo del LiveCD, por lo que sólo necesita realizar una copia de su Pupsave, sin embargo 
si usted tiene una instalación completa o tiene contenido fuera del Pupsave puede utilizar gnost en 
su lugar.

Usted necesitará una particion EXT independiente para contener los archivos de imagen de 
respaldo. El lugar más seguro es una unidad USB externa. Sin embargo su "Unidad de copia 
de seguridad" podría ser otra particion EXT en el mismo disco duro interno. Tambien puede 
utilizar una partición NTFS como su unidad de copia de seguridad, si su disco duro USB ya estaba 
formateado de esa manera. ( Sin embargo, esta alternativa no ha recibido pruebas extensivas ).

Vaya a la carpeta /usr/local/gnost y copie los dos archivos en su copia de seguridad. Si va a poner 
los archivos de imágen en una subcarpeta, copiar los archivos gnost ahi entonces.

Inicie el equipo en su LiveCD o Usb usando el prefijo "puppy pfix=ram" esto asegura que la partición 
Puppy esté desmontada.

Conecte su unidad USB y abra la particion de copia de seguridad.

Haga click en el script "gnostmenu" y seleccione # 3 en el menú.

Lea las instrucciones iniciales. Seleccione el tipo de operación ( Crear o restaurar una imágen ) 
y el nombre del archivo de imágen. Me gusta la extension ".egno" para mis archivos de 
imágen EXT. La imágen se guardará en la carpeta actual.

Gnost ejecutará una comprobación del sistema de archivos inicial de la partición origen.
Debido a que Puppy no siempre se cierra sin problemas, es posible que se le pregunte Si/No 
antes de continuar.

Por lo general, Utilizará Gnost para respaldar/restaurar una imágen en la misma partición 
de Puppy, pero es posible que con el tiempo desee mover Puppy en una Unidad o partición 
diferente. En este caso la transferencia será de la imagen a una nueva partición cuya 
geometría es diferente a la original. Asi que se van a requerir algunos pasos adicionales.

Antes de ejecutar Gnost, debe preparar la unidad, al hacer la partición EXT, asegurese de 
que la nueva partición es al menos tan grande como la original.

Despues que Gnost restaura la imagen, se ampliará el sistema de archivos EXT para llenar la 
nueva particíon.

Si usted tiene la configuración de hardware adecuada, puede copiar la partición Puppy 
directamente de la unidad antigua a la nueva sin hacer el archivo de imágen. Ejecutar 
Gnost de la carpeta en Puppy /usr/local/gnost y seleccione # 4. Tenga mucho cuidado 
de que especifica la fuente correcta y su partición destino. Hacerlo al revés puede 
destruir su Puppy!!.

Nota: Si mueve una partición Linux a una nueva ubicación, es posible que tenga que 
reinstalar su cargador de arranque GRUB para que se puede iniciar la unidad.

#### Particiones FAT 

Use el mismo procedimiento que usan las particones EXT.

 

