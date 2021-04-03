---
title: Usar PowerShell para realizar una migración total a Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: Obtenga información sobre cómo usar PowerShell para mover el contenido de un sistema de correo electrónico de origen a la vez realizando una migración total a Microsoft 365.
ms.openlocfilehash: 6e59ac4d590208e0faed22e94cabe05601b17f18
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581063"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a><span data-ttu-id="0c2ea-103">Usar PowerShell para realizar una migración total a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c2ea-103">Use PowerShell to perform a cutover migration to Microsoft 365</span></span>

<span data-ttu-id="0c2ea-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="0c2ea-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0c2ea-105">Puede migrar el contenido de los buzones de usuario desde un sistema de correo electrónico de origen a Microsoft 365 a la vez mediante una migración total.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 all at once by using a cutover migration.</span></span> <span data-ttu-id="0c2ea-106">Este artículo le guiará a través de las tareas para una migración total del correo electrónico con Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-106">This article walks you through the tasks for an email cutover migration by using Exchange Online PowerShell.</span></span>

<span data-ttu-id="0c2ea-107">Al revisar el tema Lo que necesita saber acerca de una migración de correo electrónico a [Microsoft 365,](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)puede obtener información general sobre el proceso de migración.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-107">By reviewing the topic, [What you need to know about a cutover email migration to Microsoft 365](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration), you can get an overview of the migration process.</span></span> <span data-ttu-id="0c2ea-108">Cuando se sienta cómodo con el contenido de ese artículo, úselo para empezar a migrar los buzones de un sistema de correo electrónico a otro.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>

> [!NOTE]
> <span data-ttu-id="0c2ea-109">También puede usar el centro de administración de Exchange para realizar una migración total.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-109">You can also use the Exchange admin center to perform a cutover migration.</span></span> <span data-ttu-id="0c2ea-110">Vea [Realizar una migración de correo electrónico a Microsoft 365](/Exchange/mailbox-migration/cutover-migration-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-110">See [Perform a cutover migration of email to Microsoft 365](/Exchange/mailbox-migration/cutover-migration-to-office-365).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0c2ea-111">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="0c2ea-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="0c2ea-112">Tiempo estimado para finalizar esta tarea: entre 2 y 5 minutos para crear un lote de migración.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="0c2ea-113">Después de que haya iniciado el lote de migración, la duración de la migración variará según la cantidad de buzones del lote, el tamaño de cada buzón y la capacidad de red disponible.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="0c2ea-114">Para obtener información sobre otros factores que afectan al tiempo que se tarda en migrar buzones a Microsoft 365, vea [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).</span></span>

