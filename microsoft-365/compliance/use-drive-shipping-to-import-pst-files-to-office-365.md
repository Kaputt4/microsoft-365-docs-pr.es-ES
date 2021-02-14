---
title: Usar el envío de unidades para importar los archivos PST de la organización
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
ms.custom: seo-marvel-apr2020
description: El administrador puede aprender a importar archivos PST en masa a buzones de Microsoft 365 copiando archivos PST en una unidad de disco duro y, a continuación, env a Microsoft.
ms.openlocfilehash: e94a59b19271af275f74a08355a017533f8ef45d
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127347"
---
# <a name="use-drive-shipping-to-import-your-organizations-pst-files"></a>Usar el envío de unidades para importar los archivos PST de la organización

**Este artículo está para administradores. ¿Está intentando importar archivos PST a su propio buzón? Vea [Importar correo electrónico, contactos y calendario desde un archivo .pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
Use el servicio de importación de Office 365 y el envío de unidades para importar archivos PST de forma masiva a los buzones de usuario. «Envío de unidades» significa que los archivos PST se copian en una unidad de disco duro y se envía la unidad a Microsoft de forma física. Cuando Microsoft recibe la unidad de disco duro, el personal del centro de datos copia los datos de la unidad de disco duro en un área de almacenamiento en la nube de Microsoft. A continuación, tiene la oportunidad de recortar los datos PST que se importan a los buzones de destino estableciendo filtros que controlan qué datos se importan. Después de iniciar el trabajo de importación, el servicio de importación importa los datos PST del área de almacenamiento a los buzones de usuario. El envío de unidades para importar archivos PST a buzones de usuario es una forma de migrar el correo electrónico de su organización a Office 365.
  
Estos son los pasos necesarios para usar el envío de unidades para importar archivos PST a buzones de Microsoft 365:
  
[Paso 1: Descargar la clave de almacenamiento seguro y la herramienta de importación de PST](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[Paso 2: Copiar los archivos PST en la unidad de disco duro](#step-2-copy-the-pst-files-to-the-hard-drive)

[Paso 3: Crear el archivo de asignación de importación de PST](#step-3-create-the-pst-import-mapping-file)

[Paso 4: crear un trabajo de importación de PST en Office 365](#step-4-create-a-pst-import-job-in-office-365)

[Paso 5: enviar la unidad de disco duro a Microsoft](#step-5-ship-the-hard-drive-to-microsoft)

[Paso 6: filtrar los datos e iniciar el trabajo de importación de PST](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> Debe realizar el paso 1 una vez para bajar la carga de la clave de almacenamiento seguro y la herramienta de importación. Después de realizar estos pasos, siga los pasos del 2 al 6 cada vez que desee enviar una unidad de disco duro a Microsoft. 
  
Para ver las preguntas más frecuentes sobre el uso del trasvase de unidades para importar archivos PST a Office 365, vea las preguntas más frecuentes sobre el uso del envío de unidades para [importar archivos PST.](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files) 
  
## <a name="before-you-import-pst-files"></a>Antes de importar archivos PST

- Debe tener asignado el rol importación y exportación de buzón de Exchange Online para importar archivos PST a los buzones de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Mailbox Import Export al grupo de roles Administración de la organización. También puede crear un grupo de roles, asignarle el rol Mailbox Import Export y agregarse a sí mismo como miembro. Para obtener más información, vea las secciones "Agregar un rol a un grupo de roles" o "Crear un grupo de roles" en [Administrar grupos de roles](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Además, para crear trabajos de importación en el Centro de seguridad y cumplimiento, debe cumplirse uno de estos requisitos:
    
  - Debe tener asignado el rol de los destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos de roles de administración de la organización y administración de destinatarios.
    
    O bien:
    
  - Necesita ser administrador global en su organización.
    
    > [!TIP]
    > Puede crear un nuevo grupo de roles en Exchange Online que está pensado específicamente para la importación de archivos PST a Office 365. Para obtener el nivel mínimo de privilegios necesarios para importar archivos PST, asigne los roles de importación y exportación de buzón y de destinatarios de correo al nuevo grupo de roles y, a continuación, agregue a los miembros. 
  
- Debe almacenar los archivos PST que desea copiar en una unidad de disco duro de un servidor de archivos o una carpeta compartida de la organización. En el paso 2, ejecute la herramienta de importación y exportación de Azure (WAImportExport.exe) que copia los archivos PST almacenados en este servidor de archivos o carpeta compartida en la unidad de disco duro.

- Es posible que los archivos PST de gran tamaño afecten al rendimiento del proceso de importación de PST. Por lo tanto, se recomienda que cada archivo PST que copie en la unidad de disco duro del paso 2 no sea superior a 20 GB.
    
- Solo se admiten unidades de estado sólido (SSD) de 2,5 pulgadas o discos duros internos SATA II/III de 2,5 o 3,5 pulgadas para su uso con el servicio de importación de Office 365. Puede usar discos duros de hasta 10 TB. Para los trabajos de importación, se procesará solo el primer volumen de datos del disco duro. El volumen de datos debe tener el formato NTFS. Al copiar datos en una unidad de disco duro, puedes adjuntarlos directamente mediante un conector SSD de 2,5 pulgadas o un conector SATA II/III de 2,5 pulgadas o 3,5 pulgadas, o bien puedes adjuntarlos externamente mediante un adaptador USB EXTERNO SSD de 2,5 pulgadas o 2,5 pulgadas o 3,5 pulgadas SATA II/III.
    
    > [!IMPORTANT]
    > El Servicio de importación de Office 365 no admite los discos duros externos con un adaptador USB integrado. Además, no se puede usar un disco que esté dentro de la carcasa de un disco duro externo. No envíe discos duros externos. 
  
- La unidad de disco duro a la que copie los archivos PST debe estar cifrada con BitLocker. La herramienta WAImportExport.exe, ejecutada en el paso 2, le ayudará a configurar BitLocker. También genera una clave de cifrado de BitLocker que el personal del centro de datos de Microsoft usa para acceder a la unidad para cargar los archivos PST en el área de Azure Storage en la nube de Microsoft.
    
- El envío de unidades está disponible a través de un Contrato Enterprise (EA) de Microsoft. El envío de unidades no está disponible mediante un Contrato de productos y servicios de Microsoft (MPSA).
    
- El costo de importar archivos PST a buzones de Microsoft 365 mediante el envío de unidades es de 2 USD por GB de datos. Por ejemplo, si envía una unidad de disco duro que contiene 1000 GB (1 TB) de archivos PST, el costo es 2000 USD. Puede colaborar con un asociado para abonar la cuota de importación. Para obtener información sobre cómo buscar un asociado, consulte [Buscar un asociado o distribuidor de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=785197).
    
- Usted o su organización debe tener una cuenta con FedEx o DHL. 
    
  - Las organizaciones de Estados Unidos, Brasil y Europa deben tener cuentas FedEx.
    
  - Las organizaciones de Asia oriental, el sudeste asiático, Japón, la República de Corea y Australia deben tener cuentas DHL.
    
    Microsoft usa (y cobra) esta cuenta para devolverte la unidad de disco duro.
    
- La unidad de disco duro que envíe a Microsoft puede cruzar las fronteras internacionales. En este caso, usted es responsable de garantizar que la unidad de disco duro y los datos que contiene se importen o exporten de acuerdo con las leyes aplicables. Antes de enviar una unidad de disco duro, póngase en contacto con sus asesores para comprobar que la unidad y los datos se puedan enviar de forma legal al centro de datos de Microsoft identificado. Esto ayuda a garantizar que llega a Microsoft de forma oportuna.
    
- Este procedimiento implica copiar y guardar una clave de almacenamiento seguro y una clave de cifrado de BitLocker. Asegúrese de tomar precauciones para proteger estas claves de la misma manera que protegería las contraseñas u otra información relacionada con la seguridad. Por ejemplo, puede guardarlas en un documento de Microsoft Word protegido por contraseña o en una unidad USB cifrada. Consulta la [sección Más información](#more-information) para ver un ejemplo de estas claves. 
    
- Después de importar los archivos PST a un buzón de Microsoft 365, la configuración de suspensión de retención del buzón se activada durante un período de tiempo indefinido. Esto significa que la directiva de retención asignada al buzón no se procesará hasta que desactive la espera de retención o establezca una fecha para desactivar la retención. ¿Por qué lo hacemos? Si los mensajes importados a un buzón son antiguos, es posible que se eliminen de forma permanente, ya que su período de retención ha caducado en función de la configuración de retención establecida para el buzón. Al colocar el buzón en espera de retención, el propietario del buzón tiene tiempo para administrar estos mensajes recién importados o usted tendrá tiempo para cambiar la configuración de retención del buzón. Vea la [sección Más información](#more-information) para obtener sugerencias sobre cómo administrar la suspensión de retención. 
    
- De forma predeterminada, el tamaño máximo de mensaje que puede recibir un buzón de Microsoft 365 es de 35 MB. Esto se debe a que el valor predeterminado de la propiedad *MaxReceiveSize* de un buzón está establecido en 35 MB. Pero el límite de tamaño máximo de recepción de mensajes en Microsoft 365 es de 150 MB. Por lo tanto, si importa un archivo PST que contiene un elemento superior a 35 MB, el servicio de importación de Office 365 cambiará automáticamente el valor de la propiedad *MaxReceiveSize* en el buzón de destino a 150 MB. Esto permite que se importen a buzones de usuario mensajes de hasta 150 MB. 
    
    > [!TIP]
    > Para identificar el tamaño de recepción de un buzón de correo, puede ejecutar este comando en PowerShell de Exchange Online: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`. 
  
- Puede importar archivos PST a un buzón inactivo de Office 365. Para ello, debe especificar el GUID del buzón inactivo en el parámetro `Mailbox` del archivo de asignación de importación de PST. Vea [el paso 3: Crear el archivo de asignación de importación de PST](#step-3-create-the-pst-import-mapping-file) para obtener más información. 
    
- En una implementación híbrida de Exchange, puede importar archivos PST a un buzón de archivo basado en la nube para un usuario cuyo buzón principal es local. Para ello, haga lo siguiente en el archivo de asignación de importación de PST:
    
  - Especifique la dirección de correo electrónico del buzón local del usuario en el parámetro `Mailbox`. 
    
  - Especifique el valor **TRUE** en el parámetro `IsArchive`. 
    
    Vea [el paso 3: Crear el archivo de asignación de importación de PST](#step-3-create-the-pst-import-mapping-file) para obtener más información. 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a>Paso 1: Descargar la clave de almacenamiento seguro y la herramienta de importación de PST

El primer paso es descargar la clave de almacenamiento seguro y la herramienta, y que se usa en el paso 2 para copiar archivos PST en la unidad de disco duro.
  
> [!IMPORTANT]
> Debe usar la herramienta de importación y exportación de Azure versión 1 (WAimportExportV1) para importar archivos PST correctamente mediante el método de envío de unidades. La versión 2 de la herramienta de importación y exportación de Azure no es compatible y, si la usa, se preparará incorrectamente la unidad de disco duro para el trabajo de importación. Asegúrese de descargar la herramienta de importación y exportación de Azure desde el Centro de seguridad & cumplimiento siguiendo los procedimientos descritos en este paso. 
  
1. Vaya a [https://protection.office.com/](https://protection.office.com/) e inicie sesión con las credenciales de una cuenta de administrador de su organización. 
    
2. En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **gobernanza de información**\>**Importar**\>**archivos PST**.
    
    > [!NOTE]
    > Como se indicó anteriormente, tiene que tener asignados los permisos adecuados para tener acceso a la página Importar en el Centro de & cumplimiento.  
  
3. En la página **Importar**, haga clic en ![Agregar icono](../media/ITPro-EAC-AddIcon.gif) **Nuevo trabajo de importación**.
    
4. En el asistente para importar trabajo, escriba un nombre para el trabajo de importación de PST y, a continuación, haga clic en **Siguiente**. Use letras minúsculas, números, guiones y caracteres de subrayado. Las letras en mayúscula no se pueden usar ni se pueden incluir espacios en el nombre.
    
5. En la página **Elegir tipo de trabajo de** importación, haga clic en Enviar unidades de disco duro a una de nuestras **ubicaciones** físicas y, a continuación, haga clic en **Siguiente.**
    
    ![Haga clic en Enviar unidades de disco duro a una de nuestras ubicaciones físicas para crear un trabajo de importación de envío de unidades](../media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. En la página **Importar datos**, siga los dos pasos siguientes: 
    
    ![Copie la clave de almacenamiento seguro y descargue la herramienta Azure Import Export en la página Importar datos](../media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    a. En el paso 2, haga **clic en Copiar la clave de almacenamiento seguro.** Después de mostrar la clave  de almacenamiento, haga clic en Copiar en el Portapapeles y, a continuación, péguela y guárdela en un archivo para que pueda obtener acceso a ella más adelante.
    
    b. En el paso 3, descargue la herramienta **Azure Import/Export** para descargar e instalar la herramienta Azure Import/Export (versión 1).
    
    - En la ventana emergente,  haga clic en Guardar como para guardar el archivo WaImportExportV1.zip en una \>  carpeta del equipo local. 
    
    - Extraiga el WaImportExportV1.zip archivo.
    
7. Haga **clic en** Cancelar para cerrar el asistente. 
    
    Volverá a la página **Importar** en el Centro de seguridad & cumplimiento cuando cree el trabajo de importación en el paso 4. 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a>Paso 2: Copiar los archivos PST en la unidad de disco duro

El siguiente paso es usar la herramienta WAImportExport.exe para copiar archivos PST en la unidad de disco duro. Esta herramienta cifra la unidad de disco duro con BitLocker, copia los ARCHIVOSTS en la unidad de disco duro y crea un archivo de diario que almacena información sobre el proceso de copia. Para llevar a cabo este paso, los archivos PST tienen que estar ubicados en un recurso compartido de archivos o en un servidor de archivos de su organización. Esto se conoce como el directorio de origen en el siguiente procedimiento. 

 Como se indicó anteriormente, cada archivo PST que copie en la unidad de disco duro no debe tener más de 20 GB. Los archivos PST con un tamaño superior a 20 GB pueden afectar al rendimiento del proceso de importación de PST que comience en el paso 6.
  
> [!IMPORTANT]
> Después de ejecutar por primera vez la herramienta WAImportExport.exe para una unidad de disco duro, tendrá que usar una sintaxis diferente cada vez que la use. Esta sintaxis se explica en el paso 4 de este procedimiento para copiar archivos PST en la unidad de disco duro. 
  
1. Abra el símbolo del sistema del equipo local.
    
    > [!TIP]
    > Si ejecuta el símbolo del sistema como administrador (seleccionando "Ejecutar como administrador" al abrirlo), en la ventana del símbolo del sistema aparecerán mensajes de error que le pueden ayudar a solucionar los problemas que aparecen al ejecutar la herramienta WAImportExport.exe. 
  
2. Vaya al directorio en el que instaló la herramienta WAImportExport.exe en el paso 1.
    
3. Ejecute el siguiente comando la primera vez que use la herramienta WAImportExport.exe para copiar archivos PST en una unidad de disco duro.

    ```powershell
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /blobtype:BlockBlob /encrypt /logdir:<Log file location>
    ```

    En la tabla siguiente se describen los parámetros y los valores requeridos.
    
    |**Parámetro**|**Descripción**|**Ejemplo**|
    |:-----|:-----|:-----|
    | `/j:` <br/> |Especifica el nombre del archivo de diario. Este archivo se guarda en la misma carpeta en la que se encuentra la herramienta WAImportExport.exe. Todas las unidades de disco duro que envíe a Microsoft deben tener un archivo de diario. Cada vez que ejecute la herramienta WAImportTool.exe para copiar archivos PST en una unidad de disco duro, la información se anexará al archivo de diario de esa unidad.  <br/> El personal del centro de datos de Microsoft usa la información del archivo de diario para asociar la unidad de disco duro con el trabajo de importación que crea en el paso 4 y para cargar los archivos PST en el área de Azure Storage en la nube de Microsoft.  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |Especifica la letra de la unidad de disco duro cuando se conecta a su equipo local.  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |Especifica el nombre de la sesión de copia. Cada vez que ejecuta la herramienta WAImportExport.exe para copiar los archivos en la unidad de disco duro, se define una sesión. Los archivos PST se copian en una carpeta cuyo nombre es el nombre de la sesión especificado por este parámetro.   <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |Especifica el directorio de origen de la organización que contiene los archivos PST que se copiarán durante la sesión. No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |Especifica el directorio de destino en el área de Azure Storage en la nube de Microsoft donde se cargarán los archivos PST. Debe usar el valor  `ingestiondata/` . No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> Opcionalmente, también puede agregar una ruta de acceso de archivo adicional al valor de este parámetro. Por ejemplo, puede usar la ruta de acceso del archivo del directorio de origen en la unidad de disco duro (convertida a un formato de dirección URL), que se especifica en el  `/srcdir:` parámetro. Por ejemplo,  `\\FILESERVER01\PSTs` se cambia a  `FILESERVER01/PSTs` . En este caso, aún debe incluir en  `ingestiondata` la ruta de acceso del archivo. Por lo tanto, en este ejemplo, el valor  `/dstdir:` del parámetro sería  `"ingestiondata/FILESERVER01/PSTs"` .  <br/> Si tiene archivos PST con el mismo nombre de archivo, debería agregar la ruta de acceso de archivo adicional.  <br/> > [!NOTE]> Si incluye el nombre de ruta opcional, el espacio de nombres de un archivo PST después de cargarlo en el área de Azure Storage incluye el nombre de la ruta de acceso y el nombre del archivo PST; por ejemplo,  `FILESERVER01/PSTs/annb.pst` . Si no incluye un nombre de ruta de acceso, el espacio de nombres es solo el nombre de archivo PST; por  `annb.pst` ejemplo.           | `/dstdir:"ingestiondata/"` <br/> O bien  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |Especifica la clave de la cuenta de almacenamiento que obtuvo en el paso 1. No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/blobtype:` <br/> |Especifica el tipo de blobs en el área de Azure Storage a la que se importarán los archivos PST. Para importar archivos PST, use el valor **BlockBlob**. Este parámetro es obligatorio.   <br/> | `/blobtype:BlockBlob` <br/> |
    | `/encrypt` <br/> |Este modificador activa BitLocker en la unidad de disco duro. Este parámetro es necesario la primera vez que ejecuta la herramienta WAImportExport.exe.  <br/> La clave de cifrado de BitLocker se copia en el archivo de diario y en el archivo de registro que se crea si usas el  `/logfile:` parámetro. Como se ha explicado anteriormente, el archivo de diario se guarda en la misma carpeta en la que se encuentra la herramienta WAImportExport.exe.  <br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |Este parámetro opcional especifica una carpeta en la que se guardan los archivos de registro. Si no se especifica, los archivos de registro se guardan en la misma carpeta donde se encuentra WAImportExport.exe herramienta. No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    A continuación se muestra un ejemplo de la sintaxis de la herramienta WAImportExport.exe, en el que se usan valores reales para cada parámetro:
    
    ```powershell
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" blobtype:BlockBlob /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    Después de ejecutar el comando, aparecen mensajes de estado en los que se muestra el progreso de la copia de los archivos PST en la unidad de disco duro. En un mensaje de estado final aparece el número total de archivos copiados correctamente. 
    
4. Ejecute este comando cada vez que ejecute la herramienta WAImportExport.ext para copiar los archivos PST en la misma unidad de disco duro.

    ```powershell
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> /blobtype:BlockBlob 
    ```

    A continuación se muestra un ejemplo de la sintaxis para ejecutar sesiones posteriores y copiar los archivos PST en la misma unidad de disco duro.  

    ```powershell
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/" /blobtype:BlockBlob
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a>Paso 3: Crear el archivo de asignación de importación de PST

Después de que el personal del centro de datos de Microsoft cargue los archivos PST desde la unidad de disco duro al área de Azure Storage, el servicio de importación usará la información del archivo de asignación de importación de PST, que es un archivo de valores separados por comas (CSV), que especifica a qué buzones de usuario se importan los archivos PST. Este archivo CSV se enviará en el paso siguiente, cuando cree un trabajo de importación de archivos PST.
  
1. [Descargue una copia del archivo de asignación de importación de PST](https://go.microsoft.com/fwlink/p/?LinkId=544717).
    
2. Abra o guarde el archivo CSV en el equipo local. En el ejemplo siguiente se muestra un archivo de asignación de importaciones de archivos PST completado (que se abre en el Bloc de notas). Es mucho más fácil usar Microsoft Excel para editar el archivo CSV.

    ```text
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,FILESERVER01/PSTs,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,,,,,
    ```

    En la primera fila (o la primera fila de encabezado) del archivo CSV aparecen los parámetros que usará el servicio de importación de PST para importar los archivos PST a los buzones de los usuarios. Los nombres de los parámetros están separados por comas. Cada fila situada debajo de la fila de encabezado representa los valores de parámetro para importar un archivo PST a un buzón específico. Necesita una fila para cada archivo PST que se copió en la unidad de disco duro. No olvide reemplazar los datos de los marcadores de posición del archivo de asignación por los datos reales.

    > [!NOTE]
    > No cambie nada en la fila de encabezado, ni siquiera los parámetros SharePoint; se ignorarán durante el proceso de importación de PST. 
  
3. Use la información de la tabla siguiente para rellenar el archivo CSV con la información necesaria.
    
    |**Parámetro**|**Descripción**|**Ejemplo**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Especifica el servicio en el que se importarán los datos. Use `Exchange` para importar archivos PST a los buzones de los usuarios.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> | Especifica la ubicación de la carpeta en el área de Azure Storage a la que se copiarán los archivos PST cuando la unidad de disco duro se envíe a Microsoft.  <br/>  Lo que agregue en esta columna en el archivo CSV depende de lo que haya especificado para el  `/dstdir:` parámetro en el paso anterior. Si tiene subcarpetas en la ubicación de origen, el valor del parámetro debe contener la ruta de acceso relativa de la subcarpeta; por `FilePath` ejemplo, /folder1/user1/.  <br/>  Si  `/dstdir:"ingestiondata/"` usó, deje este parámetro en blanco en el archivo CSV.  <br/>  Si incluyó un nombre de ruta opcional para el valor del parámetro (por ejemplo, use ese nombre de ruta de acceso (sin incluir  `/dstdir:` "ingestiondata") para este parámetro en el archivo  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` CSV. El valor de este parámetro distingue mayúsculas de minúsculas.  <br/>  En cualquier caso, *no* incluya "ingestiondata" en el valor del parámetro `FilePath`. Deje este parámetro en blanco o especifique solo el nombre de ruta de acceso opcional.  <br/> > [!IMPORTANT]> el caso del nombre de la ruta de acceso del archivo debe ser el mismo caso que especificó en el  `/dstdir:` parámetro en el paso anterior. Por ejemplo, si usó el nombre de subcarpeta en el paso anterior, pero luego se usó en el parámetro del archivo CSV, se producirá un error en la importación del archivo  `"ingestiondata/FILESERVER01/PSTs"`  `fileserver01/psts`  `FilePath` PST. Asegúrese de usar las mismas mayúsculas y minúsculas en ambas instancias.           |(se deja en blanco)  <br/> O bien  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |Especifica el nombre del archivo PST que se importará al buzón del usuario. El valor de este parámetro distingue mayúsculas de minúsculas.  <br/> > [!IMPORTANT]> el caso del nombre del archivo PST en el archivo CSV debe ser el mismo que el archivo PST que se cargó en la ubicación de Azure Storage en el paso 2. Por ejemplo, si usa `annb.pst` en el parámetro `Name` del archivo CSV, pero el nombre del archivo PST real es `AnnB.pst`, se producirá un error en la importación de ese archivo PST. Asegúrese de que el nombre del PST en el archivo CSV use las mismas mayúsculas y minúsculas que el archivo PST real.           | `annb.pst` <br/> |
    | `Mailbox` <br/> |Especifica la dirección de correo electrónico del buzón en el que se importará el archivo PST. No puede especificar una carpeta pública porque el servicio de importación de PST no admite la importación de archivos PST a carpetas públicas.  <br/> Para importar un archivo PST a un buzón inactivo, tiene que especificar el GUID del buzón de correo de este parámetro. Para obtener este GUID, ejecute el siguiente comando de PowerShell en Exchange Online:  `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> > [!NOTE]> a veces, puede tener varios buzones con la misma dirección de correo electrónico, donde un buzón es un buzón activo y el otro está en un estado eliminado temporalmente (o inactivo). En estas situaciones, tiene que especificar el GUID del buzón de correo para identificar exclusivamente el buzón en el que se importa el archivo PST. Para obtener este GUID para los buzones activos, ejecute el siguiente comando de PowerShell: `Get-Mailbox <identity of active mailbox> | FL Guid`. Para obtener el GUID de los buzones eliminados temporalmente (o inactivos), ejecute este comando:  `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid` .           | `annb@contoso.onmicrosoft.com` <br/> O bien:  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Especifica si se va a importar el archivo PST en el buzón de archivo del usuario. Hay dos opciones:  <br/> **FALSE** Importa el archivo PST al buzón principal del usuario.  <br/> **TRUE** Importa el archivo PST al buzón de archivo del usuario. Esto supone que el [buzón de archivo del usuario está habilitado](enable-archive-mailboxes.md). Si establece este parámetro en `TRUE` y el buzón de archivo del usuario no está habilitado, se producirá un error en la importación para ese usuario. Si falla una importación para un usuario (porque su archivo no está habilitado y esta propiedad se establece en `TRUE`), los demás usuarios en el trabajo de importación no se verán afectados.  <br/>  Si deja este parámetro en blanco, el archivo PST se importa al buzón de correo principal del usuario.  <br/> **Nota**: para importar un archivo PST a un buzón de archivo basado en la nube para un usuario cuyo buzón de correo principal es local, solo tiene que especificar `TRUE` para este parámetro y especificar la dirección de correo electrónico del buzón local del usuario para el parámetro `Mailbox`.  <br/> | `FALSE` <br/> O bien  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Especifica la carpeta en la que se importa el archivo PST.  <br/>  Si deja este parámetro en blanco, el archivo PST se importará a una nueva carpeta denominada **Imported** ubicada en el nivel raíz del buzón (el mismo nivel que la carpeta Bandeja de entrada y las demás carpetas de buzón predeterminadas).  <br/>  Si especifica , los elementos del archivo PST se importarán directamente en la carpeta Bandeja de  `/` entrada del usuario.  <br/>  Si especifica ,  `/<foldername>` los elementos del archivo PST se importarán a una carpeta denominada  *\<foldername\>* . Por ejemplo, si usa `/ImportedPst`, los elementos se importarán a una carpeta llamada **PST importados**. Esta carpeta estará ubicada en el buzón del usuario en el mismo nivel que la carpeta Bandeja de entrada.  <br/> |(se deja en blanco)  <br/> O bien  <br/>  `/` <br/> O bien  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Este parámetro opcional especifica un valor numérico de la página de códigos que se usa para importar archivos PST en el formato de archivo ANSI. Este parámetro se usa para importar archivos PST de las organizaciones de chino, japonés y coreano, porque estos idiomas suelen usar un juego de caracteres doble byte (DBCS) para la codificación de caracteres. Si no se usa este parámetro para importar archivos PST de los idiomas que usan DBCS para los nombres de las carpetas de buzón, dichos nombres suelen ser incomprensibles después de la importación.  <br/> Para obtener una lista de los valores compatibles que se pueden usar para este parámetro, vea [Identificadores de página de códigos](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/> > [!NOTE]> como se indicó anteriormente, se trata de un parámetro opcional y no tiene que incluirlo en el archivo CSV. También puede incluirlo y dejar el valor en blanco para una o varias filas.           |(se deja en blanco)  <br/> O bien  <br/>  `932` (que es el identificador de página de códigos para ANSI/OEM japonés)  <br/> |
    | `SPFileContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.  <br/> |No aplicable  <br/> |
    | `SPManifestContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.  <br/> |No aplicable  <br/> |
    | `SPSiteUrl` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.  <br/> |No aplicable  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a>Paso 4: crear un trabajo de importación de PST en Office 365

El siguiente paso consiste en crear el trabajo de importación de PST en el servicio de importación de Office 365. Como se ha explicado anteriormente, debe enviar el archivo de asignación de importación de PST que creó en el paso 3. Después de crear el trabajo, el servicio de importación usará la información del archivo de asignación para importar los archivos PST al buzón de usuario especificado después de copiar los archivos PST desde la unidad de disco duro al área de Azure Storage y crear e iniciar el trabajo de importación.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con las credenciales de una cuenta de administrador de su organización. 
    
2. En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **gobernanza de información**\>**Importar**\>**archivos PST**.
    
3. En la página **Importar**, haga clic en ![Agregar icono](../media/ITPro-EAC-AddIcon.gif) **Nuevo trabajo de importación**.
    
    > [!NOTE]
    > Como se indicó anteriormente, tiene que tener asignados los permisos adecuados para tener acceso a la página Importar en el Centro de & cumplimiento.  
  
4. Escriba un nombre para el trabajo de importación de PST y haga clic en **Siguiente**. Use letras minúsculas, números, guiones y caracteres de subrayado. Las letras en mayúscula no se pueden usar ni se pueden incluir espacios en el nombre.
    
5. En la página **Elegir tipo de trabajo de** importación, haga clic en Enviar unidades de disco duro a una de nuestras **ubicaciones** físicas y, a continuación, haga clic en **Siguiente.**
    
    ![Haga clic en Enviar unidades de disco duro a una de nuestras ubicaciones físicas para crear un trabajo de importación de envío de unidades](../media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. En el paso 6, haga clic en las unidades de disco duro que he preparado y tengo acceso a los archivos de diario de unidad necesarios y tengo acceso a las casillas de verificación del archivo **de** asignación y, a continuación, haga clic en **Siguiente.** 
    
    ![Haga clic en las dos casillas del paso 6](../media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. En la página Seleccionar el  **archivo** de unidad, haga clic en Seleccionar archivo de unidad y, a continuación, vaya a la misma carpeta donde se encuentra la herramienta WAImportExport.exe unidad. En esta carpeta se copió el archivo de diario creado en el paso 2.
    
    ![Haga clic en Seleccionar archivo de unidad para enviar el archivo de diario que se creó al WAImportExport.exe herramienta](../media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. Seleccione el archivo de diario; por ejemplo, `PSTHDD1.jrn` .
    
    > [!TIP]
    > Cuando ejecutó la herramienta WAImportExport.exe en el paso 2, el parámetro especificó el nombre del archivo de  `/j:` diario. 
  
9. Cuando el nombre del archivo de unidad  aparezca en El nombre del archivo **de** unidad, haga clic en Validar para comprobar si hay errores en el archivo de la unidad. 
    
    ![Haga clic en Validar para validar el archivo de unidad que seleccionó](../media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    El archivo de unidad debe validarse correctamente para crear un trabajo de importación de PST. Tenga en cuenta que el nombre del archivo se cambia a verde una vez que se ha validado correctamente. Si se produce un error de validación, haga clic en el vínculo **Ver registro**. Se abre un informe de errores de validación, con un mensaje de error con información sobre por qué se produjo un error en el archivo. 
    
    > [!NOTE]
    > Debe agregar y validar un archivo de diario para cada unidad de disco duro que envíe a Microsoft. 
  
10. Después de agregar y validar un archivo de diario para cada unidad de disco duro que envíe a Microsoft, haga clic en **Siguiente.**
    
11. Haga clic en Agregar archivo de asignación de selección de iconos para enviar el archivo de asignación de importación ![ de PST que ](../media/ITPro-EAC-AddIcon.gif)  creó en el paso 3. 
    
    ![Hacer clic en Seleccionar el archivo de asignación para enviar el archivo CSV que ha creado para el trabajo de importación](../media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. Cuando el nombre del archivo CSV aparezca en **Asignación del nombre de archivo**, haga clic en **Validar** para comprobar si hay errores en el archivo CSV. 
    
    ![Hacer clic en Validar para comprobar si hay errores en el archivo CSV](../media/4680999d-5538-4059-b878-2736a5445037.png)
  
    El archivo CSV debe estar validado correctamente para poder crear un trabajo de importación de PST. Tenga en cuenta que el nombre del archivo se cambia a verde una vez que se ha validado correctamente. Si se produce un error de validación, haga clic en el vínculo **Ver registro**. Se abre un informe de errores de validación, con un mensaje de error para cada fila del archivo que ha fallado. 
    
13. Después de validar correctamente el archivo de asignación de PST, haga clic **en Siguiente.**
    
14. En la **página Proporcionar información de** contacto, escriba la información de contacto en los cuadros correspondientes. 
    
    Se muestra la dirección de la ubicación de Microsoft a la que envía las unidades de disco duro. Esta dirección se genera automáticamente en función de la ubicación del centro de datos de Microsoft. Copie esta dirección en un archivo o tome una captura de pantalla.
    
15. Lea el documento de términos y condiciones, haga clic en la casilla y, a continuación, haga clic en **Guardar** para enviar el trabajo de importación. 
    
    Cuando el trabajo de importación se crea correctamente, se muestra una página de estado que explica los pasos siguientes del proceso de envío de unidades.
    
16. En la **página Importar archivos PST,** haga clic en el icono Actualizar para mostrar el nuevo trabajo de importación de envío de unidades en la ![ lista de trabajos de ](../media/O365-MDM-Policy-RefreshIcon.gif)  importación. El estado se establece en **Esperar número de seguimiento.** También puede hacer clic en el trabajo de importación para mostrar la página desplegable de estado, que contiene información más detallada sobre el trabajo de importación.
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a>Paso 5: enviar la unidad de disco duro a Microsoft

El siguiente paso es enviar la unidad de disco duro a Microsoft y, a continuación, proporcionar el número de seguimiento del envío y devolver la información de envío para el trabajo de envío de la unidad. Después de que Microsoft reciba la unidad, el personal del centro de datos llevará entre 7 y 10 días laborables cargar los archivos PST en el área de Azure Storage para su organización.
  
> [!NOTE]
> Si no proporciona el número de seguimiento y devuelve la información de envío en un plazo de 14 días a partir de la creación del trabajo de importación, el trabajo de importación expirará. Si esto ocurre, tendrá que crear un nuevo trabajo de importación de envío de unidades (vea paso 4: Crear un trabajo de importación de PST en [Office 365)](#step-4-create-a-pst-import-job-in-office-365)y volver a enviar el archivo de unidad y el archivo de asignación de importación de PST. 
  
### <a name="ship-the-hard-drive"></a>Enviar la unidad de disco duro

Tenga en cuenta lo siguiente a la hora de enviar las unidades de disco duro a Microsoft:
  
- No envíes el adaptador SATA a USB; solo tiene que enviar la unidad de disco duro.
    
- Empaquete la unidad de disco duro correctamente (por ejemplo, use un envoltorio de plástico con burbujas o una bolsa antiestática).
    
- Seleccione la empresa de transporte que desee para enviar la unidad de disco duro a Microsoft.
    
- Envíe la unidad de disco duro a la dirección de la ubicación de Microsoft que aparecía al crear el trabajo de importación en el paso 4. No olvide incluir «Office 365 Import Service» en la dirección de envío.
    
- Después de enviar la unidad de disco duro, asegúrese de anotar el nombre del transportista y el número de seguimiento, que deberá especificar en el siguiente paso.
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a>Indicar el número de seguimiento y otros datos de envío

Cuando haya enviado la unidad de disco duro a Microsoft, lleve a cabo el procedimiento siguiente en la página Servicio de importación.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con las credenciales de una cuenta de administrador de su organización. 
    
2. En el panel izquierdo, haga clic en **Gobierno de > importar > importar archivos PST**.
    
3. En la **página Importar archivos PST,** haga clic en el trabajo para el envío de la unidad para el que desea escribir el número de seguimiento. 
    
4. En la página desplegable de estado, haga clic **en Escribir número de seguimiento.**
    
5. Proporcione la siguiente información de envío:
    
1. **Operador de entrega** Escriba el nombre de la compañía de entrega que usó para enviar la unidad de disco duro a Microsoft. 
    
2. **Número de seguimiento** Escriba el número de seguimiento del envío de la unidad de disco duro. 
    
3. **Número de cuenta de la compañía de transporte de devolución** Escriba el número de cuenta de su organización para el operador que aparece en **Operador de devolución.** Microsoft usa (y cobra) esta cuenta para volver a enviar la unidad de disco duro. Las organizaciones de Estados Unidos y Europa deben tener una cuenta con FedEx. Las organizaciones de Asia y del resto del mundo deben tener una cuenta con DHL.
    
6. Haga clic en **Guardar** para guardar esta información del trabajo de importación. 
    
    En la **página Importar archivos PST,** haga clic en el icono Actualizar para actualizar la información del trabajo de importación ![ de envío de ](../media/O365-MDM-Policy-RefreshIcon.gif)  unidades. Observe que el estado ahora está establecido en **Unidades en tránsito**.

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Paso 6: filtrar los datos e iniciar el trabajo de importación de PST

Después de que Microsoft reciba la unidad de disco duro, el estado del trabajo de importación en la página Importar archivos **PST** cambiará a **Unidades recibidas.** El personal del centro de datos usa la información del archivo de diario para cargar los archivos PST en el área de Azure Storage de su organización. En este punto, el estado cambia **a Importar en curso**. Como se indicó anteriormente, se tardarán entre 7 y 10 días laborables después de recibir la unidad de disco duro para cargar los archivos PST.
  
Después de cargar los archivos PST en Azure, el estado cambia a **Análisis en curso.** Esto indica que Microsoft 365 está analizando los datos de los archivos PST (de forma segura y segura) para identificar la antigüedad de los elementos y los diferentes tipos de mensajes incluidos en los archivos PST. Cuando se completa el análisis y los datos están listos para importarse, el estado del trabajo de importación cambia a **Análisis completado.** En este punto, tiene la opción de importar todos los datos contenidos en los archivos PST o puede recortar los datos que se importan estableciendo filtros que controlan qué datos se importan.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con las credenciales de una cuenta de administrador de su organización. 
    
2. En el panel izquierdo, haga clic en **Gobierno de** información \> **Importar** archivos \> **PST.**
    
3. En la **página Importar archivos PST,** haga clic en Listo para importar a **Office 365** para el trabajo de importación que creó en el paso 4. 
    
    ![Haga clic en Preparado para importar a Microsoft 365, junto al trabajo de importación que ha creado.](../media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Se muestra una página de control flotante con información sobre los archivos PST y otra información sobre el trabajo de importación.
    
4. Haga **clic en Importar a Office 365.**
    
5. Se mostrará la página **Filtrar los datos**. Contiene las información sobre datos resultante del análisis realizado en los archivos PST por Office 365, incluida la antigüedad de los datos. En este momento, tiene la opción de filtrar los datos que se importarán o importar todos los datos tal como estén. 
    
    ![Puede recortar los datos de los archivos PST o importarlos todos](../media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. Realice una de las acciones siguientes:
    
    A. Para recortar los datos que importa, haga clic en **Sí, quiero filtrarlos antes de importarlos**.
    
    Para obtener instrucciones detalladas paso a paso sobre cómo filtrar los datos en los archivos PST y, después, iniciar el trabajo de importación, vea [Filtrar datos al importar archivos PST a Office 365](filter-data-when-importing-pst-files.md).
    
    O bien
    
    B. Para importar todos los datos de los archivos PST, haga clic en **No, quiero importarlos todos** y en **Siguiente**.
    
7. Si ha elegido importar todos los datos, haga clic en **Importar datos** para iniciar el trabajo de importación. 
    
    El estado del trabajo de importación se muestra en la **página Importar archivos PST.** Haga clic en el ![icono Actualizar](../media/O365-MDM-Policy-RefreshIcon.gif) **Actualizar** para actualizar la información de estado que se muestra en la columna **Estado**. Haga clic en el trabajo de importación para mostrar la página de control flotante de estado, donde se muestra la información de estado de cada archivo PST que se importa. Una vez completada la importación y los archivos PST se han importado a los buzones de usuario, el estado cambiará a **Completado.**

## <a name="view-a-list-of-the-pst-files-uploaded-to-microsoft-365"></a>Ver una lista de los archivos PST cargados en Microsoft 365

Puede instalar y usar el Explorador de Microsoft Azure Storage (que es una herramienta gratuita de código abierto) para ver la lista de los archivos PST que cargamos (por el personal del centro de datos de Microsoft) en el área de Azure Storage para su organización. Puede hacerlo para comprobar que los archivos PST de las unidades de disco duro que envió a Microsoft se cargaron correctamente en el área de Azure Storage.
  
El Explorador de Microsoft Azure Storage está en versión preliminar.
  
 **Importante:** No puede usar el Explorador de Azure Storage para cargar o modificar archivos PST. El único método admitido para importar archivos PST a Microsoft 365 es usar AzCopy. Además, no puede eliminar archivos PST que haya cargado al blob de Azure. Si intenta eliminar un archivo PST, recibirá un error sobre no tener los permisos necesarios. Todos los archivos PST se eliminan automáticamente del área de Azure Storage. Si no hay ningún trabajo de importación en curso, todos los archivos PST del contenedor ** ingestiondata ** se eliminan 30 días después de crear el trabajo de importación más reciente. 
  
Para instalar el Explorador de Azure Storage y conectarse al área de Azure Storage, haga lo siguiente:
  
1. Realice los pasos siguientes para obtener la dirección URL de firma de acceso compartido (SAS) de su organización. Esta dirección URL es una combinación de la dirección URL de red para la ubicación de Azure Storage en la nube de Microsoft para su organización y una clave SAS. Esta clave le proporciona los permisos necesarios para acceder a la ubicación de Azure Storage de su organización.
    
1. Vaya a [https://protection.office.com/](https://protection.office.com/) e inicie sesión con las credenciales de una cuenta de administrador de su organización. 
    
2. En el panel izquierdo del Centro de Seguridad y Cumplimiento, haga clic en **Gobernanza de la información > Importar > Importar archivos PST** .
    
3. En la página **Importar**, haga clic en ![Agregar icono](../media/ITPro-EAC-AddIcon.gif) **Nuevo trabajo de importación**.
    
4. En el asistente para importar trabajo, escriba un nombre para el trabajo de importación de PST y, a continuación, haga clic en **Siguiente**. Use letras minúsculas, números, guiones y caracteres de subrayado. Las letras en mayúscula no se pueden usar ni se pueden incluir espacios en el nombre.
    
5. En la página **Elegir tipo de trabajo de** importación, haga clic en Cargar los **datos** y, a continuación, haga clic en **Siguiente.**
    
6. En el paso 2, haga clic en **Mostrar dirección URL de carga en la red de SAS**.
    
7. Una vez que se muestre la dirección URL, cópiela y guárdela en un archivo. Asegúrese de copiar toda la dirección URL.
    
    > [!IMPORTANT]
    > Asegúrese de tomar precauciones para proteger la URL de SAS. Cualquiera puede usar esto para acceder al área de almacenamiento de Azure de su organización. 
  
8. Haga **clic en Cancelar** para cerrar el Asistente para importación de trabajos. 
    
2. Descargue e instale la [herramienta Explorador de Microsoft Azure Storage](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
3. Inicie el Explorador de Microsoft Azure Storage, haga clic derecho en **Cuentas de almacenamiento** en el panel izquierdo y, después, haga clic en **Conectar con Azure Storage**.
    
    ![Haga clic derecho en Cuentas de almacenamiento y, después, en Conectar a Azure Storage](../media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. Haga clic en **Usar un URI de Firma de acceso compartido (SAS) o cadena de conexión** y, luego, en **Siguiente**.
    
5. Haga clic en Usar un URI de **SAS,** pegue la dirección URL de SAS que obtuvo en el paso 1 en el cuadro **debajo** de URI y, a continuación, haga clic en **Siguiente**.
    
6. En la página **Resumen de conexión**, puede revisar la información de conexión y, después, haga clic en **Conectar**.
    
    El contenedor **ingestiondata** está abierto. Contiene los archivos PST de la unidad de disco duro. El contenedor **ingestiondata** se encuentra en **Cuentas de almacenamiento** \> **(servicios vinculados de SAS)** \> **Contenedores de blob**.
    
    ![El Explorador de Azure Storage muestra una lista de los archivos PST que ha cargado](../media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. Cuando termine de usar el Explorador de Microsoft Azure Storage, haga clic derecho en **ingestiondata** y, después, en **Desasociar** para desconectarse del área de Azure Storage. En caso contrario, recibirá un error la próxima vez que intente vincularse. 
    
    ![Haga clic derecho en Ingesta y, luego, seleccione Desasociar para desconectarse de su área de Azure Storage](../media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)

## <a name="troubleshooting-tips"></a>Sugerencias para solucionar problemas

- **¿Qué sucede si se produce un error en el trabajo de importación debido a errores en el archivo de asignación csv de importación de PST?** Si se produce un error en un trabajo de importación debido a errores en el archivo de asignación, no tiene que volver a asignar la unidad de disco duro a Microsoft para crear un trabajo de importación. Esto se debe a que los archivos PST de la unidad de disco duro que envió para el trabajo de importación de envío de unidades ya se han cargado en el área de Azure Storage para su organización. En este caso, solo tiene que corregir los errores en el archivo de asignación DE CSV de importación de PST y, a continuación, crear un nuevo trabajo de importación de "carga de red" y enviar el archivo de asignación CSV revisado. Para crear e iniciar un nuevo trabajo de importación de carga de red, vea el paso 5: Crear un trabajo de importación de PST en [Microsoft 365](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job) y paso [6:](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job) Filtrar datos e iniciar el trabajo de importación de PST en el tema "Usar la carga de red para importar archivos PST a Office 365". 
    
    > [!NOTE]
    > Para ayudarle a solucionar los problemas del archivo de asignación de ARCHIVOS CSV de importación de PST, use la herramienta Explorador de [Azure Storage](#view-a-list-of-the-pst-files-uploaded-to-microsoft-365) para ver la estructura de carpetas en el contenedor **de datos** de ingesta de los archivos PST de la unidad de disco duro que se cargaron en el área de almacenamiento de Azure. Los errores de archivo de asignación suelen deberse a un valor incorrecto en el parámetro FilePath. Este parámetro especifica la ubicación de un archivo PST en el área de almacenamiento de Azure. Vea la descripción del parámetro FilePath en la tabla del [paso 3.](#step-3-create-the-pst-import-mapping-file) Como se ha explicado anteriormente, el parámetro especificó la ubicación de los archivos PST en el área de almacenamiento de Azure cuando ejecutó la herramienta WAImportExport.exe en el `/dstdir:` [paso 2.](#step-2-copy-the-pst-files-to-the-hard-drive) 
  
## <a name="more-information"></a>Más información

- El envío de unidades es una forma eficaz de importar grandes cantidades de datos de mensajería de archivado a Microsoft 365 para aprovechar las características de cumplimiento que están disponibles para su organización. Después de importar los datos de archivo a los buzones de usuario, puede:
    
  - Habilite [los buzones de archivo](enable-archive-mailboxes.md) y el archivado de [expansión automática](enable-unlimited-archiving.md) para proporcionar a los usuarios más espacio de almacenamiento para los datos. 
    
  - Coloque los buzones en retención [por](https://go.microsoft.com/fwlink/?linkid=856286) juicio para conservar los datos. 
    
  - Use las herramientas [de exhibición de documentos electrónicos de](search-for-content.md) Microsoft para buscar en los datos. 
    
  - Aplicar directivas de retención de [Microsoft 365](retention.md) para controlar cuánto tiempo se conservan los datos y qué acción realizar después de que expire el período de retención. 
    
  - Busque eventos [relacionados](search-the-audit-log-in-security-and-compliance.md) con estos datos en el registro de auditoría. 
    
  - Importar datos a [buzones inactivos para](create-and-manage-inactive-mailboxes.md) archivar datos con fines de cumplimiento. 
    
  - Proteja su organización contra [la pérdida de datos](data-loss-prevention-policies.md) de información confidencial. 
    
- A continuación se muestra un ejemplo de la clave de la cuenta de almacenamiento seguro y una clave de cifrado de BitLocker. Este ejemplo también contiene la sintaxis del comando WAImportExport.exe que ejecutó para copiar los archivos PST en una unidad de disco duro. Asegúrese de tomar precauciones para protegerlos de la misma manera que protegería las contraseñas u otra información relacionada con la seguridad.
    

    ```text
    Secure storage account key: 

    yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==

    BitLocker encryption key:

    397386-221353-718905-535249-156728-127017-683716-083391

  COMMAND SYNTAX

  First time:

  WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /blobtype:BlockBlob /encrypt /logdir:<Log file location>

  Subsequent times:

  WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> /blobtype:BlockBlob 

  EXAMPLES

  First time:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER1\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /blobtype:BlockBlob /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"

  Subsequent times:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER1\PSTs\SecondBatch" /dstdir:"ingestiondata/" /blobtype:BlockBlob
    ```

- Como se ha explicado anteriormente, el servicio de importación de Office 365 activa la opción de suspensión de retención (durante un período de tiempo indefinido) después de que los archivos PST se importan a un buzón. Esto significa que  *la propiedad RentionHoldEnabled*  se establece en para que no se procese la directiva de retención asignada al  `True` buzón. Esto da al propietario del buzón tiempo para administrar los mensajes recién importados evitando que una directiva de eliminación o de archivado elimine o archive los mensajes más antiguos. Estos son algunos pasos que puede seguir para administrar esta suspensión de retención: 
    
  - Después de un período de tiempo determinado, puede desactivar la suspensión de retención ejecutando el  `Set-Mailbox -RetentionHoldEnabled $false` comando. Para obtener instrucciones, vea [Aplicar la suspensión de retención a un buzón](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
  - Puede configurar la suspensión de retención para que esté desactivada en una fecha futura. Para ello, ejecute el  `Set-Mailbox -EndDateForRetentionHold <date>` comando. Por ejemplo, suponiendo que la fecha de hoy es el 1 de junio de 2016 y desea desactivar la suspensión de retención en 30 días, ejecutaría el siguiente comando:  `Set-Mailbox -EndDateForRetentionHold 7/1/2016` . En este escenario, se deja la propiedad  *DesconexiónHoldEnabled*  establecida en  *True*. Para obtener más información, vea [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
  - Puede cambiar la configuración de la directiva de retención que está asignada a un buzón para que los elementos antiguos importados no se eliminen inmediatamente ni se muevan al buzón de archivo del usuario. Por ejemplo, podría alargar la antigüedad de la retención de una directiva de archivado o eliminación que se asigna al buzón. En este escenario, debe desactivar la suspensión de retención en el buzón de correo después de cambiar la configuración de la directiva de retención. Para obtener más información, vea [Configurar una directiva de archivado y eliminación de buzones en la organización](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    

  

