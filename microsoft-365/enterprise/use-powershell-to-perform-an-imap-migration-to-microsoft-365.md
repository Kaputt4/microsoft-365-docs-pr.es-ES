---
title: Usar PowerShell para realizar una migración de IMAP a Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 09/19/2022
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
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: Obtenga información sobre cómo usar PowerShell para realizar una migración del Protocolo de acceso a correo electrónico (IMAP) de Internet a Microsoft 365.
ms.openlocfilehash: e34a4afd18a0e3234d61261ed7504b25b389aacf
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68179249"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a>Usar PowerShell para realizar una migración de IMAP a Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Como parte del proceso de implementación de Microsoft 365, puede optar por migrar el contenido de los buzones de correo de usuario de un servicio de correo electrónico del Protocolo de acceso a correo electrónico de Internet (IMAP) a Microsoft 365. Este artículo le guiará a través de las tareas para migrar el correo electrónico IMAP con Exchange Online PowerShell.

> [!NOTE]
> También puede usar el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a> para realizar una migración IMAP. Consulte [Migración de buzones IMAP](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

Tiempo estimado para finalizar esta tarea: entre 2 y 5 minutos para crear un lote de migración. Después de que haya iniciado el lote de migración, la duración de la migración variará según la cantidad de buzones del lote, el tamaño de cada buzón y la capacidad de red disponible. Para obtener información sobre otros factores que afectan al tiempo que se tarda en migrar buzones a Microsoft 365, consulte [Rendimiento de la migración](/Exchange/mailbox-migration/office-365-migration-best-practices).

You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.

Para usar los cmdlets de Exchange Online PowerShell, deberá iniciar sesión e importar los cmdlets en la sesión local de Windows PowerShell. Consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para obtener instrucciones.

Para obtener una lista completa de los comandos de migración, consulte [Cmdlets de movimiento y migración](/powershell/exchange/).

En las migraciones IMAP existen las restricciones siguientes:

- Only items in a user's inbox or other mail folders can be migrated. You can't migrate contacts, calendar items, or tasks.

- Es posible migrar un máximo de 500.000 elementos desde el buzón de un usuario.

- El tamaño máximo de un mensaje que se puede migrar es de 35 MB.

## <a name="migration-steps"></a>Pasos de la migración

### <a name="step-1-prepare-for-an-imap-migration"></a>Paso 1: Preparar una migración IMAP
<a name="BK_Step1"> </a>

- **Si tiene un dominio para su organización IMAP, agréguelo como un dominio aceptado de su organización de Microsoft 365.** Si desea usar el mismo dominio que ya posee para sus buzones de Microsoft 365, primero debe agregarlo como un dominio aceptado a Microsoft 365. Después de agregarlo, puede crear los usuarios en Microsoft 365. Para obtener más información, consulte[Comprobación del dominio](../admin/setup/add-domain.md).

- **Agregue cada usuario a Microsoft 365 para que tenga un buzón.** Para obtener instrucciones, consulte[Agregar usuarios a Microsoft 365 para empresas](../admin/add-users/add-users.md).

- **Obtain the FQDN of the IMAP server**. You need to provide the fully qualified domain name (FQDN) (also called the full computer name) of the IMAP server that you will migrate mailbox data from when you create an IMAP migration endpoint. Use an IMAP client or the PING command to verify that you can use the FQDN to communicate with the IMAP server over the Internet.

- **Configure the firewall to allow IMAP connections**. You might have to open ports in the firewall of the organization that hosts the IMAP server so network traffic originating from the Microsoft datacenter during the migration is allowed to enter the organization that hosts the IMAP server. For a list of IP addresses used by Microsoft datacenters, see [Exchange Online URLs and IP Address Ranges](./urls-and-ip-address-ranges.md).

- **Assign the administrator account permissions to access mailboxes in your IMAP organization**. If you use administrator credentials in the CSV file, the account that you use must have the necessary permissions to access the on-premises mailboxes. The permissions required to access user mailboxes is determined by the particular IMAP server.

- **Para usar los cmdlets de Exchange Online PowerShell**, deberá iniciar sesión e importar los cmdlets en la sesión local de Windows PowerShell. Consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para obtener instrucciones.

    Para obtener una lista completa de los comandos de migración, consulte [Cmdlets de movimiento y migración](/powershell/exchange/).

- **Verify that you can connect to your IMAP server**. Run the following command in Exchange Online PowerShell to test the connection settings to your IMAP server.

  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    Para el valor del parámetro **Puerto**, es normal usar 143 para las conexiones no cifradas o de Seguridad de la capa de transporte (TLS) y 993 para las conexiones SSL.

### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a>Paso 2: Crear un archivo CSV para un lote de migración IMAP

Identify the group of users whose mailboxes you want to migrate in an IMAP migration batch. Each row in the CSV file contains information necessary to connect to a mailbox in the IMAP messaging system.

Los siguientes son los atributos necesarios para cada usuario:

- **EmailAddress** especifica el identificador de usuario del buzón de Microsoft 365 del usuario.

- **UserName** especifica el nombre de inicio de sesión que usará la cuenta para tener acceso al buzón en el servidor IMAP.

- **Password** especifica la contraseña de la cuenta en la columna **UserName**.

Here's an example of the format for the CSV file. In this example, three mailboxes are migrated:

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

Para el atributo **UserName**, además del nombre de usuario, puede usar las credenciales de una cuenta a la que se hayan asignado los permisos necesarios para tener acceso a los buzones en el servidor IMAP. A continuación, se enumeran algunos de los formatos específicos usados para algunos servidores IMAP:

 **Microsoft Exchange:**

Si va a migrar correo electrónico desde la implementación IMAP de Microsoft Exchange, use el formato **Domain/Admin_UserName/User_UserName** para el atributo **UserName** del archivo CSV. Supongamos que desea migrar el correo electrónico de Exchange de Terry Adams, Ann Beebe y Paul Cannon. Tiene una cuenta de administrador de correo, donde el nombre de usuario es **mailadmin** y la contraseña es **P\@ssw0rd**. Este es el aspecto que tendría el archivo CSV:

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 **Dovecot:**

For IMAP servers that support Simple Authentication and Security Layer (SASL), such as a Dovecot IMAP server, use the format **User_UserName*Admin_UserName**, where the asterisk ( * ) is a configurable separator character. Supongamos que va a migrar el correo electrónico de esos mismos usuarios desde un servidor IMAP de Dovecot con las credenciales de administrador **mailadmin** y **P\@ssw0rd**. Here's what your CSV file would look like:

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 **Mirapoint:**

Si va a migrar correo electrónico desde Mirapoint Message Server, use el formato **#user\@domain#Admin_UserName#** para las credenciales de administrador. Para migrar el correo electrónico desde Mirapoint con las credenciales de administrador **mailadmin** y **P\@ssw0rd**, el archivo CSV tendría este aspecto:

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 **Courier IMAP:**

Algunos sistemas de correo electrónico de origen, como Courier IMAP, no admiten el uso de credenciales de administrador de buzones para migrar buzones a Microsoft 365. En su lugar, puede configurar el sistema de correo electrónico de origen para usar carpetas compartidas virtuales. Si usa carpetas compartidas virtuales, puede usar las credenciales de administrador de buzón para tener acceso a los buzones de usuario en el sistema de correo electrónico de origen. Para obtener más información acerca de cómo configurar las carpetas compartidas virtuales para Courier IMAP, consulte [Carpetas compartidas](https://go.microsoft.com/fwlink/p/?LinkId=398870).

To migrate mailboxes after you set up virtual shared folders on your source email system, you have to include the optional attribute **UserRoot** in the migration file. This attribute specifies the location of each user's mailbox in the virtual shared folder structure on the source email system. For example, the path to Terry's mailbox is /users/terry.adams.

Este es un ejemplo de un archivo CSV que contiene el atributo **UserRoot**:

```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a>Paso 3: Crear un extremo de migración IMAP

Para migrar el correo electrónico correctamente, Microsoft 365 debe conectarse al sistema de correo electrónico de origen y comunicarse con él. Para ello, Microsoft 365 usa un punto de conexión de migración. El extremo de migración también define el número de buzones que se migrará simultáneamente y el número de buzones que se sincronizará simultáneamente durante la sincronización incremental, que se hace una vez cada 24 horas. Para crear un extremo de migración para la migración IMAP, primero debe [Conectarse a Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

Para obtener una lista completa de los comandos de migración, consulte [Cmdlets de movimiento y migración](/powershell/exchange/).

Para crear el extremo de migración IMAP denominado "IMAPEndpoint" en Exchange Online PowerShell, ejecute el comando siguiente:

```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

You can also add parameters to specify concurrent migrations, concurrent incremental migrations, and the port to use. The following Exchange Online PowerShell command creates an IMAP migration endpoint called "IMAPEndpoint" that supports 50 concurrent migrations and up to 25 concurrent incremental synchronizations. It also configures the endpoint to use port 143 for TLS encryption.

```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

Para obtener más información acerca del cmdlet **New-MigrationEndpoint**, consulte [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint)

#### <a name="verify-it-worked"></a>Compruebe que ha funcionado

Ejecute el siguiente comando en Exchange Online PowerShell para visualizar la información acerca de "IMAPEndpoint":

```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a>Paso 4: Crear e iniciar un lote de migración IMAP

You can use the [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) cmdlet to create a migration batch for an IMAP migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then start it afterwards by using the[Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch) cmdlet.

El siguiente comando de Exchange Online PowerShell iniciará automáticamente el lote de migración denominado "IMAPBatch1" usando el extremo IMAP denominado"IMAPEndpoint":

```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a>Compruebe que ha funcionado

Ejecute el [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) para ver información acerca de la "IMAPBatch1":

```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

También puede comprobar que el lote se ha iniciado ejecutando el comando siguiente:

```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Paso 5: Enrutar el correo electrónico a Microsoft 365

Los sistemas de correo electrónico utilizan un registro DNS denominado registro MX para averiguar dónde entregar los correos electrónicos. Durante el proceso de migración del correo electrónico, el registro MX apuntaba al sistema de correo electrónico de origen. Ahora que se ha completado la migración de correo electrónico a Microsoft 365, es el momento de apuntar el registro MX a Microsoft 365. Esto ayuda a asegurarse de que el correo electrónico se entrega a los buzones de Microsoft 365. Al mover el registro MX, también puede desactivar el sistema de correo electrónico antiguo cuando esté listo.

Para muchos proveedores de DNS, hay instrucciones específicas para Cambiar el registro MX. Si su proveedor de DNS no está incluido o si desea hacerse una idea de las orientaciones generales, también ofrecemos las [instrucciones generales de registro MX](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-an-mx-record-for-email-outlook-exchange-online).

It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: Step 6: Delete IMAP migration batch.

### <a name="step-6-delete-imap-migration-batch"></a>Paso 6: Eliminar el lote de migración IMAP

Después de cambiar el registro MX y comprobar que todo el correo electrónico se enruta a Microsoft 365 buzones, notifique a los usuarios que su correo va a Microsoft 365. Después, puede eliminar el lote de migración IMAP. Compruebe lo siguiente antes de eliminar el lote de migración.

- Todos los usuarios usan buzones de Microsoft 365. Una vez eliminado el lote, el correo enviado a los buzones del Exchange Server local no se copia en los buzones de Microsoft 365 correspondientes.

- Los buzones de Microsoft 365 se sincronizaron al menos una vez después de que el correo empezara a enviarse directamente a ellos. Para ello, asegúrese de que el valor del cuadro Hora de última sincronización del lote de migración es más reciente que cuando el correo comenzó a enrutarse directamente a buzones de Microsoft 365.

Para eliminar el lote de migración "IMAPBatch1" de Exchange Online PowerShell, ejecute el comando siguiente:

```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

Para obtener más información sobre el cmdlet **Remove-MigrationBatch**, consulte [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).

#### <a name="verify-it-worked"></a>Compruebe que ha funcionado

Ejecute el comando siguiente en Exchange Online PowerShell para visualizar la información sobre "IMAPBatch1":

```powershell
Get-MigrationBatch IMAPBatch1"
```

El comando devolverá el lote de migración con un estado **Quitando** o devolverá un error indicando que el lote de migración no se ha encontrado, lo que demuestra que el lote se ha eliminado.

Para obtener más información sobre el cmdlet **Get-MigrationBatch**, consulte [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).

## <a name="see-also"></a>Consulte también

[Solucionador de problemas de migración IMAP](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)