<span data-ttu-id="0c2ea-p105">Deberá tener permisos asignados para poder llevar a cabo estos procedimientos. Para ver qué permisos necesita, consulte la entrada "Movimiento de buzón y permisos de migración" en una tabla del tema [Permisos de destinatarios](/exchange/recipients-permissions-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.</span></span>

<span data-ttu-id="0c2ea-p106">Para usar los cmdlets de Exchange Online PowerShell, deberá iniciar sesión e importar los cmdlets en la sesión local de Windows PowerShell. Consulte [Conectarse a Exchange Online mediante PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-p106">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>

<span data-ttu-id="0c2ea-119">Para obtener una lista completa de los comandos de migración, consulte [Cmdlets de movimiento y migración](/powershell/exchange/).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-119">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

## <a name="migration-steps"></a><span data-ttu-id="0c2ea-120">Pasos de la migración</span><span class="sxs-lookup"><span data-stu-id="0c2ea-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-cutover-migration"></a><span data-ttu-id="0c2ea-121">Paso 1: Prepararse para una migración total</span><span class="sxs-lookup"><span data-stu-id="0c2ea-121">Step 1: Prepare for a cutover migration</span></span>
<span data-ttu-id="0c2ea-122"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="0c2ea-122"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="0c2ea-123">**Agregue la organización de Exchange local como dominio aceptado de su organización de Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="0c2ea-123">**Add your on-premises Exchange organization as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="0c2ea-124">El servicio de migración usa la dirección SMTP de los buzones locales para crear el identificador de usuario y la dirección de correo electrónico de Microsoft Online Services para los nuevos buzones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-124">The migration service uses the SMTP address of your on-premises mailboxes to create the Microsoft Online Services user ID and email address for the new Microsoft 365 mailboxes.</span></span> <span data-ttu-id="0c2ea-125">La migración producirá un error si el dominio de Exchange no es un dominio aceptado o el dominio principal de su organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-125">Migration will fail if your Exchange domain isn't an accepted domain or the primary domain of your Microsoft 365 organization.</span></span> <span data-ttu-id="0c2ea-126">Para obtener más información, vea [Verify your domain](../admin/setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-126">For more information, see [Verify your domain](../admin/setup/add-domain.md).</span></span>

- <span data-ttu-id="0c2ea-p108">**Configure Outlook en cualquier lugar en el servidor Exchange local.** El servicio de migración de correo electrónico utiliza RPC sobre HTTP, u Outlook en cualquier lugar, para conectarse al servidor Exchange local. Para obtener más información acerca de cómo configurar Outlook en cualquier lugar para Exchange 2010, Exchange 2007 y Exchange 2003, consulte lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c2ea-p108">**Configure Outlook Anywhere on your on-premises Exchange server.** The email migration service uses RPC over HTTP, or Outlook Anywhere, to connect to your on-premises Exchange server. For information about how to set up Outlook Anywhere for Exchange 2010, Exchange 2007, and Exchange 2003, see the following:</span></span>

  - <span data-ttu-id="0c2ea-130">[Exchange 2010: Habilitar Outlook Anywhere](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="0c2ea-130">[Exchange 2010: Enable Outlook Anywhere](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))</span></span>

  - <span data-ttu-id="0c2ea-131">[Exchange 2007: Cómo habilitar Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="0c2ea-131">[Exchange 2007: How to Enable Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))</span></span>

  - <span data-ttu-id="0c2ea-132">[Exchange 2003: Situaciones de implementación para RPC a través de HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="0c2ea-132">[Exchange 2003: Deployment Scenarios for RPC over HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))</span></span>

  - <span data-ttu-id="0c2ea-133">[Cómo configurar Outlook Anywhere con Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="0c2ea-133">[How to Configure Outlook Anywhere with Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0c2ea-p109">La configuración de Outlook en cualquier lugar se debe realizar con un certificado emitido por una entidad de certificación (CA) de confianza. No se puede configurar con un certificado autofirmado. Para obtener más información, consulte [Cómo configurar SSL para Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-p109">Your Outlook Anywhere configuration must be configured with a certificate issued by a trusted certification authority (CA). It can't be configured with a self-signed certificate. For more information, see [How to Configure SSL for Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).</span></span>

- <span data-ttu-id="0c2ea-p110">**Compruebe que puede conectarse a la organización de Exchange mediante Outlook en cualquier lugar.** Intente uno de estos métodos para probar la configuración de conexión:</span><span class="sxs-lookup"><span data-stu-id="0c2ea-p110">**Verify that you can connect to your Exchange organization using Outlook Anywhere.** Try one of these methods to test your connection settings:</span></span>

  - <span data-ttu-id="0c2ea-139">Utilice Microsoft Outlook desde fuera de la red corporativa para conectarse a su buzón de Exchange local.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-139">Use Microsoft Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>

  - <span data-ttu-id="0c2ea-p111">Utilice el [Analizador de conectividad remota de Microsoft Exchange](https://www.testexchangeconnectivity.com/) para probar la configuración de la conexión. Utilice Outlook en cualquier lugar (RPC sobre HTTP) o las pruebas de Detección automática de Outlook.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-p111">Use the Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) to test your connection settings. Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>

  - <span data-ttu-id="0c2ea-142">Ejecute los comandos siguientes en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-142">Run the following commands in Exchange Online PowerShell.</span></span>

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- <span data-ttu-id="0c2ea-143">**Asigne a una cuenta de usuario local los permisos necesarios para obtener acceso a los buzones de la organización de Exchange.**</span><span class="sxs-lookup"><span data-stu-id="0c2ea-143">**Assign an on-premises user account the necessary permissions to access mailboxes in your Exchange organization.**</span></span> <span data-ttu-id="0c2ea-144">La cuenta de usuario local que use para conectarse a la organización local de Exchange (también denominada administrador de migración) debe tener los permisos necesarios para tener acceso a los buzones locales que desea migrar a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-144">The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="0c2ea-145">Esta cuenta de usuario se utiliza para crear un extremo de migración para la organización local.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-145">This user account is used to create a migration endpoint to your on-premises organization.</span></span>

    <span data-ttu-id="0c2ea-p113">En la lista siguiente, se muestran los privilegios administrativos necesarios para migrar buzones con una migración total. Hay tres opciones posibles.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-p113">The following list shows the administrative privileges required to migrate mailboxes using a cutover migration. There are three possible options.</span></span>

  - <span data-ttu-id="0c2ea-148">El administrador de la migración debe ser miembro del grupo **Administradores del dominio** en Active Directory en la organización local.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-148">The migration administrator must be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>

    <span data-ttu-id="0c2ea-149">O bien</span><span class="sxs-lookup"><span data-stu-id="0c2ea-149">Or</span></span>

  - <span data-ttu-id="0c2ea-150">El administrador de la migración debe contar con permiso de **acceso completo** para cada buzón local.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-150">The migration administrator must be assigned the **FullAccess** permission for each on-premises mailbox.</span></span>

    <span data-ttu-id="0c2ea-151">O bien</span><span class="sxs-lookup"><span data-stu-id="0c2ea-151">Or</span></span>

  - <span data-ttu-id="0c2ea-152">El administrador de la migración debe tener el permiso **Recibir como** en la base de datos del buzón local que almacena los buzones de usuario.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-152">The migration administrator must be assigned the **Receive As** permission on the on-premises mailbox database that stores the user mailboxes.</span></span>

- <span data-ttu-id="0c2ea-p114">**Deshabilite la mensajería unificada.** Si los buzones locales que va a migrar están habilitados para la mensajería unificada, debe deshabilitarla en los buzones antes de migrarlos. A continuación, puede habilitar la mensajería unificada en los buzones una vez completada la migración.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-p114">**Disable Unified Messaging.** If the on-premises mailboxes you're migrating are enabled for Unified Messaging (UM), you have to disable UM on the mailboxes before you migrate them. You can then enable UM on the mailboxes after the migration is complete.</span></span>

- <span data-ttu-id="0c2ea-156">**Grupos de seguridad y delegados** El servicio de migración de correo electrónico no puede detectar si los grupos de Active Directory locales son grupos de seguridad o no, por lo que no puede aprovisionar grupos migrados como grupos de seguridad en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-156">**Security Groups and Delegates** The email migration service cannot detect whether on-premises Active Directory groups are security groups or not, so it cannot provision any migrated groups as security groups in Microsoft 365.</span></span> <span data-ttu-id="0c2ea-157">Si desea tener grupos de seguridad en su inquilino de Microsoft 365, primero debe aprovisionar un grupo de seguridad habilitado para correo vacío en su inquilino de Microsoft 365 antes de iniciar la migración de recorte.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-157">If you want to have security groups in your Microsoft 365 tenant, you must first provision an empty mail-enabled security group in your Microsoft 365 tenant before starting the cutover migration.</span></span> <span data-ttu-id="0c2ea-158">Además, este método de migración solo mueve buzones, usuarios de correo, contactos de correo y grupos habilitados para correo.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-158">Additionally, this migration method only moves mailboxes, mail users, mail contacts, and mail-enabled groups.</span></span> <span data-ttu-id="0c2ea-159">Si cualquier otro objeto de Active Directory, como el usuario que no se migra a Microsoft 365, se asigna como administrador o delegado a un objeto que se va a migrar, debe quitarse del objeto antes de migrar.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-159">If any other Active Directory object, such as user that is not migrated to Microsoft 365, is assigned as a manager or delegate to an object being migrated, they must be removed from the object before you migrate.</span></span>

### <a name="step-2-create-a-migration-endpoint"></a><span data-ttu-id="0c2ea-160">Paso 2: Crear un extremo de migración</span><span class="sxs-lookup"><span data-stu-id="0c2ea-160">Step 2: Create a migration endpoint</span></span>
<span data-ttu-id="0c2ea-161"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="0c2ea-161"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="0c2ea-162">Para migrar correo electrónico correctamente, Microsoft 365 debe conectarse y comunicarse con el sistema de correo electrónico de origen.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-162">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="0c2ea-163">Para ello, Microsoft 365 usa un extremo de migración.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-163">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="0c2ea-164">Para crear un extremo de migración de Outlook en cualquier lugar para la migración total, primero debe [Conectarse a Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-164">To create an Outlook Anywhere migration endpoint for cutover migration, first [connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="0c2ea-165">Para obtener una lista completa de los comandos de migración, consulte [Cmdlets de movimiento y migración](/powershell/exchange/).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-165">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

<span data-ttu-id="0c2ea-166">Ejecute los comandos siguientes en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0c2ea-166">Run the following commands in Exchange Online PowerShell:</span></span>

```powershell
$Credentials = Get-Credential
```

<span data-ttu-id="0c2ea-167">El ejemplo usa el cmdlet [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) para obtener y probar la configuración de conexión al servidor de Exchange local y luego utiliza dicha configuración de conexión para crear el extremo de migración denominado "CutoverEndpoint".</span><span class="sxs-lookup"><span data-stu-id="0c2ea-167">The example uses the [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) cmdlet to obtain and test the connection settings to the on-premises Exchange server, and then uses those connection settings to create the migration endpoint called "CutoverEndpoint".</span></span>

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> <span data-ttu-id="0c2ea-p117">El cmdlet **New-MigrationEndpoint** puede usarse para especificar la base de datos que debe usar el servicio con la opción **-TargetDatabase**. Si no se hace, se asigna aleatoriamente una base de datos desde el sitio de Servicios de federación de Active Directory (AD FS) 2.0 donde se encuentra el buzón de administración.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-p117">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option. Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>

#### <a name="verify-it-worked"></a><span data-ttu-id="0c2ea-170">Compruebe que ha funcionado</span><span class="sxs-lookup"><span data-stu-id="0c2ea-170">Verify it worked</span></span>

<span data-ttu-id="0c2ea-171">En Exchange Online PowerShell, ejecute el siguiente comando para visualizar la información sobre el extremo de migración "CutoverEndpoint":</span><span class="sxs-lookup"><span data-stu-id="0c2ea-171">In Exchange Online PowerShell, run the following command to display information about the "CutoverEndpoint" migration endpoint:</span></span>

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a><span data-ttu-id="0c2ea-172">Paso 3: Crear el lote de migración total</span><span class="sxs-lookup"><span data-stu-id="0c2ea-172">Step 3: Create the cutover migration batch</span></span>
<span data-ttu-id="0c2ea-173"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="0c2ea-173"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="0c2ea-p118">Puede utilizar el cmdlet **New-MigrationBatch** en Exchange Online PowerShell para crear un lote de migración para una migración total. Puede crear un lote de migración e iniciarlo automáticamente mediante la inclusión del parámetro _AutoStart_. O bien puede crear el lote de migración y, luego, iniciarlo posteriormente de forma manual mediante el uso del cmdlet **Start-MigrationBatch**. En este ejemplo se crea un lote de migración denominado "CutoverBatch" y se utiliza el extremo de migración que se creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-p118">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet. This example creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

<span data-ttu-id="0c2ea-p119">En este ejemplo se crea también un lote de migración denominado "CutoverBatch" y se utiliza el extremo de migración que se creó en el paso anterior. Dado que no se incluye el parámetro  _AutoStart_, el lote de migración debe iniciarse manualmente en el panel Migración o con el cmdlet **Start-MigrationBatch**. Como se especificó anteriormente, solo puede existir un lote de migración total cada vez.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-p119">This example also creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step. Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet. As previously stated, only one cutover migration batch can exist at a time.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="0c2ea-181">Compruebe que ha funcionado</span><span class="sxs-lookup"><span data-stu-id="0c2ea-181">Verify it worked</span></span>

<span data-ttu-id="0c2ea-182">Para comprobar que se ha creado correctamente un lote de migración para una migración total, ejecute el siguiente comando en Exchange Online PowerShell para visualizar la información sobre el nuevo lote de migración:</span><span class="sxs-lookup"><span data-stu-id="0c2ea-182">To verify that you've successfully created a migration batch for a cutover migration, run the following command in Exchange Online PowerShell to display information about the new migration batch:</span></span>

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a><span data-ttu-id="0c2ea-183">Paso 4: Iniciar el lote de migración total</span><span class="sxs-lookup"><span data-stu-id="0c2ea-183">Step 4: Start the cutover migration batch</span></span>
<span data-ttu-id="0c2ea-184"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="0c2ea-184"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="0c2ea-p120">Para iniciar el lote de migración en Exchange Online PowerShell, ejecute el comando siguiente. Esto creará un lote de migración denominado "CutoverBatch".</span><span class="sxs-lookup"><span data-stu-id="0c2ea-p120">To start the migration batch in Exchange Online PowerShell, run the following command. This will create a migration batch called "CutoverBatch".</span></span>

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a><span data-ttu-id="0c2ea-187">Compruebe que ha funcionado</span><span class="sxs-lookup"><span data-stu-id="0c2ea-187">Verify it worked</span></span>

<span data-ttu-id="0c2ea-p121">Si un lote de migración se inicia correctamente, su estado en el panel Migración aparece como Sincronizando. Para comprobar que ha iniciado correctamente un lote de migración con Exchange Online PowerShell, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c2ea-p121">If a migration batch is successfully started, its status on the migration dashboard is specified as Syncing. To verify that you've successfully started a migration batch using Exchange Online PowerShell, run the following command:</span></span>

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="0c2ea-190">Paso 5: Enrutar el correo electrónico a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c2ea-190">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="0c2ea-191"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="0c2ea-191"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="0c2ea-192">Los sistemas de correo electrónico utilizan un registro DNS denominado registro MX para averiguar dónde entregar los correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-192">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="0c2ea-193">Durante el proceso de migración del correo electrónico, el registro MX apuntaba al sistema de correo electrónico de origen.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-193">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="0c2ea-194">Ahora que se ha completado la migración de correo electrónico a Microsoft 365, es el momento de apuntar el registro MX a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-194">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="0c2ea-195">Esto ayuda a asegurarse de que el correo electrónico se entrega a los buzones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-195">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="0c2ea-196">Al mover el registro MX, también puede desactivar el sistema de correo electrónico antiguo cuando esté listo.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-196">By moving the MX record, you can also you turn off your old email system when you're ready.</span></span>

<span data-ttu-id="0c2ea-197">Para muchos proveedores de DNS, hay instrucciones específicas para Cambiar el registro MX.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-197">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="0c2ea-198">Si su proveedor de DNS no está incluido o si desea hacerse una idea de las orientaciones generales, también ofrecemos las [instrucciones generales de registro MX](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-198">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx) are provided as well.</span></span>

<span data-ttu-id="0c2ea-p124">Los sistemas de correo electrónico de sus clientes y socios pueden tardar hasta 72 horas en reconocer el registro MX cambiado. Espere al menos 72 horas antes de continuar con la tarea siguiente: [Paso 6: Eliminar el lote de migración total](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-p124">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: [Step 6: Delete the cutover migration batch](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span></span>

### <a name="step-6-delete-the-cutover-migration-batch"></a><span data-ttu-id="0c2ea-201">Paso 6: Eliminar el lote de migración total</span><span class="sxs-lookup"><span data-stu-id="0c2ea-201">Step 6: Delete the cutover migration batch</span></span>
<span data-ttu-id="0c2ea-202"><a name="Bk_step6"> </a></span><span class="sxs-lookup"><span data-stu-id="0c2ea-202"><a name="Bk_step6"> </a></span></span>

<span data-ttu-id="0c2ea-203">Después de cambiar el registro MX y comprobar que todo el correo electrónico se enruta a buzones de Microsoft 365, notifique a los usuarios que su correo va a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-203">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="0c2ea-204">Después, puede eliminar el lote de migración total.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-204">After this, you can delete the cutover migration batch.</span></span> <span data-ttu-id="0c2ea-205">Compruebe lo siguiente antes de eliminar el lote de migración.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-205">Verify the following before you delete the migration batch.</span></span>

- <span data-ttu-id="0c2ea-206">Todos los usuarios usan buzones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-206">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="0c2ea-207">Después de eliminar el lote, el correo enviado a los buzones de correo en la Exchange Server local no se copia en los buzones de Microsoft 365 correspondientes.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-207">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>

- <span data-ttu-id="0c2ea-208">Los buzones de Microsoft 365 se sincronizaron al menos una vez después de que el correo empezara a enviarse directamente a ellos.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-208">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="0c2ea-209">Para ello, asegúrese de que el valor del cuadro Última hora sincronizada del lote de migración es más reciente que cuando el correo comenzó a enrutar directamente a buzones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-209">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="0c2ea-210">Para eliminar el lote de migración "CutoverBatch" en Exchange Online PowerShell, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-210">To delete the "CutoverBatch" migration batch in Exchange Online PowerShell, run the following command:</span></span>

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a><span data-ttu-id="0c2ea-211">Sección 7: Asignar licencias de usuario</span><span class="sxs-lookup"><span data-stu-id="0c2ea-211">Section 7: Assign user licenses</span></span>
<span data-ttu-id="0c2ea-212"><a name="BK_Step7"> </a></span><span class="sxs-lookup"><span data-stu-id="0c2ea-212"><a name="BK_Step7"> </a></span></span>

 <span data-ttu-id="0c2ea-213">**Active las cuentas de usuario de Microsoft 365 para las cuentas migradas mediante la asignación de licencias.**</span><span class="sxs-lookup"><span data-stu-id="0c2ea-213">**Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.**</span></span> <span data-ttu-id="0c2ea-214">Si no asigna una licencia, el buzón se deshabilitará cuando finalice el periodo de gracia (30 días).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-214">If you don't assign a license, the mailbox is disabled when the grace period ends (30 days).</span></span> <span data-ttu-id="0c2ea-215">Para asignar una licencia en el Centro de administración de Microsoft 365, vea Asignar o [desasignación de licencias.](../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="0c2ea-215">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](../admin/manage/assign-licenses-to-users.md).</span></span>

### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="0c2ea-216">Paso 8: Finalizar las tareas posteriores a la migración</span><span class="sxs-lookup"><span data-stu-id="0c2ea-216">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="0c2ea-217"><a name="BK_Step8"> </a></span><span class="sxs-lookup"><span data-stu-id="0c2ea-217"><a name="BK_Step8"> </a></span></span>

- <span data-ttu-id="0c2ea-218">**Cree un registro DNS de Detección automática para que los usuarios puedan acceder fácilmente a sus buzones.**</span><span class="sxs-lookup"><span data-stu-id="0c2ea-218">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="0c2ea-219">Después de migrar todos los buzones locales a Microsoft 365, puede configurar un registro DNS de detección automática para su organización de Microsoft 365 para permitir a los usuarios conectarse fácilmente a sus nuevos buzones de Microsoft 365 con Outlook y clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-219">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="0c2ea-220">Este nuevo registro DNS de detección automática debe usar el mismo espacio de nombres que está usando para su organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-220">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="0c2ea-221">Por ejemplo, si el espacio de nombres basado en la nube es cloud.contoso.com, el registro DNS de Detección automática que se debe crear es autodiscover.cloud.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-221">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>

    <span data-ttu-id="0c2ea-222">Si mantiene su Exchange Server, también debe asegurarse de que el registro CNAME dns de detección automática debe apuntar a Microsoft 365 en DNS interno y externo después de la migración para que el cliente de Outlook se conecte al buzón correcto.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-222">If you keep your Exchange Server, you should also make sure that Autodiscover DNS CNAME record has to point to Microsoft 365 in both internal and external DNS after the migration so that the Outlook client will to connect to the correct mailbox.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="0c2ea-223">En Exchange 2007, Exchange 2010 y Exchange 2013 también debe establecer  `Set-ClientAccessServer AutodiscoverInternalConnectionURI` como `Null`.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-223">In Exchange 2007, Exchange 2010, and Exchange 2013 you should also set `Set-ClientAccessServer AutodiscoverInternalConnectionURI` to `Null`.</span></span>

    <span data-ttu-id="0c2ea-224">Microsoft 365 usa un registro CNAME para implementar el servicio de detección automática para outlook y clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-224">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="0c2ea-225">El registro CNAME de Detección automática debe contener la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c2ea-225">The Autodiscover CNAME record must contain the following information:</span></span>

  - <span data-ttu-id="0c2ea-226">**Alias:** autodiscover</span><span class="sxs-lookup"><span data-stu-id="0c2ea-226">**Alias:** autodiscover</span></span>

  - <span data-ttu-id="0c2ea-227">**Destino:** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0c2ea-227">**Target:** autodiscover.outlook.com</span></span>

    <span data-ttu-id="0c2ea-228">Para obtener más información, vea [Agregar registros DNS para conectar el dominio.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="0c2ea-228">For more information, see [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

- <span data-ttu-id="0c2ea-229">**Retire los servidores de Exchange locales.**</span><span class="sxs-lookup"><span data-stu-id="0c2ea-229">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="0c2ea-230">Después de comprobar que todo el correo electrónico se enruta directamente a los buzones de Microsoft 365 y ya no necesita mantener la organización de correo electrónico local o no tiene previsto implementar una solución de inicio de sesión único (SSO), puede desinstalar Exchange de los servidores y quitar la organización de Exchange local.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-230">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing a single sign-on (SSO) solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>

    <span data-ttu-id="0c2ea-231">Para obtener más información, vea los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0c2ea-231">For more information, see the following:</span></span>

  - <span data-ttu-id="0c2ea-232">[Modificar o quitar Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="0c2ea-232">[Modify or Remove Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))</span></span>

  - <span data-ttu-id="0c2ea-233">[Cómo quitar una organización de Exchange 2007](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="0c2ea-233">[How to Remove an Exchange 2007 Organization](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))</span></span>

  - <span data-ttu-id="0c2ea-234">[Cómo desinstalar Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="0c2ea-234">[How to Uninstall Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))</span></span>