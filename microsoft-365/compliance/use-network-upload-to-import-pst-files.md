---
title: Usar la carga en la red para importar los archivos PST de su organización
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 'Para administradores: obtenga información sobre cómo usar la carga en la red para importar en bloque varios archivos PST a buzones de usuario en Microsoft 365.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b59ffc9d665091a5de1e5e23ab8e32be6d86f1a5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925466"
---
# <a name="use-network-upload-to-import-your-organizations-pst-files-to-microsoft-365"></a>Usar la carga en la red para importar los archivos PST de su organización a Microsoft 365

> [!NOTE]
> Este artículo está dirigido a administradores. ¿Está intentando importar archivos PST a su propio buzón? Consulte [Importar el correo electrónico, los contactos y el calendario desde un archivo .pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)
  
Estas son las instrucciones paso a paso necesarias para usar la carga en la red para importar en bloque varios archivos PST a buzones de Microsoft 365. Para leer las preguntas más frecuentes sobre el uso de la carga en la red para importar en bloque archivos PST a los buzones de Microsoft 365, vea [Preguntas más frecuentes sobre el uso de carga en la red para importar archivos PST](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files).
  
[Paso 1: copiar la URL de SAS e instalar AzCopy](#step-1-copy-the-sas-url-and-install-azcopy)

[Paso 2: cargar los archivos PST en Microsoft 365](#step-2-upload-your-pst-files-to-office-365)

[Paso 3 (opcional): ver una lista de los archivos PST cargados](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Paso 4: crear el archivo de asignación de importación de PST](#step-4-create-the-pst-import-mapping-file)

[Paso 5: Crear un trabajo de importación de PST](#step-5-create-a-pst-import-job)

[Paso 6: filtrar los datos e iniciar el trabajo de importación de PST](#step-6-filter-data-and-start-the-pst-import-job)

Tenga en cuenta que debe llevar a cabo el paso 1 solo una vez para importar los archivos PST a los buzones de Microsoft 365. Después de realizar estos pasos, siga los pasos comprendidos entre el 2 y el 6 cada vez que quiera cargar e importar un lote de archivos PST.

## <a name="before-you-import-pst-files"></a>Antes de importar archivos PST
  
- Debe tener asignado el rol importación y exportación de buzón de Exchange Online para importar archivos PST a los buzones de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Mailbox Import Export al grupo de roles Administración de la organización. También puede crear un grupo de roles, asignarle el rol Mailbox Import Export y agregarse a sí mismo como miembro. Para obtener más información, vea las secciones "Agregar un rol a un grupo de roles" o "Crear un grupo de roles" en [Administrar grupos de roles](/Exchange/permissions-exo/role-groups).
    
    Además, para crear trabajos de importación en el Centro de seguridad y cumplimiento, debe cumplirse uno de estos requisitos:
    
  - Debe tener asignado el rol de los destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos de roles de administración de la organización y administración de destinatarios.
    
    O bien:
    
  - Necesita ser administrador global en su organización.
    
  > [!TIP]
    > Puede crear un nuevo grupo de roles en Exchange Online que esté pensado específicamente para la importación de archivos PST. Para obtener el nivel mínimo de privilegios necesarios para importar archivos PST, asigne los roles de importación y exportación de buzón y de destinatarios de correo al nuevo grupo de roles y, a continuación, agregue a los miembros.
  
- El único método admitido para importar archivos PST a Microsoft 365 es usar la herramienta AzCopy, tal y como se describe en este tema. No puede usar el Explorador de Azure Storage para cargar archivos PST directamente en el área de Azure Storage.
    
- Debe almacenar los archivos PST que quiere importar a Microsoft 365 en un servidor de archivos o en una carpeta compartida de la organización. En el paso 2, ejecutará la herramienta AzCopy, que cargará los archivos PST almacenados en este servidor de archivos o carpeta compartida en Microsoft 365.
    
- Es posible que los archivos PST de gran tamaño afecten al rendimiento del proceso de importación de PST. Por lo tanto, le recomendamos que cada archivo PST que cargue en la ubicación de  Azure Storage en el paso 2 no sea superior a 20 GB.

- Este procedimiento implica copiar y guardar una copia de una dirección URL que contiene una clave de acceso. Esta información se utilizará en el paso 2 para cargar los archivos PST y, en el paso 3, si quiere ver una lista de los archivos PST cargados en Office 365. Asegúrese de tomar precauciones para proteger esta dirección URL de la misma manera que protegería las contraseñas u otra información relacionada con la seguridad. Por ejemplo, puede guardarla en un documento de Microsoft Word protegido por contraseña o en una unidad USB cifrada. Consulte la sección [Más información](#more-information) para ver un ejemplo de la clave y URL combinadas.
    
- Puede importar archivos PST a un buzón inactivo de Office 365. Para ello, debe especificar el GUID del buzón inactivo en el parámetro `Mailbox` del archivo de asignación de importación de PST. Vea el paso 4 en la pestaña **Instrucciones** de este tema para obtener información. 
    
- En una implementación híbrida de Exchange, puede importar archivos PST a un buzón de archivo basado en la nube para un usuario cuyo buzón principal es local. Para ello, haga lo siguiente en el archivo de asignación de importación de PST:
    
  - Especifique la dirección de correo electrónico del buzón local del usuario en el parámetro `Mailbox`.
    
  - Especifique el valor **TRUE** en el parámetro `IsArchive`.
    
    Vea el [paso 4](#step-4-create-the-pst-import-mapping-file) para obtener más información.
    
- Después de que los archivos PST se importan, la configuración de espera de retención del buzón está activada durante un período de tiempo indefinido. Esto significa que la directiva de retención asignada al buzón no se procesará hasta que desactive la espera de retención o establezca una fecha para desactivar la retención. ¿Por qué lo hacemos? Si los mensajes importados a un buzón son antiguos, es posible que se eliminen de forma permanente, ya que su período de retención ha caducado en función de la configuración de retención establecida para el buzón. Al colocar el buzón en espera de retención, el propietario del buzón tiene tiempo para administrar estos mensajes recién importados o usted tendrá tiempo para cambiar la configuración de retención del buzón. Vea la pestaña [Más información](#more-information) en este tema para obtener sugerencias sobre cómo administrar la espera de retención.
    
- De forma predeterminada, el tamaño máximo de mensaje que puede recibir un buzón de Microsoft 365 es de 35 MB. Esto se debe a que el valor predeterminado de la propiedad *MaxReceiveSize* de un buzón está establecido en 35 MB. Pero el límite de tamaño máximo de recepción de mensajes en Microsoft 365 es de 150 MB. Por lo tanto, si importa un archivo PST que contiene un elemento superior a 35 MB, el servicio de importación de Office 365 cambiará automáticamente el valor de la propiedad *MaxReceiveSize* en el buzón de destino a 150 MB. Esto permite que se importen a buzones de usuario mensajes de hasta 150 MB.
    
    > [!TIP]
    > Para identificar el tamaño de recepción de un buzón de correo, puede ejecutar este comando en PowerShell de Exchange Online: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`.

- Para obtener información general sobre el proceso de importación de PST, vea la sección de este artículo [Cómo funciona el proceso de importación](#how-the-import-process-works).

## <a name="step-1-copy-the-sas-url-and-install-azcopy"></a>Paso 1: copiar la URL de SAS e instalar AzCopy

El primer paso es descargar e instalar la herramienta AzCopy, que es la herramienta que ejecutará en el Paso 2 para cargar los archivos PST en Office 365. También deberá copiar la dirección URL de SAS de su organización. Esta dirección URL es una combinación de la dirección URL de red de la ubicación de Azure Storage en la nube de Microsoft de su organización y una clave de Firma de acceso compartido (SAS). Esta clave le proporciona los permisos necesarios para cargar los archivos PST a la ubicación de Azure Storage. Asegúrese de tomar precauciones para proteger la URL de SAS. Es exclusiva para su organización y se usará en el paso 2.

> [!IMPORTANT]
> Para importar archivos PST con el método de carga de red y la sintaxis de comandos que se documentan en este artículo, debe usar la versión de AzCopy que puede descargarse en el paso 6B en el procedimiento siguiente. También puede descargar la misma versión de AzCopy [aquí](https://aka.ms/downloadazcopy). No se admite el uso de una versión diferente de AzCopy.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con las credenciales de una cuenta de administrador de su organización.
    
2. En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **gobernanza de información**\>**Importar**\>**archivos PST**.
    
    > [!NOTE]
    > Es necesario que tenga asignados los permisos adecuados para tener acceso a la página **Importar** en el Centro de seguridad y cumplimiento. Vea la sección **Antes de empezar** para obtener más información. 
    
3. En la página **Importar**, haga clic en ![Agregar icono](../media/ITPro-EAC-AddIcon.gif) **Nuevo trabajo de importación**.
    
    Se mostrará el asistente para la importación de trabajos.
    
4. Escriba un nombre para el trabajo de importación de PST y haga clic en **Siguiente**. Use letras minúsculas, números, guiones y caracteres de subrayado. Las letras en mayúscula no se pueden usar ni se pueden incluir espacios en el nombre.
    
5. En la página **¿Quiere cargar o enviar datos?**, haga clic en **Cargar los datos** y, después, en **Siguiente**.
    
    ![Hacer clic en Cargar los datos para crear un trabajo de importación de carga en la red](../media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. En la página **Importar datos**, siga los dos pasos siguientes: 
    
    ![Copiar la dirección URL de SAS y descargar la herramienta AzCopy en la página Importar datos](../media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    1. En el paso 2, haga clic en **Mostrar dirección URL de carga en la red de SAS**. Después de que se muestre la URL de SAS, haga clic en **Copiar al Portapapeles**, péguela y guárdela en un archivo para que pueda acceder a ella más tarde.
    
    1. En el paso 3, haga clic en **Descargar AzCopy** para descargar e instalar la herramienta. En la ventana emergente, haga clic en **Ejecutar** para instalar AzCopy. 
    
   > [!NOTE]
   > Puede dejar abierta la página **Importar datos** (en caso de que necesite volver a copiar la URL de SAS) o hacer clic en **Cancelar** para cerrarla. 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>Paso 2: cargar los archivos PST en Office 365

Ahora ya puede usar la herramienta AzCopy.exe para cargar los archivos PST en Office 365. Esta herramienta los carga y los almacena en una ubicación de Azure Storage en la nube de Microsoft. Como se ha explicado anteriormente, la ubicación de Azure Storage a la que carga los archivos PST está en el mismo centro de datos regional de Microsoft que su organización. Para llevar a cabo este paso, los archivos PST tienen que estar ubicados en un recurso compartido de archivos o en un servidor de archivos de su organización. Esto se conoce como el directorio de origen en este procedimiento. Cada vez que ejecute la herramienta AzCopy, puede especificar un directorio de origen diferente. 

> [!NOTE]
> Por lo tanto, le recomendamos que cada archivo PST que cargue en la ubicación de  Azure Storage en el paso 20 no sea superior a 20 GB. Los archivos PST con un tamaño superior a 20 GB pueden afectar al rendimiento del proceso de importación de PST que comience en el paso 6.

1. Abra el símbolo del sistema del equipo local.
    
2. Vaya al directorio en el que instaló la herramienta AzCopy.exe en el paso 1. Si ha instalado la herramienta en la ubicación predeterminada, vaya a `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`.
    
3. Ejecute el comando siguiente para cargar los archivos PST en Office 365.

    ```powershell
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
    ```

    > [!IMPORTANT] 
    > Debe especificar un directorio como la ubicación de origen en el comando anterior. No se puede especificar un archivo PST individual. Se cargarán todos los archivos PST en el directorio de origen.
 
    En la tabla siguiente se describen los parámetros y los valores requeridos de AzCopy.exe. La información de los pasos anteriores se usa en los valores de estos parámetros.
    
    | Parámetro | Descripción | Ejemplo |
    |:-----|:-----|:-----|
    | `/Source:` <br/> |Especifica el directorio de origen de la organización que contiene los archivos PST que se cargarán en Office 365.  <br/> No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |Especifica la URL de SAS que ha obtenido en el paso 1.  <br/> No olvide incluir el valor de este parámetro entre comillas dobles (" ").<br/><br/>**Nota:** si usa la dirección URL de SAS en un archivo de proceso por lotes o un script, tiene que tener cuidado con determinados caracteres que necesitan escapar.  Por ejemplo, tiene que cambiar `%` a `%%` y cambiar `&` a `^&`.<br/><br/>**Sugerencia:** (opcional) puede especificar una subcarpeta en la ubicación de Azure Storage en la que cargar los archivos PST. Para ello, agregue una ubicación de subcarpeta (después de "ingestiondata") en la dirección URL de SAS. En el primer ejemplo no se especifica una subcarpeta. Esto significa que los PST se cargan en la raíz (denominada *ingestiondata*) de la ubicación de Azure Storage. El segundo ejemplo carga los archivos PST en una subcarpeta (denominada *PSTFiles*) en la raíz de la ubicación de Azure Storage.  <br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> O bien:  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |Resulta en mensajes de estado detallados en un archivo de registro. De forma predeterminada, el archivo de registro detallado se denomina AzCopyVerbose.log en %LocalAppData%\Microsoft\Azure\AzCopy. Si especifica una ubicación de archivo existente para esta opción, el registro detallado se anexará a ese archivo.  <br/> No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |Este modificador opcional especifica el modo recursivo para que la herramienta AzCopy copie los archivos PST que se encuentran en las subcarpetas del directorio de origen especificado por el parámetro `/Source:`.  <br/> **Nota:** si incluye este modificador, los archivos PST de las subcarpetas tendrán un nombre de ruta de archivo diferente en la ubicación de Azure Storage una vez cargados. Tendrá que especificar el nombre exacto de la ruta de acceso de archivo en el archivo CSV que cree en el paso 4.  <br/> | `/S` <br/> |
    | `/Y` <br/> |Este modificador necesario permite el uso de tokens de SAS de solo escritura al cargar los archivos PST en la ubicación de Azure Storage. La URL de SAS que ha obtenido en el paso 1 (y especificado en el parámetro `/Dest:`) es una dirección URL de solo escritura de SAS, por lo que debe incluir este modificador. Una dirección URL de SAS de solo escritura no le impedirá usar el Explorador de Azure Storage para ver una lista de los archivos PST cargados en la ubicación de Azure Storage.  <br/> | `/Y` <br/> |

A continuación se muestra un ejemplo de la sintaxis de la herramienta AzCopy.exe, en el que se usan valores reales para cada parámetro:
    
```powershell
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
```

Después de ejecutar el comando, aparecen mensajes de estado en los que se muestra el progreso de la carga de los archivos PST. En un mensaje de estado final aparece el número total de archivos cargados correctamente.

> [!TIP]
> Después de ejecutar correctamente el comando AzCopy.exe y de comprobar que todos los parámetros son correctos, guarde una copia de la sintaxis de la línea de comandos en el mismo archivo (protegido) en el que ha copiado la información obtenida en el paso 1. Luego, puede copiar y pegar este comando en un símbolo del sistema cada vez que quiera ejecutar la herramienta AzCopy.exe para cargar los archivos PST a Office 365. Los únicos valores que puede que deba cambiar son los del parámetro `/Source:`. Esto depende del directorio de origen en el que están los archivos PST.

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Paso 3 (opcional): ver una lista de los archivos PST cargados en Office 365

Como paso opcional, puede instalar y usar el Explorador de Microsoft Azure Storage (una herramienta gratuita de código abierto) para ver la lista de archivos PST que ha cargado en el blob de Azure. Hay dos motivos principales para hacerlo:
  
- Comprobar que los archivos PST de la carpeta compartida o el servidor de archivos de la organización se cargaron correctamente en el blob de Azure.
    
- Comprobar el nombre de archivo (y el nombre de ruta de subcarpeta, si se incluye) de cada archivo PST cargado en el blob de Azure. Esto es útil al crear el archivo de asignación de PST en el paso siguiente, ya que tendrá que especificar el nombre de ruta de la carpeta y el nombre de archivo de todos los archivos PST. Comprobar estos nombres puede ayudar a reducir posibles errores en el archivo de asignación de PST.
    
El Explorador de Microsoft Azure Storage está en versión preliminar.
  
> [!IMPORTANT]
> No puede usar el Explorador de Microsoft Azure Storage para cargar o modificar archivos PST. El único método admitido para importar archivos PST es usar AzCopy. Además, no puede eliminar archivos PST que haya cargado al blob de Azure. Si intenta eliminar un archivo PST, recibirá un error sobre no tener los permisos necesarios. Tenga en cuenta que todos los archivos PST se eliminan automáticamente de su área de almacenamiento de Azure. Si no hay ningún trabajo de importación en curso, los archivos PST del contenedor **ingestiondata** se eliminarán en un plazo de 30 días tras crear el último trabajo de importación.
  
Para instalar el Explorador de Azure Storage y conectarse al área de Azure Storage, haga lo siguiente:
  
1. Descargue e instale la [herramienta Explorador de Microsoft Azure Storage](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
2. Inicie el Explorador de Microsoft Azure Storage.

3. En la página **Seleccionar recurso** del cuadro de diálogo **Conectarse a Azure Storage**, haga clic en **Contenedor de blobs**.
  
4. En la página **Seleccionar método de autenticación**, seleccione la opción **Firma de acceso compartido (SAS)** y haga clic en **Siguiente**.
    
5. En la página **Escriba la información de conexión**, pegue la dirección URL SAS que obtuvo en el paso 1 en el cuadro que hay debajo de Dirección **URL SAS del contenedor de blobs** y haga clic en **Siguiente**. Después de pegar la dirección URL SAS, el cuadro situado debajo de **Nombre para mostrar** se rellena automáticamente con **ingestiondata**.
    
6. En la página **Resumen**, puede revisar la información de conexión y, después, haga clic en **Conectar**.
    
    El contenedor **ingestiondata** está abierto. Contiene los archivos PST que ha cargado en el paso 2. El contenedor **ingestiondata** se encuentra en **Cuentas de almacenamiento** \> **(contenedores vinculados)** \> **Contenedores de blob**. 
  
7. Cuando termine de usar el Explorador de Microsoft Azure Storage, haga clic derecho en **ingestiondata** y, después, en **Desasociar** para desconectarse del área de Azure Storage. En caso contrario, recibirá un error la próxima vez que intente vincularse.
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>Paso 4: crear el archivo de asignación de importación de PST

Después de cargar los archivos PST en la ubicación de Azure Storage de su organización, el siguiente paso consiste en crear un archivo de valores separados por comas (CSV) que especifique los buzones de usuario en los que se importarán los archivos PST. Este archivo CSV se enviará en el paso siguiente, cuando cree un trabajo de importación de archivos PST.
  
1. [Descargue una copia del archivo de asignación de importación de PST](https://go.microsoft.com/fwlink/p/?LinkId=544717).

2. Abra o guarde el archivo CSV en el equipo local. En el ejemplo siguiente se muestra un archivo de asignación de importaciones de archivos PST completado (que se abre en el Bloc de notas). Es mucho más fácil usar Microsoft Excel para editar el archivo CSV.

    ```console
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,PSTFiles,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,PSTFiles,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```

    En la primera fila (o la primera fila de encabezado) del archivo CSV aparecen los parámetros que usará el servicio de importación de PST para importar los archivos PST a los buzones de los usuarios. Los nombres de los parámetros están separados por comas. Cada fila situada debajo de la fila de encabezado representa los valores de parámetro para importar un archivo PST a un buzón específico. Necesita una fila para cada archivo PST al que desee importar un buzón de usuario. Puede tener un máximo de 500 filas en el archivo de asignación CSV. Para importar más de 500 archivos PST, tendrá que crear varios archivos de asignación distintos y varios trabajos de importación en el paso 5.

    > [!NOTE]
    > No cambie nada en la fila de encabezado, ni siquiera los parámetros SharePoint; se ignorarán durante el proceso de importación de PST. Además, no olvide reemplazar los datos de los marcadores de posición del archivo de asignación por los datos reales.

 3. Use la información de la tabla siguiente para rellenar el archivo CSV con la información necesaria.

    | Parámetro | Descripción | Ejemplo |
    |:-----|:-----|:-----|
    | `Workload` <br/> |Especifica el servicio en el que se importarán los datos. Use `Exchange` para importar archivos PST a los buzones de los usuarios.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Especifica la ubicación de la carpeta en la ubicación de Azure Storage en la que ha cargado los archivos PST en el paso 2.  <br/> Si no ha incluido un nombre de subcarpeta opcional en la dirección URL de SAS en el parámetro `/Dest:` del paso 2, deje este parámetro en blanco en el archivo CSV. Si ha incluido un nombre de subcarpeta, especifíquelo en este parámetro (vea el segundo ejemplo). El valor de este parámetro distingue mayúsculas de minúsculas.  <br/> En cualquier caso, *no* incluya "ingestiondata" en el valor del parámetro `FilePath`.  <br/><br/> **Importante:** el uso de mayúsculas y minúsculas del nombre de la ruta de acceso del archivo debe ser el mismo que el usado si ha incluido un nombre de subcarpeta opcional en la dirección URL de SAS en el parámetro `/Dest:` del paso 2. Por ejemplo, si en el paso 2 ha usado `PSTFiles` para el nombre de subcarpeta y, después, `pstfiles` en el parámetro `FilePath` del archivo CSV, se producirá un error en la importación del archivo PST. Asegúrese de usar las mismas mayúsculas y minúsculas en ambas instancias.  <br/> |(se deja en blanco)  <br/> O bien  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |Especifica el nombre del archivo PST que se importará al buzón del usuario. El valor de este parámetro distingue mayúsculas de minúsculas.  <br/> <br/>**Importante:** el uso de mayúsculas y minúsculas del nombre de archivo PST en el archivo CSV debe ser el mismo que el archivo PST cargado en la ubicación de Azure Storage en el paso 2. Por ejemplo, si usa `annb.pst` en el parámetro `Name` del archivo CSV, pero el nombre del archivo PST real es `AnnB.pst`, se producirá un error en la importación de ese archivo PST. Asegúrese de que el nombre del PST en el archivo CSV use las mismas mayúsculas y minúsculas que el archivo PST real.  <br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |Especifica la dirección de correo electrónico del buzón en el que se importará el archivo PST. No puede especificar una carpeta pública porque el servicio de importación de PST no admite la importación de archivos PST a carpetas públicas.  <br/> Para importar un archivo PST a un buzón inactivo, tiene que especificar el GUID del buzón de correo de este parámetro. Para obtener este GUID, ejecute el siguiente comando de PowerShell en Exchange Online:  `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**Nota:** en algunos casos, es posible que tenga varios buzones con la misma dirección de correo electrónico, donde un buzón es un buzón activo y el otro buzón está en un estado de eliminación temporal (o inactivo). En estas situaciones, tiene que especificar el GUID del buzón de correo para identificar exclusivamente el buzón en el que se importa el archivo PST. Para obtener este GUID para los buzones activos, ejecute el siguiente comando de PowerShell: `Get-Mailbox <identity of active mailbox> | FL Guid`. Para obtener el GUID para los buzones eliminados temporalmente (o inactivos), ejecute este comando `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`.  <br/> | `annb@contoso.onmicrosoft.com` <br/> O bien:  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Especifica si se va a importar el archivo PST en el buzón de archivo del usuario. Hay dos opciones:  <br/><br/>**FALSE**: importa el archivo PST en el buzón principal del usuario.  <br/> **TRUE**: importa el archivo PST en el buzón de archivo del usuario. Esto supone que el [buzón de archivo del usuario está habilitado](enable-archive-mailboxes.md). <br/><br/>Si establece este parámetro en `TRUE` y el buzón de archivo del usuario no está habilitado, se producirá un error en la importación para ese usuario. Si falla una importación para un usuario (porque su archivo no está habilitado y esta propiedad se establece en `TRUE`), los demás usuarios en el trabajo de importación no se verán afectados.  <br/>  Si deja este parámetro en blanco, el archivo PST se importa al buzón de correo principal del usuario.  <br/> <br/>**Nota**: para importar un archivo PST a un buzón de archivo basado en la nube para un usuario cuyo buzón de correo principal es local, solo tiene que especificar `TRUE` para este parámetro y especificar la dirección de correo electrónico del buzón local del usuario para el parámetro `Mailbox`.  <br/> | `FALSE` <br/> O bien  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Especifica la carpeta en la que se importa el archivo PST.  <br/> <br/> Si deja este parámetro en blanco, el archivo PST se importará a una carpeta nueva llamada **Importados**, ubicada en el nivel raíz del buzón (el mismo nivel que la Bandeja de entrada y el resto de las carpetas del buzón predeterminadas).  <br/> <br/> Si no especifica `/`, las carpetas y los elementos en el archivo PST se importan en el nivel superior de la estructura de carpetas, en el archivo o el buzón de destino. Si existe una carpeta en el buzón de destino (por ejemplo, carpetas predeterminadas como Bandeja de entrada, Elementos enviados y Elementos eliminados), los elementos en el archivo PST en esa carpeta se combinan en la carpeta existente en el buzón de destino. Por ejemplo, si el archivo PST contiene una carpeta Bandeja de entrada, los elementos de esa carpeta se importarán a la carpeta Bandeja de entrada del buzón de destino. Si estas carpetas no existen en la estructura del buzón de destino, se crearán unas nuevas.  <br/><br/>  Si especifica `/<foldername>`, los elementos y carpetas del archivo PST se importarán a una carpeta llamada *\<foldername\>* . Por ejemplo, si usa `/ImportedPst`, los elementos se importarán a una carpeta llamada **PST importados**. Esta carpeta estará ubicada en el buzón del usuario en el mismo nivel que la carpeta Bandeja de entrada.  <br/><br/> **Sugerencia:** considere la posibilidad de ejecutar algunos lotes de prueba para experimentar este parámetro y determinar la mejor ubicación de la carpeta en la que va a importar los archivos PST.  <br/> |(se deja en blanco)  <br/> O bien  <br/>  `/` <br/> O bien  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Este parámetro opcional especifica un valor numérico de la página de códigos que se usa para importar archivos PST en el formato de archivo ANSI. Este parámetro se usa para importar archivos PST de las organizaciones de chino, japonés y coreano, porque estos idiomas suelen usar un juego de caracteres doble byte (DBCS) para la codificación de caracteres. Si no se usa este parámetro para importar archivos PST de los idiomas que usan DBCS para los nombres de las carpetas de buzón, dichos nombres suelen ser incomprensibles después de la importación.  <br/><br/> Para obtener una lista de los valores compatibles que se pueden usar para este parámetro, vea [Identificadores de página de códigos](/windows/win32/intl/code-page-identifiers).  <br/> <br/>**Nota:** como se ha mencionado anteriormente, se trata de un parámetro opcional y no es necesario incluirlo en el archivo CSV. También puede incluirlo y dejar el valor en blanco para una o varias filas.  <br/> |(se deja en blanco)  <br/> O bien  <br/>  `932` (que es el identificador de página de códigos para ANSI/OEM japonés)  <br/> |
    | `SPFileContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.  <br/> |No aplicable  <br/> |
    | `SPManifestContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.  <br/> |No aplicable  <br/> |
    | `SPSiteUrl` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.  <br/> |No aplicable  <br/> |

## <a name="step-5-create-a-pst-import-job"></a>Paso 5: Crear un trabajo de importación de PST

El siguiente paso consiste en crear el trabajo de importación de PST en el servicio de importación de Microsoft 365. Como se ha explicado anteriormente, usted envía el archivo de asignación de importación de PST que ha creado en el paso 4. Después de crear el trabajo, Microsoft 365 analiza los datos de los archivos PST y, después, le da la oportunidad de filtrar los datos que se importan realmente a los buzones especificados en el archivo de asignación de importación de PST (vea el [Paso 6](#step-6-filter-data-and-start-the-pst-import-job)).
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con las credenciales de una cuenta de administrador de su organización. 

2. En el panel izquierdo del Centro de Seguridad y Cumplimiento, haga clic en **Gobernanza de la información > Importar > Importar archivos PST** .

3. En la página **Importar**, haga clic en ![Agregar icono](../media/ITPro-EAC-AddIcon.gif) **Nuevo trabajo de importación**.

   > [!NOTE]
   > Debe tener asignados los permisos adecuados para tener acceso a la página **Importar** en el Centro de seguridad y cumplimiento para crear un trabajo de importación. Vea la sección **Antes de empezar** para obtener más información. 

4. Escriba un nombre para el trabajo de importación de PST y haga clic en **Siguiente**. Use letras minúsculas, números, guiones y caracteres de subrayado. Las letras en mayúscula no se pueden usar ni se pueden incluir espacios en el nombre.

5. En la página **¿Quiere cargar o enviar datos?**, haga clic en **Cargar los datos** y, después, en **Siguiente**.

    ![Hacer clic en Cargar los datos para crear un trabajo de importación de carga en la red](../media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. En el paso 4, en la página **Importar datos**, marque las casillas **Terminé de cargar mis archivos** y **Tengo acceso al archivo de asignación**, y haga clic en **Siguiente**.

    ![Marcar las dos casillas del paso 4](../media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. En la página **Seleccionar el archivo de asignación**, haga clic en **Seleccionar el archivo de asignación** para enviar el archivo de asignación de CSV que ha creado en el paso 4. 

    ![Hacer clic en Seleccionar el archivo de asignación para enviar el archivo CSV que ha creado para el trabajo de importación](../media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. Cuando el nombre del archivo CSV aparezca en **Asignación del nombre de archivo**, haga clic en **Validar** para comprobar si hay errores en el archivo CSV. 

    ![Hacer clic en Validar para comprobar si hay errores en el archivo CSV](../media/4680999d-5538-4059-b878-2736a5445037.png)
  
    El archivo CSV debe estar validado correctamente para poder crear un trabajo de importación de PST. El nombre del archivo cambia a verde una vez que se ha validado correctamente. Si se produce un error de validación, haga clic en el vínculo **Ver registro**. Se abre un informe de errores de validación, con un mensaje de error para cada fila del archivo que ha fallado.

   > [!NOTE]
   > Como se ha explicado anteriormente, un archivo de asignación puede tener un máximo de 500 de filas. Se producirá un error de validación si el archivo de asignación contiene más de 500 filas. Para importar más de 500 archivos PST, tendrá que crear varios archivos de asignación distintos y varios trabajos de importación.

9. Cuando el archivo de asignación de importación se haya validado correctamente, lea el documento de términos y condiciones y, después, marque la casilla.

10. Haga clic en **Guardar** para enviar el trabajo y, después de crear correctamente el trabajo, haga clic en **Cerrar**. 

    Se muestra una página de estado, con un estado de **Análisis en curso** y el nuevo trabajo de importación se muestra en la lista de la página **Importar archivos PST**. 

11. Haga clic en **Actualizar** ![Icono Actualizar](../media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información de estado que se muestra en la columna **Estado**. Cuando el análisis se haya completado y los datos estén listos para su importación, el estado cambia a **Análisis finalizado**.

    Puede hacer clic en el trabajo de importación para mostrar la página de control flotante de estado, que contiene información más detallada sobre el trabajo de importación, como el estado de todos los archivos PST que aparecen en el archivo de asignación.
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Paso 6: filtrar los datos e iniciar el trabajo de importación de PST

Después de crear e iniciar el trabajo de importación en el paso 5, Microsoft 365 analiza de forma segura los datos de los archivos PST. Esto conlleva identificar la antigüedad de los elementos y los diferentes tipos de mensajes incluidos en los archivos PST. Una vez se haya completado el análisis y los datos estén listos para la importación, tiene la opción de importar todos los datos incluidos en los archivos PST o de recortar solo algunos de ellos, estableciendo filtros para controlar los datos para importar.
  
1. En la página **Importar** en el Centro de seguridad y cumplimiento, haga clic en **Preparado para importar a Office 365** para el trabajo de importación que ha creado en el paso 5. 
    
    ![Haga clic en Preparado para importar a Microsoft 365, junto al trabajo de importación que ha creado.](../media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Se muestra una página de control flotante con información sobre los archivos PST y otra información sobre el trabajo de importación.
    
2. En la página de control flotante, haga clic en **Importar a Office 365**.
    
    Se mostrará la página **Filtrar los datos**. Contiene las información sobre datos resultante del análisis realizado en los archivos PST por Office 365, incluida la antigüedad de los datos. En este momento, tiene la opción de filtrar los datos que se importarán o importar todos los datos tal como estén. 
    
    ![Puede recortar los datos de los archivos PST o importarlos todos](../media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. Realiza una de las siguientes acciones:
    
   1. Para recortar los datos que importa, haga clic en **Sí, quiero filtrarlos antes de importarlos**.
    
      Para obtener instrucciones detalladas paso a paso sobre cómo filtrar los datos en los archivos PST y, después, iniciar el trabajo de importación, vea [Filtrar datos al importar archivos PST a Office 365](filter-data-when-importing-pst-files.md).
    
      O bien:
    
   1. Para importar todos los datos de los archivos PST, haga clic en **No, quiero importarlos todos** y en **Siguiente**.
    
4. Si ha elegido importar todos los datos, haga clic en **Importar datos** para iniciar el trabajo de importación. 
    
   El estado del trabajo de importación se mostrará en la página **importar la página de archivos PST**. Haga clic en el ![icono Actualizar](../media/O365-MDM-Policy-RefreshIcon.gif) **Actualizar** para actualizar la información de estado que se muestra en la columna **Estado**. Haga clic en el trabajo de importación para mostrar la página de control flotante de estado, donde se muestra la información de estado de cada archivo PST que se importa. 


  
## <a name="more-information"></a>Más información

- ¿Por qué importar archivos PST a Microsoft 365?
    
  - Es una buena forma de importar los datos de mensajería de archivo de su organización a Microsoft 365.
    
  - Los datos están disponibles para el usuario en todos los dispositivos, ya que se almacenan en la nube.
    
  - Permite satisfacer las necesidades de cumplimiento de su organización, ya que facilita la aplicación de las características de cumplimiento de Microsoft 365 a los datos de los archivos PST que ha importado. Incluye lo siguiente:
    
  - Habilitar [buzones de archivo](enable-archive-mailboxes.md) y el [archivado de ampliación automática](enable-unlimited-archiving.md) para dar a los usuarios espacio de almacenamiento de buzón adicional para almacenar los datos importados. 
    
  - Colocar los buzones en [Suspensión por litigio](./create-a-litigation-hold.md) para conservar los datos importados. 
    
  - Usar las [herramientas eDiscovery](search-for-content.md) de Microsoft para buscar en los datos importados. 
    
  - Usar [las directivas de retención de Microsoft 365](retention.md) para controlar cuánto tiempo se conservan los datos importados y las acciones que deben realizarse cuando expire el período de retención. 
    
  - Buscar en el [registro de auditoría](search-the-audit-log-in-security-and-compliance.md) eventos relacionados con el buzón que afectan a los datos importados. 
    
  - Importar datos a [buzones de correo inactivos](create-and-manage-inactive-mailboxes.md) para archivar datos por motivos de cumplimiento. 
    
  - Usar [directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) para evitar la pérdida de datos confidenciales fuera de su organización. 
  
- Este es un ejemplo de la dirección URL de la Firma de acceso compartido (SAS) que se ha obtenido en el paso 1. Este ejemplo también contiene la sintaxis del comando que se ejecuta en la herramienta AzCopy.exe para cargar los archivos PST. Asegúrese de tomar precauciones para proteger la URL de SAS de la misma manera que protegería las contraseñas u otra información relacionada con la seguridad.

    ```console
    SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D

    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y

    EXAMPLES

    This example uploads PST files to the root of the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    
    This example uploads PST files to a subfolder named PSTFiles  in the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    ```

- Como se ha explicado anteriormente, el servicio de importación de Office 365 activa la opción de suspensión de retención (durante un período de tiempo indefinido) después de que los archivos PST se importan a un buzón. Esto significa que la propiedad *RetentionHoldEnabled* se establece en **True** para que no se procese la directiva de retención que se asigna al buzón. Esto da al propietario del buzón tiempo para administrar los mensajes recién importados evitando que una directiva de eliminación o de archivado elimine o archive los mensajes más antiguos. Estos son algunos pasos que puede seguir para administrar esta suspensión de retención: 
    
    - Tras un período de tiempo específico, puede desactivar la suspensión de retención al ejecutar el comando **Set-Mailbox-RetentionHoldEnabled $false**. Para obtener instrucciones, vea [Aplicar la suspensión de retención a un buzón](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).
    
   - Puede configurar la suspensión de retención para que esté desactivada en una fecha futura. Para hacerlo, ejecute el comando **Set-Mailbox-EndDateForRetentionHold *date***. Por ejemplo, si damos por sentado que la fecha de hoy es el 1 de junio de 2016 y quiere que la suspensión de retención esté desactivada en un plazo de 30 días, ejecute el comando siguiente: **Set-Mailbox-EndDateForRetentionHold 7/1/2016**. En este escenario, debe dejar la propiedad **RetentionHoldEnabled** configurada en *True*. Para obtener más información, vea [Set-Mailbox](/powershell/module/exchange/set-mailbox).
    
   - Puede cambiar la configuración de la directiva de retención que está asignada a un buzón para que los elementos antiguos importados no se eliminen inmediatamente ni se muevan al buzón de archivo del usuario. Por ejemplo, podría alargar la antigüedad de la retención de una directiva de archivado o eliminación que se asigna al buzón. En este escenario, debe desactivar la suspensión de retención en el buzón de correo después de cambiar la configuración de la directiva de retención. Para obtener más información, vea [Configurar una directiva de archivado y eliminación de buzones en la organización](set-up-an-archive-and-deletion-policy-for-mailboxes.md).

### <a name="how-the-import-process-works"></a>Cómo funciona el proceso de importación
  
Puede usar la opción carga en la red y el servicio de importación de Office 365 para importar archivos PST en bloque a los buzones de usuario. La carga en la red significa que carga los archivos PST en un área de almacenamiento temporal en la nube de Microsoft. Luego, el servicio de importación de Office 365 copia los archivos PST del área de almacenamiento en los buzones de usuario de destino.
  
Aquí se muestra una ilustración y una descripción del proceso de carga en la red para importar archivos PST a buzones de Office 365.
  
![Flujo de trabajo del proceso de carga en la red para importar archivos PST a Office 365](../media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **Descargar la herramienta de importación de PST y la clave en la ubicación de Azure Storage privada**: el primer paso es descargar la herramienta de línea de comandos de AzCopy y una clave de acceso usada para cargar los archivos PST en una ubicación de Azure Storage en la nube de Microsoft. Puede obtenerlas en la página **Importar** en el Centro de seguridad y cumplimiento. La clave (denominada SAS, firma de acceso seguro) le proporciona los permisos necesarios para cargar los archivos PST en una ubicación de Azure Storage privada y segura. Esta clave de acceso es exclusiva para su organización y le ayuda a evitar el acceso no autorizado a archivos PST tras su carga en la nube de Microsoft. Tenga en cuenta que para importar archivos PST su organización no necesita una suscripción a Azure separada. 
    
2. **Cargar los archivos PST en la ubicación de Azure Storage**: el siguiente paso es usar la herramienta AzCopy.exe (descargada en el paso 1) para cargar y almacenar los archivos PST en una ubicación de Azure Storage que se encuentre en el mismo centro de datos regional de Microsoft que su organización. Para poder cargar los archivos PST que quiere importar, estos deben encontrarse en un recurso compartido de archivos o en un servidor de archivos de su organización.
    
    Existe un paso opcional que puede realizar para ver la lista de los archivos PST una vez que se hayan cargado en la ubicación de Azure Storage.
    
3. **Crear un archivo de asignación de importación de PST**: una vez que los archivos PST se hayan cargado en la ubicación de Azure Storage, el siguiente paso es crear un archivo de valores separados por comas (CSV) que especifique los buzones de usuario en los que se importarán los archivos PST. Tenga en cuenta que un archivo PST se puede importar al buzón principal de un usuario o al buzón de archivo. El servicio de importación de Office 365 usa la información del archivo CVS para importar los archivos PST.
    
4. **Crear un trabajo de importación de PST**: el siguiente paso es crear un trabajo de importación de PST en la página **Importar archivos PST** del Centro de seguridad y cumplimiento, y enviar el archivo de asignación de importación de PST creado en el paso anterior. Una vez creado el trabajo de importación, Microsoft 365 analiza los datos de los archivos PST y, después, le permite establecer filtros para controlar los datos que se importan a los buzones especificados en el archivo de asignación de importación de PST. 
    
5. **Filtrar los datos PST que se importarán a los buzones**: después de crear e iniciar el trabajo de importación, Microsoft 365 analiza de forma segura los datos de los archivos PST. Esto conlleva identificar la antigüedad de los elementos y los diferentes tipos de mensajes incluidos en los archivos PST. Una vez se haya completado el análisis y los datos estén listos para la importación, tiene la opción de importar todos los datos incluidos en los archivos PST o de recortar solo algunos de ellos, estableciendo filtros para controlar los datos para importar.
    
6. **Iniciar el trabajo de importación de PST**: tras iniciarse el trabajo de importación, Microsoft 365 usa la información del archivo de asignación para importar los archivos PST desde la ubicación de Azure Storage a los buzones de los usuarios. En la página **Importar archivos PST** del Centro de seguridad y cumplimiento se mostrará la información de estado sobre el trabajo de importación (incluida información individual de cada archivo PST importado). Cuando finalice el trabajo de importación, el estado del trabajo aparecerá como **Completado**.