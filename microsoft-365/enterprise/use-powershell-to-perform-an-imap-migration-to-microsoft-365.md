---
title: Usar PowerShell para realizar una migración de IMAP a Microsoft 365
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
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: Obtenga información sobre cómo usar PowerShell para realizar una migración del Protocolo de acceso al correo de Internet (IMAP) a Microsoft 365.
ms.openlocfilehash: 67621ecfca7ec323a73b91a530f848dd7571f9b2
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464449"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a><span data-ttu-id="5f134-103">Usar PowerShell para realizar una migración de IMAP a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f134-103">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>

<span data-ttu-id="5f134-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="5f134-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5f134-105">Como parte del proceso de implementación de Microsoft 365, puede elegir migrar el contenido de los buzones de usuario de un servicio de correo electrónico de Protocolo de acceso al correo de Internet (IMAP) a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f134-105">As part of the process of deploying Microsoft 365, you can choose to migrate the contents of user mailboxes from an Internet Mail Access Protocol (IMAP) email service to Microsoft 365.</span></span> <span data-ttu-id="5f134-106">Este artículo le guiará a través de las tareas para migrar el correo electrónico IMAP con Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f134-106">This article walks you through the tasks for an email IMAP migration by using Exchange Online PowerShell.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5f134-107">También puede usar el centro de administración de Exchange para realizar una migración IMAP.</span><span class="sxs-lookup"><span data-stu-id="5f134-107">You can also use the Exchange admin center to perform an IMAP migration.</span></span> <span data-ttu-id="5f134-108">Vea [Migrar los buzones IMAP.](https://go.microsoft.com/fwlink/p/?LinkId=536685)</span><span class="sxs-lookup"><span data-stu-id="5f134-108">See [Migrate your IMAP mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=536685).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5f134-109">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="5f134-109">What do you need to know before you begin?</span></span>

<span data-ttu-id="5f134-110">Tiempo estimado para finalizar esta tarea: entre 2 y 5 minutos para crear un lote de migración.</span><span class="sxs-lookup"><span data-stu-id="5f134-110">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="5f134-111">Después de que haya iniciado el lote de migración, la duración de la migración variará según la cantidad de buzones del lote, el tamaño de cada buzón y la capacidad de red disponible.</span><span class="sxs-lookup"><span data-stu-id="5f134-111">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="5f134-112">Para obtener información sobre otros factores que afectan al tiempo que se tarda en migrar buzones a Microsoft 365, vea [Rendimiento de la migración.](https://go.microsoft.com/fwlink/p/?LinkId=275079)</span><span class="sxs-lookup"><span data-stu-id="5f134-112">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span></span>
  
<span data-ttu-id="5f134-p104">Deberá tener permisos asignados para poder llevar a cabo estos procedimientos. Para ver qué permisos necesita, consulte la entrada "Movimiento de buzón y permisos de migración" en una tabla del tema [Permisos de destinatarios](https://go.microsoft.com/fwlink/p/?LinkId=534105).</span><span class="sxs-lookup"><span data-stu-id="5f134-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](https://go.microsoft.com/fwlink/p/?LinkId=534105) topic.</span></span>
  
<span data-ttu-id="5f134-p105">Para usar los cmdlets de Exchange Online PowerShell, deberá iniciar sesión e importar los cmdlets en la sesión local de Windows PowerShell. Consulte [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=534121) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="5f134-p105">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
  
<span data-ttu-id="5f134-117">Para obtener una lista completa de los comandos de migración, consulte [Cmdlets de movimiento y migración](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="5f134-117">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="5f134-118">En las migraciones IMAP existen las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5f134-118">The following restrictions apply to IMAP migrations:</span></span>
  
- <span data-ttu-id="5f134-p106">Solo es posible migrar elementos de la bandeja de entrada o de otras carpetas de correo de un usuario. No se pueden migrar los contactos, los elementos de calendario ni las tareas.</span><span class="sxs-lookup"><span data-stu-id="5f134-p106">Only items in a user's inbox or other mail folders can be migrated. You can't migrate contacts, calendar items, or tasks.</span></span>
    
- <span data-ttu-id="5f134-121">Es posible migrar un máximo de 500.000 elementos desde el buzón de un usuario.</span><span class="sxs-lookup"><span data-stu-id="5f134-121">A maximum of 500,000 items can be migrated from a user's mailbox.</span></span>
    
- <span data-ttu-id="5f134-122">El tamaño máximo de un mensaje que se puede migrar es de 35 MB.</span><span class="sxs-lookup"><span data-stu-id="5f134-122">The maximum message size that can be migrated is 35 MB.</span></span>
    
## <a name="migration-steps"></a><span data-ttu-id="5f134-123">Pasos de la migración</span><span class="sxs-lookup"><span data-stu-id="5f134-123">Migration steps</span></span>

### <a name="step-1-prepare-for-an-imap-migration"></a><span data-ttu-id="5f134-124">Paso 1: Preparar una migración IMAP</span><span class="sxs-lookup"><span data-stu-id="5f134-124">Step 1: Prepare for an IMAP migration</span></span>
<span data-ttu-id="5f134-125"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="5f134-125"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="5f134-126">**Si tiene un dominio para su organización IMAP, agrégrelo como un dominio aceptado de su organización de Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="5f134-126">**If you have a domain for you IMAP organization, add it as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="5f134-127">Si desea usar el mismo dominio que ya posee para sus buzones de Microsoft 365, primero debe agregarlo como un dominio aceptado a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f134-127">If you want to use the same domain you already own for your Microsoft 365 mailboxes, you first have to add it as an accepted domain to Microsoft 365.</span></span> <span data-ttu-id="5f134-128">Después de agregarlo, puede crear los usuarios en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f134-128">After you have added it, you can create your users in Microsoft 365.</span></span> <span data-ttu-id="5f134-129">Para obtener más información, vea[Comprobar el dominio.](https://go.microsoft.com/fwlink/p/?LinkId=534110)</span><span class="sxs-lookup"><span data-stu-id="5f134-129">For more information, see[Verify your domain](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span></span>
    
- <span data-ttu-id="5f134-130">**Agregue cada usuario a Microsoft 365 para que tenga un buzón.**</span><span class="sxs-lookup"><span data-stu-id="5f134-130">**Add each user to Microsoft 365 so that they have a mailbox.**</span></span> <span data-ttu-id="5f134-131">Para obtener instrucciones,[consulte Agregar usuarios a Microsoft 365 para empresas.](https://go.microsoft.com/fwlink/p/?LinkId=535065)</span><span class="sxs-lookup"><span data-stu-id="5f134-131">For instructions, see[Add users to Microsoft 365 for business](https://go.microsoft.com/fwlink/p/?LinkId=535065).</span></span>
    
- <span data-ttu-id="5f134-p109">**Obtenga el FQDN del servidor IMAP**. Debe indicar el nombre de dominio completo (FQDN) (también denominado nombre de equipo completo) del servidor IMAP desde el que migrará los datos de buzones al crear un extremo de migración IMAP. Use un cliente IMAP o el comando PING para comprobar si puede usar el FQDN para comunicarse a través de Internet con el servidor IMAP.</span><span class="sxs-lookup"><span data-stu-id="5f134-p109">**Obtain the FQDN of the IMAP server**. You need to provide the fully qualified domain name (FQDN) (also called the full computer name) of the IMAP server that you will migrate mailbox data from when you create an IMAP migration endpoint. Use an IMAP client or the PING command to verify that you can use the FQDN to communicate with the IMAP server over the Internet.</span></span>
    
- <span data-ttu-id="5f134-p110">**Configure el servidor de seguridad para permitir las conexiones IMAP**. Es posible que deba abrir puertos en el servidor de seguridad de la organización que hospeda el servidor IMAP para que el tráfico de red con origen en el centro de datos de Microsoft durante la migración pueda entrar en la organización que hospeda el servidor IMAP. Para obtener una lista de direcciones IP utilizadas por los centros de datos de Microsoft, consulte [Direcciones URL e intervalos de direcciones IP de Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=535066).</span><span class="sxs-lookup"><span data-stu-id="5f134-p110">**Configure the firewall to allow IMAP connections**. You might have to open ports in the firewall of the organization that hosts the IMAP server so network traffic originating from the Microsoft datacenter during the migration is allowed to enter the organization that hosts the IMAP server. For a list of IP addresses used by Microsoft datacenters, see [Exchange Online URLs and IP Address Ranges](https://go.microsoft.com/fwlink/p/?LinkId=535066).</span></span>
    
- <span data-ttu-id="5f134-p111">**Asigne al administrador permisos de cuenta para tener acceso a los buzones de su organización IMAP**. Si utiliza credenciales de administrador en el archivo CSV, la cuenta que utilice debe tener los permisos necesarios para tener acceso a los buzones locales. Cada servidor IMAP determina los permisos necesarios para tener acceso a los buzones de usuario.</span><span class="sxs-lookup"><span data-stu-id="5f134-p111">**Assign the administrator account permissions to access mailboxes in your IMAP organization**. If you use administrator credentials in the CSV file, the account that you use must have the necessary permissions to access the on-premises mailboxes. The permissions required to access user mailboxes is determined by the particular IMAP server.</span></span> 
    
- <span data-ttu-id="5f134-p112">**Para usar los cmdlets de Exchange Online PowerShell**, deberá iniciar sesión e importar los cmdlets en la sesión local de Windows PowerShell. Consulte [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=534121) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="5f134-p112">**To use the Exchange Online PowerShell cmdlets**, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
    
    <span data-ttu-id="5f134-143">Para obtener una lista completa de los comandos de migración, consulte [Cmdlets de movimiento y migración](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="5f134-143">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
    
- <span data-ttu-id="5f134-p113">**Compruebe que puede conectarse a su servidor IMAP**. Ejecute el siguiente comando en Exchange Online PowerShell para probar la configuración de conexión al servidor IMAP.</span><span class="sxs-lookup"><span data-stu-id="5f134-p113">**Verify that you can connect to your IMAP server**. Run the following command in Exchange Online PowerShell to test the connection settings to your IMAP server.</span></span>
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    <span data-ttu-id="5f134-146">Para el valor del parámetro **Puerto**, es normal usar 143 para las conexiones no cifradas o de Seguridad de la capa de transporte (TLS) y 993 para las conexiones SSL.</span><span class="sxs-lookup"><span data-stu-id="5f134-146">For the value of the **Port** parameter, it's typical to use 143 for unencrypted or Transport Layer Security (TLS) connections and to use 993 for SSL connections.</span></span>
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a><span data-ttu-id="5f134-147">Paso 2: Crear un archivo CSV para un lote de migración IMAP</span><span class="sxs-lookup"><span data-stu-id="5f134-147">Step 2: Create a CSV file for an IMAP migration batch</span></span>
<span data-ttu-id="5f134-148"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="5f134-148"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="5f134-p114">Identifique el grupo de usuarios cuyos buzones de correo quiere migrar en un lote de migración de IMAP. Cada fila del archivo CSV contiene la información necesaria para conectar a un buzón del sistema de mensajería de IMAP.</span><span class="sxs-lookup"><span data-stu-id="5f134-p114">Identify the group of users whose mailboxes you want to migrate in an IMAP migration batch. Each row in the CSV file contains information necessary to connect to a mailbox in the IMAP messaging system.</span></span>
  
<span data-ttu-id="5f134-151">Los siguientes son los atributos necesarios para cada usuario:</span><span class="sxs-lookup"><span data-stu-id="5f134-151">Here are the required attributes for each user:</span></span> 
  
- <span data-ttu-id="5f134-152">**EmailAddress** especifica el identificador de usuario del buzón de Microsoft 365 del usuario.</span><span class="sxs-lookup"><span data-stu-id="5f134-152">**EmailAddress** specifies the user ID for the user's Microsoft 365 mailbox.</span></span>
    
- <span data-ttu-id="5f134-153">**UserName** especifica el nombre de inicio de sesión que usará la cuenta para tener acceso al buzón en el servidor IMAP.</span><span class="sxs-lookup"><span data-stu-id="5f134-153">**UserName** specifies the logon name for the account to use to access the mailbox on the IMAP server.</span></span>
    
- <span data-ttu-id="5f134-154">**Password** especifica la contraseña de la cuenta en la columna **UserName**.</span><span class="sxs-lookup"><span data-stu-id="5f134-154">**Password** specifies the password for the account in the **UserName** column.</span></span>
    
<span data-ttu-id="5f134-p115">A continuación, se muestra un ejemplo del formato del archivo CSV. En este ejemplo, se migran tres buzones:</span><span class="sxs-lookup"><span data-stu-id="5f134-p115">Here's an example of the format for the CSV file. In this example, three mailboxes are migrated:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

<span data-ttu-id="5f134-157">Para el atributo **UserName**, además del nombre de usuario, puede usar las credenciales de una cuenta a la que se hayan asignado los permisos necesarios para tener acceso a los buzones en el servidor IMAP. A continuación, se enumeran algunos de los formatos específicos usados para algunos servidores IMAP:</span><span class="sxs-lookup"><span data-stu-id="5f134-157">For the **UserName** attribute, in addition to the user name, you can use the credentials of an account that has been assigned the necessary permissions to access mailboxes on the IMAP server, the following are some of the specific formats used for some of the IMAP servers:</span></span>
  
 <span data-ttu-id="5f134-158">**Microsoft Exchange:**</span><span class="sxs-lookup"><span data-stu-id="5f134-158">**Microsoft Exchange:**</span></span>
  
<span data-ttu-id="5f134-159">Si va a migrar correo electrónico desde la implementación IMAP de Microsoft Exchange, use el formato **Domain/Admin_UserName/User_UserName** para el atributo **UserName** del archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="5f134-159">If you're migrating email from the IMAP implementation for Microsoft Exchange, use the format **Domain/Admin_UserName/User_UserName** for the **UserName** attribute in the CSV file.</span></span> <span data-ttu-id="5f134-160">Supongamos que desea migrar el correo electrónico de Exchange de Terry Adams, Ann Beebe y Paul Cannon.</span><span class="sxs-lookup"><span data-stu-id="5f134-160">Let's say you're migrating email from Exchange for Terry Adams, Ann Beebe, and Paul Cannon.</span></span> <span data-ttu-id="5f134-161">Tiene una cuenta de administrador de correo, donde el nombre de usuario es **mailadmin** y la contraseña es **P \@ ssw0rd**.</span><span class="sxs-lookup"><span data-stu-id="5f134-161">You have a mail administrator account, where the user name is **mailadmin** and the password is **P\@ssw0rd**.</span></span> <span data-ttu-id="5f134-162">Este es el aspecto que tendría el archivo CSV:</span><span class="sxs-lookup"><span data-stu-id="5f134-162">Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 <span data-ttu-id="5f134-163">**Dovecot:**</span><span class="sxs-lookup"><span data-stu-id="5f134-163">**Dovecot:**</span></span>
  
<span data-ttu-id="5f134-164">For IMAP servers that support Simple Authentication and Security Layer (SASL), such as a Dovecot IMAP server, use the format **User_UserName\*Admin_UserName**, where the asterisk ( \* ) is a configurable separator character.</span><span class="sxs-lookup"><span data-stu-id="5f134-164">For IMAP servers that support Simple Authentication and Security Layer (SASL), such as a Dovecot IMAP server, use the format **User_UserName\*Admin_UserName**, where the asterisk ( \* ) is a configurable separator character.</span></span> <span data-ttu-id="5f134-165">Supongamos que está migrando el correo electrónico de esos mismos usuarios desde un servidor IMAP Dovecot con las credenciales de administrador **mailadmin** y **P \@ ssw0rd**.</span><span class="sxs-lookup"><span data-stu-id="5f134-165">Let's say you're migrating those same users' email from a Dovecot IMAP server using the administrator credentials **mailadmin** and **P\@ssw0rd**.</span></span> <span data-ttu-id="5f134-166">Here's what your CSV file would look like:</span><span class="sxs-lookup"><span data-stu-id="5f134-166">Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 <span data-ttu-id="5f134-167">**Mirapoint:**</span><span class="sxs-lookup"><span data-stu-id="5f134-167">**Mirapoint:**</span></span>
  
<span data-ttu-id="5f134-168">Si va a migrar el correo electrónico desde el servidor de mensajes de Mirapoint, use el formato **#user \@ domain#Admin_UserName#** para las credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="5f134-168">If you're migrating email from Mirapoint Message Server, use the format **#user\@domain#Admin_UserName#** for the administrator credentials.</span></span> <span data-ttu-id="5f134-169">Para migrar el correo electrónico desde Mirapoint con las credenciales de administrador **mailadmin** y **P \@ ssw0rd,** el archivo CSV tendría este aspecto:</span><span class="sxs-lookup"><span data-stu-id="5f134-169">To migrate email from Mirapoint using the administrator credentials **mailadmin** and **P\@ssw0rd**, your CSV file would look like this:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 <span data-ttu-id="5f134-170">**Courier IMAP:**</span><span class="sxs-lookup"><span data-stu-id="5f134-170">**Courier IMAP:**</span></span>
  
<span data-ttu-id="5f134-171">Algunos sistemas de correo electrónico de origen, como Courier IMAP, no admiten el uso de credenciales de administrador de buzones para migrar buzones a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f134-171">Some source email systems, such as Courier IMAP, don't support using mailbox admin credentials to migrate mailboxes to Microsoft 365.</span></span> <span data-ttu-id="5f134-172">En su lugar, puede configurar el sistema de correo electrónico de origen para usar carpetas compartidas virtuales.</span><span class="sxs-lookup"><span data-stu-id="5f134-172">Instead, you can set up your source email system to use virtual shared folders.</span></span> <span data-ttu-id="5f134-173">Si usa carpetas compartidas virtuales, puede usar las credenciales de administrador de buzón para tener acceso a los buzones de usuario en el sistema de correo electrónico de origen.</span><span class="sxs-lookup"><span data-stu-id="5f134-173">By using virtual shared folders, you can use the mailbox admin credentials to access user mailboxes on the source email system.</span></span> <span data-ttu-id="5f134-174">Para obtener más información acerca de cómo configurar las carpetas compartidas virtuales para Courier IMAP, consulte [Carpetas compartidas](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span><span class="sxs-lookup"><span data-stu-id="5f134-174">For more information about how to configure virtual shared folders for Courier IMAP, see [Shared Folders](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span></span>
  
<span data-ttu-id="5f134-p120">Para migrar buzones después de configurar las carpetas compartidas virtuales en el sistema de correo electrónico de origen, debe incluir el atributo opcional **UserRoot** en el archivo de migración. Este atributo especifica la ubicación del buzón de cada usuario en la estructura de carpetas compartidas virtuales del sistema de correo electrónico de origen. Por ejemplo, la ruta de acceso al buzón de Terry es /users/terry.adams.</span><span class="sxs-lookup"><span data-stu-id="5f134-p120">To migrate mailboxes after you set up virtual shared folders on your source email system, you have to include the optional attribute **UserRoot** in the migration file. This attribute specifies the location of each user's mailbox in the virtual shared folder structure on the source email system. For example, the path to Terry's mailbox is /users/terry.adams.</span></span>
  
<span data-ttu-id="5f134-178">Este es un ejemplo de un archivo CSV que contiene el atributo **UserRoot**:</span><span class="sxs-lookup"><span data-stu-id="5f134-178">Here's an example of a CSV file that contains the **UserRoot** attribute:</span></span>
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a><span data-ttu-id="5f134-179">Paso 3: Crear un extremo de migración IMAP</span><span class="sxs-lookup"><span data-stu-id="5f134-179">Step 3: Create an IMAP migration endpoint</span></span>
<span data-ttu-id="5f134-180"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="5f134-180"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="5f134-181">Para migrar el correo electrónico correctamente, Microsoft 365 debe conectarse al sistema de correo electrónico de origen y comunicarse con él.</span><span class="sxs-lookup"><span data-stu-id="5f134-181">To migrate email successfully, Microsoft 365 needs to connect to and communicate with the source email system.</span></span> <span data-ttu-id="5f134-182">Para ello, Microsoft 365 usa un extremo de migración.</span><span class="sxs-lookup"><span data-stu-id="5f134-182">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="5f134-183">El extremo de migración también define el número de buzones que se migrará simultáneamente y el número de buzones que se sincronizará simultáneamente durante la sincronización incremental, que se hace una vez cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="5f134-183">The migration endpoint also defines the number of mailboxes to migrate simultaneously and the number of mailboxes to synchronize simultaneously during incremental synchronization, which occurs once every 24 hours.</span></span> <span data-ttu-id="5f134-184">Para crear un extremo de migración para la migración IMAP, primero debe [Conectarse a Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span><span class="sxs-lookup"><span data-stu-id="5f134-184">To create a migration end point for IMAP migration, first [connect to Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span></span> 
  
<span data-ttu-id="5f134-185">Para obtener una lista completa de los comandos de migración, consulte [Cmdlets de movimiento y migración](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="5f134-185">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="5f134-186">Para crear el extremo de migración IMAP denominado "IMAPEndpoint" en Exchange Online PowerShell, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f134-186">To create the IMAP migration endpoint called "IMAPEndpoint" in Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

<span data-ttu-id="5f134-p122">También puede agregar parámetros para especificar las migraciones simultáneas, las migraciones incrementales simultáneas y el puerto que se va a usar. El siguiente comando de Exchange Online PowerShell crea un extremo de migración IMAP denominado "IMAPEndpoint" que admite 50 migraciones simultáneas y hasta 25 sincronizaciones incrementales simultáneas. También configura el extremo para que use el puerto 143 para el cifrado TLS.</span><span class="sxs-lookup"><span data-stu-id="5f134-p122">You can also add parameters to specify concurrent migrations, concurrent incremental migrations, and the port to use. The following Exchange Online PowerShell command creates an IMAP migration endpoint called "IMAPEndpoint" that supports 50 concurrent migrations and up to 25 concurrent incremental synchronizations. It also configures the endpoint to use port 143 for TLS encryption.</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

<span data-ttu-id="5f134-190">Para obtener más información acerca del cmdlet **New-MigrationEndpoint**, consulte [New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437)</span><span class="sxs-lookup"><span data-stu-id="5f134-190">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="5f134-191">Compruebe que ha funcionado</span><span class="sxs-lookup"><span data-stu-id="5f134-191">Verify it worked</span></span>

<span data-ttu-id="5f134-192">Ejecute el siguiente comando en Exchange Online PowerShell para visualizar la información acerca de "IMAPEndpoint":</span><span class="sxs-lookup"><span data-stu-id="5f134-192">Run the following command in Exchange Online PowerShell to display information about the "IMAPEndpoint":</span></span>
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a><span data-ttu-id="5f134-193">Paso 4: Crear e iniciar un lote de migración IMAP</span><span class="sxs-lookup"><span data-stu-id="5f134-193">Step 4: Create and start an IMAP migration batch</span></span>
<span data-ttu-id="5f134-194"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="5f134-194"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="5f134-p123">Puede usar el cmdlet [New-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536439) para crear un lote de migración para una migración IMAP. Puede crear un lote de migración e iniciarlo automáticamente mediante la inclusión del parámetro _AutoStart_. Como alternativa, puede crear el lote de migración y, luego, iniciarlo posteriormente con el cmdlet [Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440).</span><span class="sxs-lookup"><span data-stu-id="5f134-p123">You can use the [New-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536439) cmdlet to create a migration batch for an IMAP migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then start it afterwards by using the[Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440) cmdlet.</span></span>
  
<span data-ttu-id="5f134-198">El siguiente comando de Exchange Online PowerShell iniciará automáticamente el lote de migración denominado "IMAPBatch1" usando el extremo IMAP denominado"IMAPEndpoint":</span><span class="sxs-lookup"><span data-stu-id="5f134-198">The following Exchange Online PowerShell command will automatically start the migration batch called "IMAPBatch1" using the IMAP endpoint called "IMAPEndpoint":</span></span>
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a><span data-ttu-id="5f134-199">Compruebe que ha funcionado</span><span class="sxs-lookup"><span data-stu-id="5f134-199">Verify it worked</span></span>

<span data-ttu-id="5f134-200">Ejecute el [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441) para ver información acerca de la "IMAPBatch1":</span><span class="sxs-lookup"><span data-stu-id="5f134-200">Run the [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441) cmdlet to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

<span data-ttu-id="5f134-201">También puede comprobar que el lote se ha iniciado ejecutando el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f134-201">You can also verify that the batch has started by running the following command:</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="5f134-202">Paso 5: Enrutar el correo electrónico a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f134-202">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="5f134-203"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="5f134-203"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="5f134-204">Los sistemas de correo electrónico utilizan un registro DNS denominado registro MX para averiguar dónde entregar los correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="5f134-204">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="5f134-205">Durante el proceso de migración del correo electrónico, el registro MX apuntaba al sistema de correo electrónico de origen.</span><span class="sxs-lookup"><span data-stu-id="5f134-205">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="5f134-206">Ahora que la migración de correo electrónico a Microsoft 365 se ha completado, es el momento de apuntar el registro MX a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f134-206">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="5f134-207">Esto ayuda a asegurarse de que el correo electrónico se entrega a los buzones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f134-207">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="5f134-208">Al mover el registro MX, también puede desactivar el sistema de correo electrónico antiguo cuando esté listo.</span><span class="sxs-lookup"><span data-stu-id="5f134-208">By moving the MX record, you can also turn off your old email system when you're ready.</span></span> 
  
<span data-ttu-id="5f134-209">Para muchos proveedores de DNS, hay instrucciones específicas para Cambiar el registro MX.</span><span class="sxs-lookup"><span data-stu-id="5f134-209">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="5f134-210">Si su proveedor de DNS no está incluido, o si desea obtener una idea de las instrucciones generales, se proporcionan también [Instrucciones generales del registro MX ](https://go.microsoft.com/fwlink/?LinkId=397449).</span><span class="sxs-lookup"><span data-stu-id="5f134-210">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions ](https://go.microsoft.com/fwlink/?LinkId=397449) are provided as well.</span></span>
  
<span data-ttu-id="5f134-p126">Los sistemas de correo electrónico de sus clientes y socios pueden tardar hasta 72 horas en reconocer el registro MX cambiado. Espere al menos 72 horas antes de continuar con la tarea siguiente: Paso 6: Eliminar el lote de migración IMAP.</span><span class="sxs-lookup"><span data-stu-id="5f134-p126">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: Step 6: Delete IMAP migration batch.</span></span> 
  
### <a name="step-6-delete-imap-migration-batch"></a><span data-ttu-id="5f134-213">Paso 6: Eliminar el lote de migración IMAP</span><span class="sxs-lookup"><span data-stu-id="5f134-213">Step 6: Delete IMAP migration batch</span></span>
<span data-ttu-id="5f134-214"><a name="BK_Step6"> </a></span><span class="sxs-lookup"><span data-stu-id="5f134-214"><a name="BK_Step6"> </a></span></span>

<span data-ttu-id="5f134-215">Después de cambiar el registro MX y comprobar que todo el correo electrónico se enruta a los buzones de Microsoft 365, notifique a los usuarios que su correo va a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f134-215">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="5f134-216">Después, puede eliminar el lote de migración IMAP.</span><span class="sxs-lookup"><span data-stu-id="5f134-216">After this, you can delete the IMAP migration batch.</span></span> <span data-ttu-id="5f134-217">Compruebe lo siguiente antes de eliminar el lote de migración.</span><span class="sxs-lookup"><span data-stu-id="5f134-217">Verify the following before you delete the migration batch.</span></span>
  
- <span data-ttu-id="5f134-218">Todos los usuarios usan buzones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f134-218">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="5f134-219">Después de eliminar el lote, el correo enviado a los buzones de correo de la Exchange Server local no se copia en los buzones de Microsoft 365 correspondientes.</span><span class="sxs-lookup"><span data-stu-id="5f134-219">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>
    
- <span data-ttu-id="5f134-220">Los buzones de Microsoft 365 se sincronizaron al menos una vez después de que el correo se empezara a enviar directamente a ellos.</span><span class="sxs-lookup"><span data-stu-id="5f134-220">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="5f134-221">Para ello, asegúrese de que el valor del cuadro Hora de última sincronización del lote de migración es más reciente que cuando el correo se empezó a enrutar directamente a los buzones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f134-221">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>
    
<span data-ttu-id="5f134-222">Para eliminar el lote de migración "IMAPBatch1" de Exchange Online PowerShell, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f134-222">To delete the "IMAPBatch1" migration batch from Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

<span data-ttu-id="5f134-223">Para obtener más información sobre el cmdlet **Remove-MigrationBatch**, consulte [Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span><span class="sxs-lookup"><span data-stu-id="5f134-223">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="5f134-224">Compruebe que ha funcionado</span><span class="sxs-lookup"><span data-stu-id="5f134-224">Verify it worked</span></span>

<span data-ttu-id="5f134-225">Ejecute el comando siguiente en Exchange Online PowerShell para visualizar la información sobre "IMAPBatch1":</span><span class="sxs-lookup"><span data-stu-id="5f134-225">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

<span data-ttu-id="5f134-226">El comando devolverá el lote de migración con un estado **Quitando** o devolverá un error indicando que el lote de migración no se ha encontrado, lo que demuestra que el lote se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="5f134-226">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>
  
<span data-ttu-id="5f134-227">Para obtener más información sobre el cmdlet **Get-MigrationBatch**, consulte [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span><span class="sxs-lookup"><span data-stu-id="5f134-227">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5f134-228">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f134-228">See also</span></span>

[<span data-ttu-id="5f134-229">Solucionador de problemas de migración IMAP</span><span class="sxs-lookup"><span data-stu-id="5f134-229">IMAP Migration Troubleshooter</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536482)

