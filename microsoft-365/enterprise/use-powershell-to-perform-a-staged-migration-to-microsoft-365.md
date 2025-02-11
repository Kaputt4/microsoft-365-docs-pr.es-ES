---
title: Usar PowerShell para realizar una migración preconfigurada a Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 06/07/2022
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: Obtenga información sobre cómo usar PowerShell para mover contenido de un sistema de correo electrónico de origen a lo largo del tiempo mediante una migración preconfigurada a Microsoft 365.
ms.openlocfilehash: be60b6469b8e432728ef174104403900e115e68f
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68191703"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a>Usar PowerShell para realizar una migración preconfigurada a Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede migrar el contenido de los buzones de usuario de un sistema de correo electrónico de origen a Microsoft 365 a lo largo del tiempo mediante una migración preconfigurada.

Este artículo le guiará a través de las tareas necesarias para realizar una migración preconfigurada del correo electrónico con Exchange Online PowerShell. El tema [Lo que necesita saber sobre una migración de correo electrónico preconfigurada](/Exchange/mailbox-migration/what-to-know-about-a-staged-migration) le proporciona información general sobre el proceso de migración. Cuando se sienta cómodo con el contenido de ese artículo, úselo para empezar a migrar los buzones de un sistema de correo electrónico a otro.

> [!NOTE]
> También puede usar el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a> para realizar la migración preconfigurada. Consulte [Realizar una migración provisional del correo electrónico a Microsoft 365](/Exchange/mailbox-migration/perform-a-staged-migration/perform-a-staged-migration).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

Tiempo estimado para finalizar esta tarea: entre 2 y 5 minutos para crear un lote de migración. Después de que haya iniciado el lote de migración, la duración de la migración variará según la cantidad de buzones del lote, el tamaño de cada buzón y la capacidad de red disponible. Para obtener información sobre otros factores que afectan al tiempo que se tarda en migrar buzones a Microsoft 365, consulte [Rendimiento de la migración](/Exchange/mailbox-migration/office-365-migration-best-practices).

You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.

Para usar los cmdlets de Exchange Online PowerShell, deberá iniciar sesión e importar los cmdlets en la sesión local de Windows PowerShell. Consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para obtener instrucciones.

Para obtener una lista completa de los comandos de migración, consulte [Cmdlets de movimiento y migración](/powershell/exchange/).

## <a name="migration-steps"></a>Pasos de la migración

### <a name="step-1-prepare-for-a-staged-migration"></a>Paso 1: Prepararse para una migración preconfigurada

Antes de migrar buzones a Microsoft 365 mediante una migración preconfigurada, hay algunos cambios que debe realizar en el entorno de Exchange.

 **Configure Outlook Anywhere on your on-premises Exchange Server** The email migration service uses Outlook Anywhere (also known as RPC over HTTP), to connect to your on-premises Exchange Server. For information about how to set up Outlook Anywhere for Exchange Server 2007, and Exchange 2003, see the following:

- [Exchange 2007: Cómo habilitar Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))

- [Cómo configurar Outlook Anywhere con Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))

> [!IMPORTANT]
> You must use a certificate issued by a trusted certification authority (CA) with your Outlook Anywhere configuration. Outlook Anywhere can't be configured with a self-signed certificate. For more information, see [How to configure SSL for Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).

 **Opcional: compruebe que puede conectarse a su organización Exchange con Outlook en cualquier lugar** Pruebe con uno de los métodos siguientes para probar la configuración de su conexión.

- Use Outlook desde fuera de la red corporativa para conectarse a su buzón de correo de Exchange local.

