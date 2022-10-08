---
title: Usar PowerShell para realizar una migración total a Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
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
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: Obtenga información sobre cómo usar PowerShell para mover el contenido de un sistema de correo electrónico de origen a la vez realizando una migración total a Microsoft 365.
ms.openlocfilehash: 798c47584143c108395f14f57ed9c6494c42565f
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68177512"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a>Usar PowerShell para realizar una migración total a Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede migrar el contenido de los buzones de usuario de un sistema de correo electrónico de origen a Microsoft 365 a la vez mediante una migración total. Este artículo le guiará a través de las tareas para una migración total del correo electrónico con Exchange Online PowerShell.

Al revisar el tema [Lo que necesita saber sobre una migración de correo electrónico de transición a Microsoft 365](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration), puede obtener información general sobre el proceso de migración. Cuando se sienta cómodo con el contenido de ese artículo, úselo para empezar a migrar los buzones de un sistema de correo electrónico a otro.

> [!NOTE]
> También puede usar el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a> para realizar una migración total. Consulte [Realizar una migración total del correo electrónico a Microsoft 365](/Exchange/mailbox-migration/cutover-migration-to-office-365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

Tiempo estimado para finalizar esta tarea: entre 2 y 5 minutos para crear un lote de migración. Después de que haya iniciado el lote de migración, la duración de la migración variará según la cantidad de buzones del lote, el tamaño de cada buzón y la capacidad de red disponible. Para obtener información sobre otros factores que afectan al tiempo que se tarda en migrar buzones a Microsoft 365, consulte [Rendimiento de la migración](/Exchange/mailbox-migration/office-365-migration-best-practices).

You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.

Para usar los cmdlets de Exchange Online PowerShell, deberá iniciar sesión e importar los cmdlets en la sesión local de Windows PowerShell. Consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para obtener instrucciones.

Para obtener una lista completa de los comandos de migración, consulte [Cmdlets de movimiento y migración](/powershell/exchange/).

## <a name="migration-steps"></a>Pasos de la migración

### <a name="step-1-prepare-for-a-cutover-migration"></a>Paso 1: Prepararse para una migración total
<a name="BK_Step1"> </a>

- **Agregue la organización de Exchange local como un dominio aceptado de su organización de Microsoft 365.** El servicio de migración usa la dirección SMTP de los buzones locales para crear el identificador de usuario y la dirección de correo electrónico de Microsoft Online Services para los nuevos buzones de Microsoft 365. Se producirá un error en la migración si el dominio de Exchange no es un dominio aceptado o el dominio principal de la organización de Microsoft 365. Para obtener más información, consulte [Comprobación del dominio](../admin/setup/add-domain.md).

- **Configure Outlook Anywhere on your on-premises Exchange server.** The email migration service uses RPC over HTTP, or Outlook Anywhere, to connect to your on-premises Exchange server. For information about how to set up Outlook Anywhere for Exchange 2010, Exchange 2007, and Exchange 2003, see the following:

  - [Exchange 2010: Habilitar Outlook Anywhere](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))

  - [Exchange 2007: Cómo habilitar Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))

  - [Exchange 2003: Situaciones de implementación para RPC a través de HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))

  - [Cómo configurar Outlook Anywhere con Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))

    > [!IMPORTANT]
    > Your Outlook Anywhere configuration must be configured with a certificate issued by a trusted certification authority (CA). It can't be configured with a self-signed certificate. For more information, see [How to Configure SSL for Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).

- **Verify that you can connect to your Exchange organization using Outlook Anywhere.** Try one of these methods to test your connection settings:

  - Utilice Microsoft Outlook desde fuera de la red corporativa para conectarse a su buzón de Exchange local.

  - Use the Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) to test your connection settings. Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.

  - Ejecute los comandos siguientes en Exchange Online PowerShell.

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- **Asigne a una cuenta de usuario local los permisos necesarios para obtener acceso a los buzones de la organización de Exchange.** La cuenta de usuario local que usa para conectarse a la organización local de Exchange (también denominada administrador de migración) debe tener los permisos necesarios para acceder a los buzones locales que desea migrar a Microsoft 365. Esta cuenta de usuario se utiliza para crear un extremo de migración para la organización local.

    En la lista siguiente, se muestran los privilegios administrativos necesarios para migrar buzones con una migración total. Hay tres opciones posibles.

  - El administrador de la migración debe ser miembro del grupo **Administradores del dominio** en Active Directory en la organización local.

    O bien

  - El administrador de la migración debe contar con permiso de **acceso completo** para cada buzón local.

    O bien

  - El administrador de la migración debe tener el permiso **Recibir como** en la base de datos del buzón local que almacena los buzones de usuario.

