---
title: Usar PowerShell para realizar una migración preconfigurada a Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: Obtenga información sobre cómo usar PowerShell para mover contenido de un sistema de correo electrónico de origen con el tiempo mediante una migración por fases a Microsoft 365.
ms.openlocfilehash: 0c93de181c54fb1c4021d23d787b63577317aad4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924797"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a>Usar PowerShell para realizar una migración preconfigurada a Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede migrar el contenido de los buzones de usuario de un sistema de correo electrónico de origen a Microsoft 365 con el tiempo mediante una migración por fases.
  
Este artículo le guiará a través de las tareas necesarias para realizar una migración preconfigurada del correo electrónico con Exchange Online PowerShell. El tema What [you need to know about a staged email migration](/Exchange/mailbox-migration/what-to-know-about-a-staged-migration), le ofrece información general sobre el proceso de migración. Cuando se sienta cómodo con el contenido de ese artículo, úselo para empezar a migrar los buzones de un sistema de correo electrónico a otro.
  
> [!NOTE]
> También puede usar el centro de administración de Exchange para realizar una migración preconfigurada. Vea [Realizar una migración por fases de correo electrónico a Microsoft 365](/Exchange/mailbox-migration/perform-a-staged-migration/perform-a-staged-migration). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

Tiempo estimado para finalizar esta tarea: entre 2 y 5 minutos para crear un lote de migración. Después de que haya iniciado el lote de migración, la duración de la migración variará según la cantidad de buzones del lote, el tamaño de cada buzón y la capacidad de red disponible. Para obtener información sobre otros factores que afectan al tiempo que se tarda en migrar buzones a Microsoft 365, vea [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).
  
Deberá tener permisos asignados para poder llevar a cabo estos procedimientos. Para ver qué permisos necesita, consulte la sección "Movimiento de buzón y permisos de migración" en el tema [Permisos de destinatarios](/exchange/recipients-permissions-exchange-2013-help).
  
Para usar los cmdlets de Exchange Online PowerShell, deberá iniciar sesión e importar los cmdlets en la sesión local de Windows PowerShell. Consulte [Conectarse a Exchange Online mediante PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell) para obtener instrucciones.
  
Para obtener una lista completa de los comandos de migración, consulte [Cmdlets de movimiento y migración](/powershell/exchange/).
  
## <a name="migration-steps"></a>Pasos de la migración

### <a name="step-1-prepare-for-a-staged-migration"></a>Paso 1: Prepararse para una migración preconfigurada

Antes de migrar buzones a Microsoft 365 mediante una migración por fases, hay algunos cambios que debe realizar en el entorno de Exchange.
  
 **Configure Outlook en cualquier lugar en su Exchange Server** local El servicio de migración de correo electrónico utiliza Outlook en cualquier lugar (también conocido como RPC sobre HTTP) para conectarse a su Exchange Server local. Para obtener información acerca de cómo configurar Outlook en cualquier lugar para Exchange Server 2007 y Exchange 2003, consulte los temas siguientes:
  
- [Exchange 2007: Cómo habilitar Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))
    
- [Cómo configurar Outlook Anywhere con Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))
    
> [!IMPORTANT]
> Debe usar un certificado emitido por una entidad de certificación (CA) de confianza con su configuración de Outlook en cualquier lugar. Outlook en cualquier lugar no se puede configurar con un certificado autofirmado. Para obtener más información, consulte [Cómo configurar SSL para Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)). 
  
 **Opcional: compruebe que puede conectarse a su organización Exchange con Outlook en cualquier lugar** Pruebe con uno de los métodos siguientes para probar la configuración de su conexión.
  
- Use Outlook desde fuera de la red corporativa para conectarse a su buzón de correo de Exchange local.
    
