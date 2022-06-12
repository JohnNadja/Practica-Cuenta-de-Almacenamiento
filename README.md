# Práctica sobre la creación y uso de una *Cuenta de Almacenamiento* de Azure y sus servicios que provee para la gestión de datos y almacenamiento.

![storage-acc-icon](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-acc-icon.png)

## Índice

### [Introducción](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#introducci%C3%B3n-1) 
### [Requisitos](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#requisitos-1)
### [Práctica Blob Storage](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#pr%C3%A1ctica-blob-storage-1)
### [Práctica File Storage](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#pr%C3%A1ctica-file-storage-1) 
### [Práctica Queue Storage](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#pr%C3%A1ctica-queue-storage-1)
### [Práctica Table Storage](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#pr%C3%A1ctica-table-storage-1)


### Introducción
Una *Cuenta de Almacenamiento* es una cuenta de Azure que provee una plataforma de almacenamiento para contener todos los objetos de los demás servicios. Por como se menciona es un servicio de tipo [IaaS](https://azure.microsoft.com/es-mx/overview/what-is-iaas/#overview), además de que proporciona seguridad, alta disponibilidad, durabilidad y escalabilidad. Todo esto gracias a [*Azure Storage*](https://docs.microsoft.com/es-mx/azure/storage/) Dicho esto, en esta práctica se realizará la creación y uso de los servicios de:
- Blob Storage (Almacenamiento de Blobs)
- File Storage (Almacenamiento de Archivos)
- Queue Storage (Almacenamiento de Colas)
- Table Storage (Almacenamiento de Tablas)

Para fines más sencillos, se utilizará la Cuenta de Almacenamiento para poder realizar cada uno de los servicios dentro de ésta. Si aún no se ésta familiarizado con los servicios de Azure Storage, se puede consultar algunos temas de los que se tendrá en cuenta durante las prácticas.

#### Blob Storage
![storage-blob](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-blob.png)
Es un servicio tipo de servicio [IaaS](https://azure.microsoft.com/es-mx/overview/what-is-iaas/#overview) que puede almacenar  y compartir cualquier objeto (archivo) con un máximo de **8 Terabytes** de las máquinas virtuales. Tmabién permite guardar bases de datos (*pro tip*: este servicio es bueno para el respaldo de bases de datos). Usualmente su uso es para realizar *Streaming de video* y/o *audio* ya sea con alguna página web o acceso desde enlaces directos. Para más información de este servicio, se puede consultar el siguiente [enlace]()

#### File Storage
![storage-files](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-files.png)
Es un servicio [IaaS](https://azure.microsoft.com/es-mx/overview/what-is-iaas/#overview) para únicamente almacenar archivos pequeños, privados; monitorear su acceso y compartición desde una nube local a [Azure](https://azure.microsoft.com/es-mx/). Estos archivos se pueden acceder desde las máquinas virtuales de Azure

#### Disk Storage
![storage-disk](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-disk.png)
Es un disco duro (sea HDD o SSD) virtual que se guarda en una máquina virtual de Azure (*Dato curioso: las máquinas virtuales de Azure cuentan con 2 discos duros; uno para su Sistema operativo y otro para el almacenamiento de datos*). Más información en este [*enlace*](https://azure.microsoft.com/es-mx/services/storage/disks/).

#### Queue Storage
![storage-queue](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-queue.png)
Es un servicio [IaaS](https://azure.microsoft.com/es-mx/overview/what-is-iaas/#overview) que puede almacenar y compartir mensajes (de hasta 64kb) entre máquinas virtuales de Azure. Los mensajes son objetos de tipo *String* y se pueden enviar desde una máquina virtual a otra. Incluso se puede hacer un servidor local para *enfilar* dichos mensajes y procesarlos con alguna API , IoT, etc. Para más información de este servicio, se puede consultar el siguiente [*enlace*](https://docs.microsoft.com/es-mx/azure/storage/queues/storage-queues-introduction).

#### Table Storage
![storage-table](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-table.png)
Es un servicio [IaaS](https://azure.microsoft.com/es-mx/overview/what-is-iaas/#overview) que puede almacenar y compartir tablas de datos ***NoSQL estructurados*** en la nube, proporcionando un almacén de claves/atributos con un diseño sin esquema entre máquinas virtuales de Azure. Las tablas son objetos de tipo *JSON* y se pueden enviar desde una máquina virtual a otra. Para más información de este servicio, se puede consultar el siguiente [*enlace*](https://docs.microsoft.com/es-mx/azure/storage/tables/storage-tables-introduction).

-------
### Requisitos
 - Tener una cuenta de Azure para realizar la práctica en su [*Portal*](https://portal.azure.com/#home) (si aún no se cuenta con alguna, se puede hacer el registro en el siguiente [*enlace*](https://azure.microsoft.com/es-mx/free/)). 
 - Contar con una suscripción activa de Azure para poder realizar la práctica (en el enlace anterior se muestra como se puede hacer).


-------
### Práctica Blob Storage
![storage-blob](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-blob.png)
El servicio de Blob Storage está implícito ya que está integrado al servicio de Cuenta de almacenamiento. 
Contando con los rquerimientos anteriores, se procede a seguir las siguientes instrucciones: 
###### <sup>1
1. Buscar dentro del Portal de Azure el servicio de *Cuenta de Almacenamiento* y creamos una con los siguientes parámetros:
    - Datos básicos:
        | Parámetro | Valor |
        | ---------- | ----- |
        | Grupo de Recursos | Seleccionamos el grupo de recursos al que se le asignará la cuenta de almacenamiento. En caso de no tener un grupo de recursos, se crea uno en el apartado *Crear nuevo*|
        | Nombre de la cuenta de almacenamiento | Ingresamos un nombre de la cuenta de almacenamiento.|
        | Región | Buscamos la región más cercana posible. ***Sugerencia***: de preferencia se deberá mantener la región para las próximas prácticas.|
        | Rendimiento | Hay 2 opciones: ***Estándar*** (el rendimiento más bajo y que no requiera alta demanda) o ***Premium*** (el rendimiento más alto y que provee menor latencia en la disposición de carga, consulta y descarga de objetos/archivos). Para ésta ocasión será **Estándar**.|
        | Redundancia | Existen varias opciones: ***LRS*** (redundancia local o en el mismo servidor), ***GRS*** (redundancia en otra región), ***ZRS*** (redundancia en una [*zona de disponibilidad*](https://docs.microsoft.com/es-mx/azure/availability-zones/az-overview#availability-zones). ésta suele ser la más rápida para latencias bajas), y ***GZRS*** (redundancia en otra región y con [*zona de disponibilidad*](https://docs.microsoft.com/es-mx/azure/availability-zones/az-overview#availability-zones)) Para ésta ocasión será **LRS**. (nota: como se mencionan en ese orden, va desde más barato a más caro)|

    - Redes, aquí sólo nos importa por el momento:
        | Parámetro | Valor |
        | ---------- | ----- |
        | Acceso de red | Seleccionamos la opción **Habilitar el acceso público desde todas las redes**.|
        | Preferencia de enrutamiento | Seleccionamos la opción **Enrutamiento de red de Microsoft**.|
    
        - Pulsamos el botón de **Revisa y crear** para confirmar que todo esté correcto.
        ![storage-acc1]() 
        - Pulsamos el botón de *Crear* y esperamos a que se cree la cuenta de almacenamiento (se notificará cuando esté listo).
        - Ingresamos al recurso recién creado (ya sea en la misma ventana o en la ventana de *Inicio* de Azure).

2. Para encontrar el servicio de *Blob Storage* en la cuenta de almacenamiento, se buscará en el panel izquierdo el botón ***Contenedores***.Se encuentra en el apartado **Almacenamiento de datos**.
![buscar-contenedor](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/buscar-contenedor.gif)

3. Se requiere un nuevo contendor para almacenar los datos de la práctica. Se agrega uno y se coloca de parámetros:
    | Parámetro | Valor |
    | ---------- | ----- |
    | Nombre del contenedor | Ingresamos el nombre del contenedor.|
    | Tipo de acceso público | Seleccionamos la opción **Contenedor** (*acceso de lecura anónimo para conetenedores y blobs*) para que todos en el mundo puedan ver este contenedor |
        
    - Pulsamos el botón de *Crear* y esperamos a que se cree el contenedor.
    ![storage-cont1](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-cont1.gif)
    
4. Se ingresa al contenedor recién creado y se puede subir cualquier archivo desde el ordenador:
    - Seleccionamos el botón de **Cargar** y buscamos el archivo que se quiere subir. Se abrirá el **Explorador de Archivos** del ordenador. 
    - Aceptamos la subida de dicho archivo que requerimos con el botón **Cargar** del panel derecho.
    ![storage-subir](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-subir.gif)
    - Al terminar la subida, se puede acceder a la URL del archivo accediendo a éste y copiando dicha URL en el panel dereho correspondiente.
    ![storage-url](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-url.gif)
    - Si se quiere eliminar el archivo, se debe hacer *clic derecho* en él y seleccionar la opción **Eliminar** (marcamos la casilla *Eliminar también [instantáneas](https://docs.microsoft.com/es-es/azure/storage/blobs/snapshots-overview) del blob* si no queremos que almacene *una versión de sólo lectura* del archivo a eliminar).
    ![storage-eliminar](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-eliminar.gif)

5. [Extra] Se puede crear un contenedor para sitio web. Para ello se debe buscar en el panel derecho el botón ***Sitio web estático***. Se encuentra en el apartado **Administración de datos**. Se habilita y se escribe el *nombre del documento de ínidice* y se pulsa el botón de **Guardar**. Cabe recalcar que, en este caso, el contenedor se creará automáticamente (tendrá de nombre **$web**); pero es más largo el proceso de subida de archivos ya que es subir un archivo a la vez.
![storage-sitio](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-sitio.gif)


[⚠](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#importante)
######<sub>[Volver al índice](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#%C3%ADndice)<sub>


----
### Práctica File Storage
![storage-files](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-files.png)
1. Se requiere crear una cuenta de almacenamiento. Se puede realizar únicamente con el [paso 1](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#1) de la práctica de *Blob Storage* o bien, reutilizar la misma *cuenta de almacenamiento*.
2. Para encontrar el servicio de *File Storage* en la cuenta de almacenamiento, se buscará en el panel izquierdo el botón ***Recursos compartidos de archivos***.Se encuentra en el apartado **Almacenamiento de datos**.
![buscar-fileStorage](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/buscar-fileStorage.gif)
    - Se pulsa el botón de **+ Recurso compartido de archivos** y aparece un panel del lado derecho que deberá tener los siguientes datos:
        | Parámetro | Valor |
        | ---------- | ----- |
        | Nombre | Ingresamos el nombre del archivo a subir.|
        | Nivel | Dependiendo de lo que se requiere, será la opción adecuada. Para fines sencillos, seleccionamos la opción **Transacción optimizada**.|

        - Pulsamos el botón de *Crear* y esperamos a que se cree el archivo.
        ![file-new-FS](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/file-new-FS.gif)

3. Se ingresa al archivo recién creado y se puede subir cualquier archivo pequeño (como un PDF) desde el ordenador:
    - Seleccionamos el botón de **Cargar** y buscamos el archivo que se quiere subir. Se abrirá el **Explorador de Archivos** del ordenador. 
    - Aceptamos la subida de dicho archivo que requerimos con el botón **Cargar** del panel derecho.
    ![file-subir](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/file-subir.gif)

4. Para compartirlo, se debe pulsar el botón de **Conectar** y aparecerá un nuevo panel a la derecha.
    - Si quieremos compartirlo, usaremos el comando que nos ofrecen y lo pegamos en una ventana de PowerShell (sea en una máquina virtual o en nuestro ordenador).
    ![file-compartir](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/file-compartir.gif)

5. Si queremos crear un directorio, se debe pulsar el botón de **Agregar directorio** y aparecerá un nuevo panel para agregar el nombre de éste.
![file-directorio](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/file-directorio.gif)

5. Para eliminar el archivo (o directorio), se debe hacer *clic derecho* en él y seleccionar la opción **Eliminar**.

[⚠](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#importante)
###### <sub>[Volver al índice](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#%C3%ADndice)<sub>

-----

### Práctica Queue Storage
![storage-queue](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-queue.png)
1. Se requiere crear una cuenta de almacenamiento. Se puede realizar únicamente con el [paso 1](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#1) de la práctica de *Blob Storage* o bien, reutilizar la misma *cuenta de almacenamiento*.
2. Para encontrar el servicio de *Queue Storage* en la cuenta de almacenamiento, se buscará en el panel izquierdo el botón ***Colas***.Se encuentra en el apartado **Almacenamiento de datos**.
![buscar-queue](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/buscar-queue.gif)
    - Se pulsa el botón de **+ Cola** y aparece un panel al que se le asignará un nuevo nombre. Pulsamos el botón de **Aceptar** y esperamos a que se cree la cola.
    - Accedemos a la cola y seleccionamos el botón de **Agregar mensaje** con el texto del mensaje que queremos enviar, además de configurar el tiempo de expiración (o incluso marcar la casilla para que nunca expire).
    ![queue-new](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/queue-new.gif)
3. Para elminar el mensaje o la cola, se pulsa el botón correspondiente que se muestra en esa ventana.	


[⚠](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#importante)

###### <sub>[Volver al índice](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#%C3%ADndice)<sub>
----

### Práctica Table Storage
![storage-table](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/storage-table.png)
1. Se requiere crear una cuenta de almacenamiento. Se puede realizar únicamente con el [paso 1](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#1) de la práctica de *Blob Storage* o bien, reutilizar la misma *cuenta de almacenamiento*.
2. Para encontrar el servicio de *Queue Storage* en la cuenta de almacenamiento, se buscará en el panel derecho el botón ***Tablas***.Se encuentra en el apartado **Almacenamiento de datos**.
![buscar-tableStorage](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/buscar-tableStorage.gif)
    - Se pulsa el botón de **+ Tabla** y aparece un panel al que se le asignará un nuevo nombre. Pulsamos el botón de **Aceptar** y esperamos a que se cree la tabla.
    - Para editarla se busca en el panel izquierdo el botón de **Explorador de almacenamiento** y se pulsa para encontrar las tablas.
    - Seleccionamos nuestra tabla para después pulsar el botón de **+ Agregar entidad**. Aparecerá un panel a la derecha.
    - Podemos escribir lo siguiente:
        | Parámetro | Valor |
        | ---------- | ----- |
        | Nombre de propiedad | se asigna un nombre de la entidad.|
        | Tipo | seleccionamos el tipo de dato que queremos que sea esa propiedad.|
        | Valor | colocamos algún texto para mantener el valor de la propiedad|

    - Pulsamos el botón de *Insertar* y ahora se tiene la nueva tabla editada.
    ![table-new](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/table-new.gif)

3. Para eliminar la tabla, se regresa al panel izquierdo y seleccionamos la tabla a eliminar.
![table-delete](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento/blob/main/images/table-delete.gif) 

[⚠](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#importante)
###### <sub>[Volver al índice](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#%C3%ADndice)<sub>


#### Listo, ahora se conocen varios de los servicios que se pueden realizar gracias a una ***Cuenta de Almacenamiento*** en Azure.

----
# **⚠Importante⚠** 
### Recordar eliminar el grupo de recursos que se creó en Azure para evitar costos extras no deseados en caso de no ocupar el servicio.
Se puede hacer desde el panel de Azure en inicio y buscando el tipo de recurso que se llama **Grupo de Recursos**.
######<sub>[Volver al índice](https://github.com/JohnNadja/Practica-Cuenta-de-Almacenamiento#%C3%ADndice)<sub>

## Hasta aquí la finalización de la práctica.