- Use el [Analizador de conectividad remota de Microsoft](https://testconnectivity.microsoft.com/) para probar la configuración de conexión. Use las pruebas de Detección automática de Outlook en cualquier lugar (RPC sobre HTTP) o Outlook.

- Ejecute los comandos siguientes en Exchange Online PowerShell:

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 **Establecer permisos** La cuenta de usuario local que usa para conectarse a la organización local de Exchange (también denominada administrador de migración) debe tener los permisos necesarios para acceder a los buzones locales que desea migrar a Microsoft 365. Esta cuenta de usuario se usa al conectarse al sistema de correo electrónico mediante la creación de un punto de conexión de migración más adelante en este procedimiento [Paso 3: Crear un punto de conexión de migración](#step-3-create-a-migration-endpoint).

Para migrar los buzones de correo, el administrador debe tener uno de los siguientes conjuntos de permisos:

- Forme parte del grupo de **administradores de dominio** de Active Directory de la organización local.

    o bien

- Reciba el permiso **FullAccess** para cada buzón local y el permiso **WriteProperty** para modificar la propiedad **TargetAddress** en las cuentas de usuario locales.

    o bien

- Reciba el permiso **ReceiveAs** en la base de datos de buzones local en la que se almacenan los buzones de los usuarios y el permiso **WriteProperty** para modificar la propiedad **TargetAddress** en las cuentas de usuario locales.

Para obtener instrucciones sobre cómo establecer estos permisos, consulte [Asignación de permisos para migrar buzones a Microsoft 365](/Exchange/mailbox-migration/assign-permissions-for-migration).

 **Disable Unified Messaging (UM)** If UM is turned on for the on-premises mailboxes you're migrating, turn off UM before migration. Turn on UM for the mailboxes after migration is complete. For how-to steps, see[disable unified messaging](/previous-versions/office/exchange-server-2007/bb124691(v=exchg.80)).

 **Use la sincronización de directorios para crear nuevos usuarios en Microsoft 365.** La sincronización de directorios se usa para crear todos los usuarios locales de la organización de Microsoft 365.

You need to license the users after they're created. You have 30 days to add licenses after the users are created. For steps to add licenses, see [Step 8: Complete post-migration tasks](#step-8-complete-post-migration-tasks).

 Puede usar la herramienta de sincronización de Microsoft Azure Active Directory (Azure AD) o Microsoft Azure AD Sync Services para sincronizar y crear usuarios locales en Microsoft 365. Una vez que los buzones de correo se migran a Microsoft 365, se administran cuentas de usuario en la organización local y se sincronizan con la organización de Microsoft 365. Para más información, consulte [Integración de Directory](/previous-versions/azure/azure-services/jj573653(v=azure.100)).

### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a>Paso 2: Crear un archivo CSV para un lote de migración preconfigurada

Después de identificar los usuarios cuyos buzones locales desea migrar a Microsoft 365, use un archivo de valores separados por comas (CSV) para crear un lote de migración. Cada fila del archivo CSV,usada por Microsoft 365 para ejecutar la migración, contiene información sobre un buzón local.

> [!NOTE]
> No hay un límite para el número de buzones que puede migrar a Microsoft 365 mediante una migración preconfigurada. El archivo CSV para un lote de migración puede contener un máximo de 2.000 filas. Para migrar más de 2.000 buzones, debe crear archivos CSV adicionales y usar cada archivo para crear un nuevo lote de migración.

 **Atributos admitidos**

The CSV file for a staged migration supports the following three attributes. Each row in the CSV file corresponds to a mailbox and must contain a value for each of these attributes.

|**Atributo**|**Descripción**|**Obligatorio**|
|:-----|:-----|:-----|
|EmailAddress  <br/> |Especifica la dirección de correo electrónico SMTP principal (por ejemplo, pilarp@contoso.com) para los buzones locales.  <br/> Use la dirección SMTP principal para buzones locales y no identificadores de usuario de Microsoft 365. Por ejemplo, si el dominio local se denomina contoso.com pero el dominio de correo electrónico de Microsoft 365 se denomina service.contoso.com, usaría el nombre de dominio contoso.com para las direcciones de correo electrónico en el archivo CSV.  <br/> |Necesario  <br/> |
|Contraseña  <br/> |Contraseña que se va a establecer para el nuevo buzón de Microsoft 365. Las restricciones de contraseña que se aplican a la organización de Microsoft 365 también se aplican a las contraseñas incluidas en el archivo CSV.  <br/> |Opcional  <br/> |
|ForceChangePassword  <br/> |Especifica si un usuario debe cambiar la contraseña la primera vez que inicia sesión en su nuevo buzón de Microsoft 365. Use **True** o **False** como valor de este parámetro. <br/> > [!NOTE]> Si ha implementado una solución de inicio de sesión único (SSO) implantando los servicios de federación de Active Directory (AD FS) o superior en la organización local, debe usar **False** como valor del atributo **ForceChangePassword**.          |Opcional  <br/> |

 **Formato del archivo CSV**

A continuación, se muestra un ejemplo del formato del archivo CSV. En este ejemplo, se migran tres buzones locales a Microsoft 365.

The first row, or header row, of the CSV file lists the names of the attributes, or fields, specified in the rows that follow. Each attribute name is separated by a comma.

```powershell
EmailAddress,Password,ForceChangePassword
pilarp@contoso.com,Pa$$w0rd,False
tobyn@contoso.com,Pa$$w0rd,False
briant@contoso.com,Pa$$w0rd,False
```

Each row under the header row represents one user and supplies the information that will be used to migrate the user's mailbox. The attribute values in each row must be in the same order as the attribute names in the header row.

Use any text editor, or an application like Excel , to create the CSV file. Save the file as a .csv or .txt file.

> [!NOTE]
> If the CSV file contains non-ASCII or special characters, save the CSV file with UTF-8 or other Unicode encoding. Depending on the application, saving the CSV file with UTF-8 or other Unicode encoding can be easier when the system locale of the computer matches the language used in the CSV file.

### <a name="step-3-create-a-migration-endpoint"></a>Paso 3: Crear un extremo de migración

Para migrar el correo electrónico correctamente, Microsoft 365 debe conectarse y comunicarse con el sistema de correo electrónico de origen. Para ello, Microsoft 365 usa un punto de conexión de migración. Para crear un extremo de migración de Outlook en cualquier lugar con PowerShell, para la migración preconfigurada, primero debe [Conectarse a Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

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
> The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option. Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.

#### <a name="verify-it-worked"></a>Compruebe que ha funcionado

En Exchange Online PowerShell, ejecute el siguiente comando para visualizar la información sobre el extremo de migración "StagedEndpoint":

```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a>Paso 4: Crear e iniciar un lote de migración preconfigurada

You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet. This example creates a migration batch called "StagedBatch1" and uses the migration endpoint that was created in the previous step.

```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

En este ejemplo se crea también un lote de migración denominado "StagedBatch1" y se utiliza el extremo de migración que se creó en el paso anterior. Dado que el parámetro _AutoStart_ no está incluido, el lote de migración debe iniciarse manualmente en el panel de migración o mediante el cmdlet **Start-MigrationBatch** . Como se especificó anteriormente, solo puede existir un lote de migración total cada vez.

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

Después de haber migrado correctamente un lote de buzones, se necesita alguna manera para que los usuarios puedan obtener acceso a su correo. Un usuario cuyo buzón de correo se ha migrado ahora tiene un buzón local y otro en Microsoft 365. Los usuarios que tengan un buzón en Microsoft 365 dejarán de recibir correo nuevo en su buzón local.

Dado que no ha terminado con las migraciones, aún no está listo para dirigir a todos los usuarios a Microsoft 365 para su correo electrónico. ¿Qué debe hacer en el caso de las personas que tienen ambos buzones? Lo que puede hacer es cambiar los correos locales que ya ha migrado a usuarios habilitados para correo. Al cambiar de un buzón a un usuario habilitado para correo, puede dirigirlo a Microsoft 365 para su correo electrónico en lugar de ir a su buzón local.

Otra razón importante para convertir buzones locales en usuarios habilitados para correo es conservar las direcciones proxy de los buzones de Microsoft 365 copiando direcciones proxy a los usuarios habilitados para correo. Esto permite administrar los usuarios basados en la nube de la organización local mediante Active Directory. Además, si decide retirar la organización de Exchange Server local después de migrar todos los buzones a Microsoft 365, las direcciones proxy que ha copiado a los usuarios habilitados para correo permanecerán en su Active Directory local.

### <a name="step-6-delete-a-staged-migration-batch"></a>Paso 6: Eliminar un lote de migración preconfigurada

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

### <a name="step7-assign-licenses-to-microsoft-365-users"></a>Paso 7: Asignación de licencias a usuarios de Microsoft 365

Active las cuentas de usuario de Microsoft 365 para las cuentas migradas mediante la asignación de licencias. Si no asigna una licencia, el buzón se deshabilitará cuando finalice el periodo de gracia (30 días). Para asignar una licencia en el Centro de administración de Microsoft 365, consulte [Asignación o anulación de la asignación de licencias](../admin/manage/assign-licenses-to-users.md).

### <a name="step-8-complete-post-migration-tasks"></a>Paso 8: Finalizar las tareas posteriores a la migración

- **Cree un registro DNS de Detección automática para que los usuarios puedan acceder fácilmente a sus buzones.** Después de migrar todos los buzones locales a Microsoft 365, puede configurar un registro DNS de detección automática para su organización de Microsoft 365 para permitir que los usuarios se conecten fácilmente a sus nuevos buzones de Microsoft 365 con Outlook y clientes móviles. Este nuevo registro DNS de detección automática tiene que usar el mismo espacio de nombres que usa para su organización de Microsoft 365. Por ejemplo, si el espacio de nombres basado en la nube es cloud.contoso.com, el registro DNS de Detección automática que se debe crear es autodiscover.cloud.contoso.com.

    Microsoft 365 usa un registro CNAME para implementar el servicio de detección automática para outlook y clientes móviles. El registro CNAME de Detección automática debe contener la información siguiente:

  - **Alias:** autodiscover

  - **Destino:** autodiscover.outlook.com

    Para obtener más información, consulte [Agregar registros DNS para conectar el dominio](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

- **Retire los servidores de Exchange locales.** Después de comprobar que todo el correo electrónico se enruta directamente a los buzones de Microsoft 365 y ya no necesita mantener la organización de correo electrónico local o no tiene previsto implementar una solución de SSO, puede desinstalar Exchange de los servidores y quitar la organización local de Exchange.

> [!NOTE]
> La retirada de Exchange puede tener consecuencias no deseadas. Antes de retirar su organización Exchange local, le recomendamos que se ponga en contacto con el soporte técnico de Microsoft.

Para obtener más información, vea los artículos siguientes:

- [Modificar o quitar Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))

- [Cómo quitar una organización de Exchange 2007](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))

- [Cómo desinstalar Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))
