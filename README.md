gnost
=====

Herramienta para clonar particiones EXT, NTFS, FAT

### USO

#### Particiones NTFS

Necesitarás otra partición para guardar y respaldar tus archivos de imágen, preferentemente, deberían tener formato
ext2 y el lugar más seguro es una unidad usb externa, sin embargo su " Unidad de Copia de Respaldo" podría ser otra partición 
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
desde el directorio en Puppy  /usr/local/gnost y seleccione # 2. Tenga mucho cuidado especificar
la fuente correcta y partición de destino. Si lo hace al revés destruirá su Windows!

Aunque Windows se suele instalar en la primera partición de una unidad, Gnost puede moverlo a 
una partición diferente. Entonces, tendrá que editar el archivo c:\boot.ini y actualizar los números de partición.

Continuara...