- **Disable Unified Messaging.** If the on-premises mailboxes you're migrating are enabled for Unified Messaging (UM), you have to disable UM on the mailboxes before you migrate them. You can then enable UM on the mailboxes after the migration is complete.

- **Grupos de seguridad y delegados** El servicio de migración de correo electrónico no puede detectar si Active Directory local grupos son grupos de seguridad o no, por lo que no puede aprovisionar ningún grupo migrado como grupos de seguridad en Microsoft 365. Si desea tener grupos de seguridad en el inquilino de Microsoft 365, primero debe aprovisionar un grupo de seguridad vacío habilitado para correo en el inquilino de Microsoft 365 antes de iniciar la migración de transición. Además, este método de migración solo mueve buzones, usuarios de correo, contactos de correo y grupos habilitados para correo. Si cualquier otro objeto de Active Directory, como el usuario que no se migra a Microsoft 365, se asigna como administrador o delegado a un objeto que se va a migrar, se debe quitar del objeto antes de migrar.

### <a name="step-2-create-a-migration-endpoint"></a>Paso 2: Crear un extremo de migración
<a name="BK_Step2"> </a>

Para migrar el correo electrónico correctamente, Microsoft 365 debe conectarse y comunicarse con el sistema de correo electrónico de origen. Para ello, Microsoft 365 usa un punto de conexión de migración. Para crear un extremo de migración de Outlook en cualquier lugar para la migración total, primero debe [Conectarse a Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

Para obtener una lista completa de los comandos de migración, consulte [Cmdlets de movimiento y migración](/powershell/exchange/).

Ejecute los comandos siguientes en Exchange Online PowerShell:

```powershell
$Credentials = Get-Credential
```

El ejemplo usa el cmdlet [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) para obtener y probar la configuración de conexión al servidor de Exchange local y luego utiliza dicha configuración de conexión para crear el extremo de migración denominado "CutoverEndpoint".

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option. Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.

#### <a name="verify-it-worked"></a>Compruebe que ha funcionado

En Exchange Online PowerShell, ejecute el siguiente comando para visualizar la información sobre el extremo de migración "CutoverEndpoint":

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a>Paso 3: Crear el lote de migración total
<a name="BK_Step3"> </a>

You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet. This example creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

This example also creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step. Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet. As previously stated, only one cutover migration batch can exist at a time.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a>Compruebe que ha funcionado

Para comprobar que se ha creado correctamente un lote de migración para una migración total, ejecute el siguiente comando en Exchange Online PowerShell para visualizar la información sobre el nuevo lote de migración:

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a>Paso 4: Iniciar el lote de migración total

To start the migration batch in Exchange Online PowerShell, run the following command. This will create a migration batch called "CutoverBatch".

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a>Compruebe que ha funcionado

If a migration batch is successfully started, its status on the migration dashboard is specified as Syncing. To verify that you've successfully started a migration batch using Exchange Online PowerShell, run the following command:

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Paso 5: Enrutar el correo electrónico a Microsoft 365

Los sistemas de correo electrónico utilizan un registro DNS denominado registro MX para averiguar dónde entregar los correos electrónicos. Durante el proceso de migración del correo electrónico, el registro MX apuntaba al sistema de correo electrónico de origen. Ahora que se ha completado la migración de correo electrónico a Microsoft 365, es el momento de apuntar el registro MX a Microsoft 365. Esto ayuda a asegurarse de que el correo electrónico se entrega a los buzones de Microsoft 365. Al mover el registro MX, también puede desactivar el sistema de correo electrónico antiguo cuando esté listo.

Para muchos proveedores de DNS, hay instrucciones específicas para Cambiar el registro MX. Si su proveedor de DNS no está incluido o si desea hacerse una idea de las orientaciones generales, también ofrecemos las [instrucciones generales de registro MX](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-an-mx-record-for-email-outlook-exchange-online).

It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: [Step 6: Delete the cutover migration batch](#step-6-delete-the-cutover-migration-batch).

### <a name="step-6-delete-the-cutover-migration-batch"></a>Paso 6: Eliminar el lote de migración total

Después de cambiar el registro MX y comprobar que todo el correo electrónico se enruta a Microsoft 365 buzones, notifique a los usuarios que su correo va a Microsoft 365. Después, puede eliminar el lote de migración total. Compruebe lo siguiente antes de eliminar el lote de migración.

- Todos los usuarios usan buzones de Microsoft 365. Una vez eliminado el lote, el correo enviado a los buzones del Exchange Server local no se copia en los buzones de Microsoft 365 correspondientes.

- Los buzones de Microsoft 365 se sincronizaron al menos una vez después de que el correo empezara a enviarse directamente a ellos. Para ello, asegúrese de que el valor del cuadro Hora de última sincronización del lote de migración es más reciente que cuando el correo comenzó a enrutarse directamente a buzones de Microsoft 365.

Para eliminar el lote de migración "CutoverBatch" en Exchange Online PowerShell, ejecute el comando siguiente.

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a>Sección 7: Asignar licencias de usuario

 **Active las cuentas de usuario de Microsoft 365 para las cuentas migradas mediante la asignación de licencias.** Si no asigna una licencia, el buzón se deshabilitará cuando finalice el periodo de gracia (30 días). Para asignar una licencia en el Centro de administración de Microsoft 365, consulte [Asignación o anulación de la asignación de licencias](../admin/manage/assign-licenses-to-users.md).

### <a name="step-8-complete-post-migration-tasks"></a>Paso 8: Finalizar las tareas posteriores a la migración

- **Cree un registro DNS de Detección automática para que los usuarios puedan acceder fácilmente a sus buzones.** Después de migrar todos los buzones locales a Microsoft 365, puede configurar un registro DNS de detección automática para su organización de Microsoft 365 para permitir que los usuarios se conecten fácilmente a sus nuevos buzones de Microsoft 365 con Outlook y clientes móviles. Este nuevo registro DNS de detección automática tiene que usar el mismo espacio de nombres que usa para su organización de Microsoft 365. Por ejemplo, si el espacio de nombres basado en la nube es cloud.contoso.com, el registro DNS de Detección automática que se debe crear es autodiscover.cloud.contoso.com.

    Si mantiene la Exchange Server, también debe asegurarse de que el registro CNAME de Detección automática de DNS tenga que apuntar a Microsoft 365 en DNS interno y externo después de la migración para que el cliente de Outlook se conecte al buzón correcto.

    > [!NOTE]
    >  En Exchange 2007, Exchange 2010 y Exchange 2013 también debe establecer  `Set-ClientAccessServer AutodiscoverInternalConnectionURI` como `Null`.

    Microsoft 365 usa un registro CNAME para implementar el servicio de detección automática para outlook y clientes móviles. El registro CNAME de Detección automática debe contener la información siguiente:

  - **Alias:** autodiscover

  - **Destino:** autodiscover.outlook.com

    Para obtener más información, consulte [Agregar registros DNS para conectar el dominio](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

- **Retire los servidores de Exchange locales.** Después de comprobar que todo el correo electrónico se enruta directamente a los buzones de Microsoft 365 y ya no necesita mantener la organización de correo electrónico local o no tiene previsto implementar una solución de inicio de sesión único (SSO), puede desinstalar Exchange de los servidores y quitar la organización local de Exchange.

    Para obtener más información, vea los artículos siguientes:

  - [Modificar o quitar Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))

  - [Cómo quitar una organización de Exchange 2007](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))

  - [Cómo desinstalar Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))
