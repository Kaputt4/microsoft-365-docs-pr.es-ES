---
title: Ejecutar un informe de grupo de roles de administrador en EOP independiente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a ejecutar un informe de grupo de roles de administrador en Exchange Online Protection (EOP) independiente. Este informe registra Cuándo un administrador agrega o quita miembros de grupos de roles de administrador, EOP registra cada ocurrencia.
ms.openlocfilehash: 39022892075b295a26645157941195b97897c690
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350944"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="20676-104">Ejecutar un informe de grupo de roles de administrador en EOP independiente</span><span class="sxs-lookup"><span data-stu-id="20676-104">Run an administrator role group report in standalone EOP</span></span>

<span data-ttu-id="20676-105">En las organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, cuando un administrador agrega o quita miembros de grupos de roles administrativos, el servicio registra cada ocurrencia.</span><span class="sxs-lookup"><span data-stu-id="20676-105">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="20676-106">Para obtener más información acerca de los grupos de roles en EOP independiente, consulte [Permissions in Standalone EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="20676-106">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="20676-107">Al ejecutar un informe de grupo de roles de administrador en el centro de administración de Exchange (EAC), las entradas se muestran como resultados de búsqueda e incluyen los grupos de funciones afectados, quién cambió la pertenencia al grupo de roles y cuándo se realizaron las actualizaciones de pertenencia.</span><span class="sxs-lookup"><span data-stu-id="20676-107">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="20676-108">Use este informe para supervisar los cambios en los permisos administrativos asignados a los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="20676-108">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="20676-109">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="20676-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="20676-110">Para abrir el centro de administración de Exchange, vea [centro de administración de Exchange en EOP independiente](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="20676-110">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="20676-111">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="20676-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="20676-112">En concreto, necesita el rol registros de auditoría o registros de auditoría con permiso de vista, que se asignan a los grupos de roles ComplianceManagement, OrganizationManagement (administradores globales) y SecurityAdministrator de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="20676-112">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="20676-113">Para obtener más información, vea [permisos en EOP independiente](feature-permissions-in-eop.md) y [usar el EAC para modificar la lista de miembros de los grupos de roles](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="20676-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="20676-114">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="20676-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="20676-115">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="20676-115">Having problems?</span></span> <span data-ttu-id="20676-116">Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="20676-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="20676-117">Usar el EAC para ejecutar un informe de grupo de roles de administrador</span><span class="sxs-lookup"><span data-stu-id="20676-117">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="20676-118">Ejecute el informe de grupo de roles de administrador para buscar los cambios en los grupos de roles de administración de la organización dentro de un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="20676-118">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="20676-119">En el EAC, vaya a **Compliance management** \> **Auditoría**de administración de cumplimiento y, a continuación, elija **ejecutar un informe de grupo de roles de administrador**.</span><span class="sxs-lookup"><span data-stu-id="20676-119">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="20676-120">En la página **Buscar cambios en los grupos de roles de administrador** que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="20676-120">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="20676-121">Fecha de **Inicio** y **fecha de finalización**: Introduzca un intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="20676-121">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="20676-122">De manera predeterminada, el informe busca los cambios efectuados en los grupos de roles de administrador en las últimas dos semanas.</span><span class="sxs-lookup"><span data-stu-id="20676-122">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="20676-123">**Seleccionar grupos de roles**: de forma predeterminada, se busca en todos los grupos de roles.</span><span class="sxs-lookup"><span data-stu-id="20676-123">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="20676-124">Para filtrar los resultados por grupos de funciones específicos, haga clic en **seleccionar grupos de roles**.</span><span class="sxs-lookup"><span data-stu-id="20676-124">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="20676-125">En el cuadro de diálogo que aparece, seleccione un grupo de roles y haga clic en **agregar >**.</span><span class="sxs-lookup"><span data-stu-id="20676-125">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="20676-126">Repita este paso tantas veces como sea necesario y, a continuación, haga clic en **Aceptar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="20676-126">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="20676-127">Cuando haya terminado, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="20676-127">When you're finished, click **Search**.</span></span>

<span data-ttu-id="20676-p108">Si se encuentran cambios con los criterios especificados, aparecerán en el panel de resultados. Haga clic en un grupo de roles de los resultados de la búsqueda para ver los cambios en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="20676-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="20676-130">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="20676-130">How do you know this worked?</span></span>

<span data-ttu-id="20676-p109">Si se ejecutó correctamente un informe de grupo de roles de administrador, los grupos de roles que cambiaron dentro del intervalo de fechas se muestran en el panel de resultados de la búsqueda. Si no hay resultados, entonces no se hicieron cambios a los grupos de funciones dentro del intervalo de fechas especificado. Si cree que debería haber resultados, cambie el intervalo de fechas y vuelva a ejecutar el informe.</span><span class="sxs-lookup"><span data-stu-id="20676-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="20676-134">Supervisión de cambios en la pertenencia a grupos de funciones</span><span class="sxs-lookup"><span data-stu-id="20676-134">Monitor changes to role group membership</span></span>

<span data-ttu-id="20676-p110">Cuando se agregan miembros a un grupo de funciones, o se quitan de él, los resultados de la búsqueda mostrados en el panel de detalles indican que la pertenencia al grupo de funciones se ha actualizado y enumera los miembros actuales. En los resultados no se indica explícitamente el usuario que se agregó o quitó.</span><span class="sxs-lookup"><span data-stu-id="20676-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="20676-p111">Para determinar si un usuario se agregó o quitó, tiene que comparar dos entradas independientes en el informe. Por ejemplo, veamos las siguientes entradas de registro para el grupo de roles **Servicio de asistencia**:</span><span class="sxs-lookup"><span data-stu-id="20676-p111">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="20676-139">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="20676-139">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="20676-140">Administrador</span><span class="sxs-lookup"><span data-stu-id="20676-140">Administrator</span></span> <br> <span data-ttu-id="20676-141">Miembros actualizados: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="20676-141">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="20676-142">2/06/2018 10:09 A.M.</span><span class="sxs-lookup"><span data-stu-id="20676-142">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="20676-143">Administrador</span><span class="sxs-lookup"><span data-stu-id="20676-143">Administrator</span></span> <br> <span data-ttu-id="20676-144">Miembros actualizados: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="20676-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="20676-145">2/19/2018 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="20676-145">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="20676-146">Administrador</span><span class="sxs-lookup"><span data-stu-id="20676-146">Administrator</span></span> <br> <span data-ttu-id="20676-147">Miembros actualizados: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="20676-147">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="20676-148">En este ejemplo, la cuenta de usuario Administrador realizó los siguientes cambios:</span><span class="sxs-lookup"><span data-stu-id="20676-148">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="20676-149">El 2/06/2018 agrega el usuario tonip.</span><span class="sxs-lookup"><span data-stu-id="20676-149">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="20676-150">El 2/19/2018, eliminó el usuario pilarp.</span><span class="sxs-lookup"><span data-stu-id="20676-150">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="20676-151">Usar Exchange Online PowerShell independiente para buscar entradas de registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="20676-151">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="20676-152">Puede usar Exchange Online PowerShell para buscar entradas de registro de auditoría que cumplan los criterios especificados.</span><span class="sxs-lookup"><span data-stu-id="20676-152">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="20676-153">Para obtener una lista de los criterios de búsqueda, consulte [Registro de auditoría de administrador](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx).</span><span class="sxs-lookup"><span data-stu-id="20676-153">For a list of search criteria, see [Administrator audit logging](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx).</span></span> <span data-ttu-id="20676-154">Este procedimiento usa el cmdlet **Search-AdminAuditLog** y muestra los resultados de la búsqueda en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20676-154">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="20676-155">Utilice este cmdlet cuando tenga que devolver un conjunto de resultados que supera los límites definidos en el cmdlet **New-AdminAuditLogSearch** o en los Informes de auditoría de la EAC.</span><span class="sxs-lookup"><span data-stu-id="20676-155">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="20676-156">Para buscar en el registro de auditoría los criterios que especifique, utilice la siguiente sintaxis.</span><span class="sxs-lookup"><span data-stu-id="20676-156">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="20676-157">De manera predeterminada, el cmdlet **Search-AdminAuditLog** devuelve un máximo de 1.000 entradas de registro.</span><span class="sxs-lookup"><span data-stu-id="20676-157">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="20676-158">Use el parámetro _resultsize_ para especificar hasta 250.000 entradas de registro.</span><span class="sxs-lookup"><span data-stu-id="20676-158">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="20676-159">O bien, use el valor `Unlimited` para devolver todas las entradas.</span><span class="sxs-lookup"><span data-stu-id="20676-159">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="20676-160">En este ejemplo se buscan todas las entradas del registro de auditoría con los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="20676-160">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="20676-161">**Fecha de inicio**: 08/04/2018</span><span class="sxs-lookup"><span data-stu-id="20676-161">**Start date**: 08/04/2018</span></span>

- <span data-ttu-id="20676-162">**Fecha de finalización**: 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="20676-162">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="20676-163">**Identificadores de usuario**: Davids, chrisd, Kima</span><span class="sxs-lookup"><span data-stu-id="20676-163">**User IDs**: davids, chrisd, kima</span></span>

- <span data-ttu-id="20676-164">**Cmdlets**: **set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="20676-164">**Cmdlets**: **Set-Mailbox**</span></span>

- <span data-ttu-id="20676-165">**Parámetros**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="20676-165">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="20676-p114">En este ejemplo se buscan los cambios realizados en un buzón específico. Esto resulta útil si está resolviendo problemas o necesita proporcionar información para una investigación. Se utilizan los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="20676-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="20676-169">**Fecha de inicio**: 05/01/2018</span><span class="sxs-lookup"><span data-stu-id="20676-169">**Start date**: 05/01/2018</span></span>

- <span data-ttu-id="20676-170">**Fecha de finalización**: 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="20676-170">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="20676-171">**Identificador de objeto**: contoso.com/users/DavidS</span><span class="sxs-lookup"><span data-stu-id="20676-171">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="20676-172">Si las búsquedas devuelven muchas entradas de registro, le recomendamos que use el procedimiento proporcionado en **use Exchange Online PowerShell para buscar entradas de registro de auditoría y enviar los resultados a un destinatario** más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="20676-172">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic.</span></span> <span data-ttu-id="20676-173">El procedimiento de esta sección envía un archivo XML como dato adjunto de correo electrónico a los destinatarios que especifique, de modo que será más fácil extraer los datos que interesan.</span><span class="sxs-lookup"><span data-stu-id="20676-173">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="20676-174">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="20676-174">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="20676-175">Ver los detalles de las entradas del registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="20676-175">View details of audit log entries</span></span>

<span data-ttu-id="20676-p116">El cmdlet **Search-AdminAuditLog** devuelve los campos descritos en la sección "Contenido del registro de auditoría" de [Registro de auditoría de administrador](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx). Entre los campos que devuelve el cmdlet, **CmdletParameters** y **ModifiedProperties** contienen información adicional que no se puede ver de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="20676-p116">The **Search-AdminAuditLog** cmdlet returns the fields described in the "Audit log contents section of [Administrator audit logging](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx). Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="20676-178">Para ver el contenido de los campos **CmdletParameters** y **ModifiedProperties** siga los pasos que se describen a continuación.</span><span class="sxs-lookup"><span data-stu-id="20676-178">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="20676-179">O bien, puede usar el procedimiento que se indica en **usar Exchange Online PowerShell para buscar entradas de registro de auditoría y enviar los resultados a un destinatario** más adelante en este tema para crear un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="20676-179">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic to create an XML file.</span></span>

<span data-ttu-id="20676-180">En este procedimiento se aplican los siguientes conceptos:</span><span class="sxs-lookup"><span data-stu-id="20676-180">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="20676-181">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="20676-181">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="20676-182">about_Variables</span><span class="sxs-lookup"><span data-stu-id="20676-182">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="20676-183">Decida los criterios que desea buscar, ejecute el cmdlet **Search-AdminAuditLog** y guarde los resultados en una variable utilizando el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="20676-183">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="20676-184">Cada entrada de registro de auditoría se almacena como un elemento de matriz en la variable `$Results` .</span><span class="sxs-lookup"><span data-stu-id="20676-184">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="20676-185">Puede seleccionar un elemento de matriz especificando su índice de elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="20676-185">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="20676-186">Los índices de elemento de matriz comienzan en cero (0) para el primer elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="20676-186">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="20676-187">Por ejemplo, para recuperar el quinto elemento de matriz, que tiene un índice de 4, utilice el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="20676-187">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="20676-p119">El comando anterior devuelve la entrada de registro almacenada en el elemento de matriz 4. Para ver el contenido de los campos **CmdletParameters** y **ModifiedProperties** para esta entrada de registro, utilice los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="20676-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="20676-190">Para ver el contenido de los campos **CmdletParameters** o **ModifiedParameters** en otra entrada de registro, cambie el índice del elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="20676-190">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>