- Use el [Analizador de conectividad remota de Microsoft](https://https://testconnectivity.microsoft.com/) para probar la configuración de conexión. Use las pruebas de Detección automática de Outlook en cualquier lugar (RPC sobre HTTP) o Outlook.
    
- Ejecute los comandos siguientes en Exchange Online PowerShell:
    
  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 **Establecer permisos** La cuenta de usuario local que use para conectarse a la organización local de Exchange (también denominada administrador de migración) debe tener los permisos necesarios para tener acceso a los buzones locales que desea migrar a Microsoft 365. Esta cuenta de usuario se utiliza cuando se conecta a su sistema de correo electrónico creando un extremo de migración más adelante en este procedimiento ([Paso 3: Crear un extremo de migración](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint) ).
  
Para migrar los buzones de correo, el administrador debe tener uno de los siguientes conjuntos de permisos:
  
- Forme parte del grupo de **administradores de dominio** de Active Directory de la organización local.
    
    o bien
    
- Reciba el permiso **FullAccess** para cada buzón local y el permiso **WriteProperty** para modificar la propiedad **TargetAddress** en las cuentas de usuario locales.
    
    o bien
    
- Reciba el permiso **ReceiveAs** en la base de datos de buzones local en la que se almacenan los buzones de los usuarios y el permiso **WriteProperty** para modificar la propiedad **TargetAddress** en las cuentas de usuario locales.
    
Para obtener instrucciones sobre cómo establecer estos permisos, vea Asignar permisos para migrar [buzones a Microsoft 365](/Exchange/mailbox-migration/assign-permissions-for-migration).
  
 **Deshabilitar mensajería unificada (UM)** Si la mensajería unificada está activada para los buzones locales que se van a migrar, desactive la mensajería unificada antes de la migración. Active la mensajería unificada para los buzones una vez completada la migración. Para obtener información sobre procedimientos, consulte [Cómo deshabilitar la mensajería unificada para un usuario](/previous-versions/office/exchange-server-2007/bb124691(v=exchg.80)).
  
 **Use la sincronización de directorios para crear nuevos usuarios en Microsoft 365.** La sincronización de directorios se usa para crear todos los usuarios locales de la organización de Microsoft 365.
  
Debe autorizar a los usuarios después de crearlos. Dispone de 30 días para agregar licencias después de haber creado los usuarios. Para conocer los pasos para agregar licencias, consulte [Paso 8: Finalizar las tareas posteriores a la migración](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration).
  
 Puede usar la Herramienta de sincronización de Microsoft Azure Active Directory (Azure AD) o los Servicios de sincronización de Microsoft Azure AD para sincronizar y crear usuarios locales en Microsoft 365. Una vez que los buzones se migran a Microsoft 365, se administran cuentas de usuario en la organización local y se sincronizan con la organización de Microsoft 365. Para más información, consulte [Integración de Directory](/previous-versions/azure/azure-services/jj573653(v=azure.100)).
  
### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a>Paso 2: Crear un archivo CSV para un lote de migración preconfigurada

Después de identificar los usuarios cuyos buzones locales desea migrar a Microsoft 365, use un archivo de valores separados por comas (CSV) para crear un lote de migración. Cada fila del archivo CSV ,usada por Microsoft 365 para ejecutar la migración, contiene información sobre un buzón local. 
  
> [!NOTE]
> No hay un límite para el número de buzones que puede migrar a Microsoft 365 mediante una migración por fases. El archivo CSV para un lote de migración puede contener un máximo de 2.000 filas. Para migrar más de 2.000 buzones, debe crear archivos CSV adicionales y usar cada archivo para crear un nuevo lote de migración. 
  
 **Atributos admitidos**
  
El archivo CSV para una migración preconfigurada es compatible con los tres atributos siguientes. Cada fila del archivo CSV corresponde a un buzón y debe contener un valor para cada uno de estos atributos.
  
|**Atributo**|**Descripción**|**Obligatorio**|
|:-----|:-----|:-----|
|EmailAddress  <br/> |Especifica la dirección de correo electrónico SMTP principal (por ejemplo, pilarp@contoso.com) para los buzones locales.  <br/> Use la dirección SMTP principal para los buzones locales y no los id. de usuario de Microsoft 365. Por ejemplo, si el dominio local se denomina contoso.com pero el dominio de correo electrónico de Microsoft 365 se denomina service.contoso.com, usaría el nombre de dominio contoso.com para las direcciones de correo electrónico del archivo CSV.  <br/> |Necesario  <br/> |
|Contraseña  <br/> |La contraseña que se establecerá para el nuevo buzón de Microsoft 365. Las restricciones de contraseña que se aplican a su organización de Microsoft 365 también se aplican a las contraseñas incluidas en el archivo CSV.  <br/> |Opcional  <br/> |
|ForceChangePassword  <br/> |Especifica si un usuario debe cambiar la contraseña la primera vez que inicie sesión en su nuevo buzón de Microsoft 365. Use **True** o **False** como valor de este parámetro. <br/> > [!NOTE]> Si ha implementado una solución de inicio de sesión único (SSO) implantando los servicios de federación de Active Directory (AD FS) o superior en la organización local, debe usar **False** como valor del atributo **ForceChangePassword**.          |Opcional  <br/> |
   
 **Formato del archivo CSV**
  
A continuación, se muestra un ejemplo del formato del archivo CSV. En este ejemplo, se migran tres buzones locales a Microsoft 365.
  
En la primera fila, o fila de encabezado, del archivo CSV se enumeran los nombres de los atributos, o campos, especificados en las filas que le siguen. Los nombres de atributo se separan con una coma.
  
```powershell
EmailAddress,Password,ForceChangePassword 
pilarp@contoso.com,Pa$$w0rd,False 
tobyn@contoso.com,Pa$$w0rd,False 
briant@contoso.com,Pa$$w0rd,False 
```

Cada fila que hay bajo la fila de encabezado representa a un usuario y proporciona la información que se usará para migrar el buzón del usuario. Los valores de atributo de cada fila deben seguir el mismo orden que los nombres de atributo de la fila de encabezado. 
  
Use cualquier editor de texto, o bien una aplicación como Excel para crear el archivo CSV. Guarde el archivo como .csv o .txt.
  
> [!NOTE]
> Si el archivo CSV contiene caracteres especiales o que no son ASCII, guárdelo con codificación UTF-8 o con otra codificación Unicode. Según la aplicación, puede resultar más fácil guardar el archivo CSV con codificación UTF-8 u otra codificación Unicode si la configuración regional del equipo coincide con el idioma utilizado en el archivo CSV. 
  
### <a name="step-3-create-a-migration-endpoint"></a>Paso 3: Crear un extremo de migración
<a name="BK_Endpoint"> </a>

Para migrar correo electrónico correctamente, Microsoft 365 debe conectarse y comunicarse con el sistema de correo electrónico de origen. Para ello, Microsoft 365 usa un extremo de migración. Para crear un extremo de migración de Outlook en cualquier lugar con PowerShell, para la migración preconfigurada, primero debe [Conectarse a Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). 
  
Para obtener una lista completa de los comandos de migración, consulte [Cmdlets de movimiento y migración](/powershell/exchange/).
  
Para crear un extremo de migración de Outlook en cualquier lugar denominado "StagedEndpoint" en Exchange Online PowerShell, ejecute estos comandos:
  
```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

Para obtener más información acerca del cmdlet **New-MigrationEndpoint**, consulte [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint)
  
> [!NOTE]
> El cmdlet **New-MigrationEndpoint** puede usarse para especificar la base de datos que debe usar el servicio con la opción **-TargetDatabase**. Si no se hace, se asigna aleatoriamente una base de datos desde el sitio de Servicios de federación de Active Directory (AD FS) 2.0 donde se encuentra el buzón de administración.
  
#### <a name="verify-it-worked"></a>Compruebe que ha funcionado

En Exchange Online PowerShell, ejecute el siguiente comando para visualizar la información sobre el extremo de migración "StagedEndpoint":
  
```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a>Paso 4: Crear e iniciar un lote de migración preconfigurada
<a name="BK_Endpoint"> </a>

Puede utilizar el cmdlet **New-MigrationBatch** en Exchange Online PowerShell para crear un lote de migración para una migración de traslado. Puede crear un lote de migración e iniciarlo automáticamente mediante la inclusión del parámetro _AutoStart_. O bien puede crear el lote de migración y, luego, iniciarlo posteriormente de forma manual mediante el uso del cmdlet **Start-MigrationBatch**. En este ejemplo se crea un lote de migración denominado "StagedBatch1" y se utiliza el extremo de migración que se creó en el paso anterior.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

En este ejemplo se crea también un lote de migración denominado "StagedBatch1" y se utiliza el extremo de migración que se creó en el paso anterior. Dado que no se incluye el parámetro  _AutoStart_, el lote de migración debe iniciarse manualmente en el panel Migración o con el cmdlet **Start-MigrationBatch**. Como se especificó anteriormente, solo puede existir un lote de migración total cada vez.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a>Compruebe que ha funcionado

Ejecute el siguiente comando en Exchange Online PowerShell para visualizar la información sobre "StagedBatch1":
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

También puede comprobar que el lote se ha iniciado ejecutando el comando siguiente:
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

Para obtener más información sobre el cmdlet **Get-MigrationBatch**, consulte [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).
  
### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a>Paso 5: Convertir los buzones locales en usuarios habilitados para correo electrónico
<a name="BK_Endpoint"> </a>

Después de haber migrado correctamente un lote de buzones, se necesita alguna manera para que los usuarios puedan obtener acceso a su correo. Un usuario cuyo buzón se ha migrado ahora tiene un buzón local y otro en Microsoft 365. Los usuarios que tienen un buzón en Microsoft 365 dejarán de recibir correo nuevo en su buzón local. 
  
Dado que no ha terminado con las migraciones, aún no está listo para dirigir a todos los usuarios a Microsoft 365 para su correo electrónico. ¿Qué debe hacer en el caso de las personas que tienen ambos buzones? Lo que puede hacer es cambiar los correos locales que ya ha migrado a usuarios habilitados para correo. Al cambiar de un buzón a un usuario habilitado para correo, puede dirigir el usuario a Microsoft 365 para su correo electrónico en lugar de ir a su buzón local. 
  
Otro motivo importante para convertir buzones locales en usuarios habilitados para correo es conservar las direcciones proxy de los buzones de Microsoft 365 copiando direcciones proxy a los usuarios habilitados para correo. Esto permite administrar los usuarios basados en la nube de la organización local mediante Active Directory. Además, si decide retirar la organización de Exchange Server local después de migrar todos los buzones a Microsoft 365, las direcciones proxy que haya copiado a los usuarios habilitados para correo permanecerán en su Active Directory local.
    
### <a name="step-6-delete-a-staged-migration-batch"></a>Paso 6: Eliminar un lote de migración preconfigurada
<a name="BK_Endpoint"> </a>

 Cuando haya migrado correctamente todos los buzones de un lote de migración y haya convertido los buzones locales del lote en usuarios habilitados para correo, ya estará listo para eliminar un lote de migración preconfigurada. Asegúrese de comprobar que el correo se reenvía a los buzones de Microsoft 365 en el lote de migración. Cuando elimina un lote de migración preconfigurada, el servicio de migración limpia todos los registros relacionados con el lote de migración y elimina dicho lote.
  
Para eliminar el lote de migración "StagedBatch1" en Exchange Online PowerShell, ejecute el comando siguiente.
  
```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

Para obtener más información sobre el cmdlet **Remove-MigrationBatch**, consulte [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).
  
#### <a name="verify-it-worked"></a>Compruebe que ha funcionado

Ejecute el comando siguiente en Exchange Online PowerShell para visualizar la información sobre "IMAPBatch1":
  
```powershell
Get-MigrationBatch StagedBatch1
```

El comando devolverá el lote de migración con un estado **Quitando** o devolverá un error indicando que el lote de migración no se ha encontrado, lo que demuestra que el lote se ha eliminado.
  
Para obtener más información sobre el cmdlet **Get-MigrationBatch**, consulte [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).
  
### <a name="step7-assign-licenses-to-microsoft-365-users"></a>Paso 7: Asignar licencias a usuarios de Microsoft 365
<a name="BK_Endpoint"> </a>

Active las cuentas de usuario de Microsoft 365 para las cuentas migradas mediante la asignación de licencias. Si no asigna una licencia, el buzón se deshabilitará cuando finalice el periodo de gracia (30 días). Para asignar una licencia en el Centro de administración de Microsoft 365, vea Asignar o [desasignación de licencias.](../admin/manage/assign-licenses-to-users.md)
  
### <a name="step-8-complete-post-migration-tasks"></a>Paso 8: Finalizar las tareas posteriores a la migración
<a name="BK_Postmigration"> </a>

- **Cree un registro DNS de Detección automática para que los usuarios puedan acceder fácilmente a sus buzones.** Después de migrar todos los buzones locales a Microsoft 365, puede configurar un registro DNS de detección automática para su organización de Microsoft 365 para permitir a los usuarios conectarse fácilmente a sus nuevos buzones de Microsoft 365 con Outlook y clientes móviles. Este nuevo registro DNS de detección automática debe usar el mismo espacio de nombres que está usando para su organización de Microsoft 365. Por ejemplo, si el espacio de nombres basado en la nube es cloud.contoso.com, el registro DNS de Detección automática que se debe crear es autodiscover.cloud.contoso.com.
    
    Microsoft 365 usa un registro CNAME para implementar el servicio de detección automática para outlook y clientes móviles. El registro CNAME de Detección automática debe contener la información siguiente:
    
  - **Alias:** autodiscover
    
  - **Destino:** autodiscover.outlook.com
    
    Para obtener más información, vea [Agregar registros DNS para conectar el dominio.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
- **Retire los servidores de Exchange locales.** Después de comprobar que todo el correo electrónico se enruta directamente a los buzones de Microsoft 365 y ya no necesita mantener la organización de correo electrónico local o no tiene previsto implementar una solución de SSO, puede desinstalar Exchange de los servidores y quitar la organización de Exchange local.
    
    Para obtener más información, vea los artículos siguientes:
    
  - [Modificar o quitar Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))
    
  - [Cómo quitar una organización de Exchange 2007](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))
    
  - [Cómo desinstalar Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))
