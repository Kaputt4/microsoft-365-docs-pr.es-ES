---
title: Ejecutar un informe de grupo de roles de administrador en EOP independiente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a ejecutar un informe de grupo de roles de administrador en Exchange Online Protection (EOP) independiente. Este informe registra cuando un administrador agrega miembros a o quita miembros de grupos de roles de administrador.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0281dcb13f5cee0ba8db8c4faed5054f481337cf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908799"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="213c9-104">Ejecutar un informe de grupo de roles de administrador en EOP independiente</span><span class="sxs-lookup"><span data-stu-id="213c9-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="213c9-105">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="213c9-105">**Applies to**</span></span>
-  [<span data-ttu-id="213c9-106">Exchange Online Protection independiente</span><span class="sxs-lookup"><span data-stu-id="213c9-106">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="213c9-107">En organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, cuando un administrador agrega miembros o quita miembros de grupos de roles administrativos, el servicio registra cada aparición.</span><span class="sxs-lookup"><span data-stu-id="213c9-107">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="213c9-108">Para obtener más información acerca de los grupos de roles en EOP independiente, vea [Permissions in standalone EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="213c9-108">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="213c9-109">Al ejecutar un informe de grupo de roles de administrador en el Centro de administración de Exchange (EAC), las entradas se muestran como resultados de búsqueda e incluyen los grupos de roles afectados, quién cambió la pertenencia al grupo de roles y cuándo y qué actualizaciones de pertenencia se realizaron.</span><span class="sxs-lookup"><span data-stu-id="213c9-109">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="213c9-110">Use este informe para supervisar los cambios en los permisos administrativos asignados a los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="213c9-110">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="213c9-111">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="213c9-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="213c9-112">Para abrir el Centro de administración de Exchange, vea [Centro de administración de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="213c9-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="213c9-113">Debe tener asignados permisos en Exchange Online Protection antes de poder realizar los procedimientos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="213c9-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="213c9-114">En concreto, necesita el  rol **Registros** de auditoría o Registros de auditoría de solo vista, que están asignados a los grupos de roles Administración de la **organización,** Administración de cumplimiento y Administrador **de** seguridad de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="213c9-114">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="213c9-115">Para obtener más información, vea [Permissions in standalone EOP](feature-permissions-in-eop.md) y [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="213c9-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="213c9-116">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este artículo, vea [Métodos abreviados](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para el Centro de administración de Exchange en Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="213c9-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="213c9-117">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="213c9-117">Having problems?</span></span> <span data-ttu-id="213c9-118">Pida ayuda en el foro de [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) .</span><span class="sxs-lookup"><span data-stu-id="213c9-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="213c9-119">Usar el EAC para ejecutar un informe de grupo de roles de administrador</span><span class="sxs-lookup"><span data-stu-id="213c9-119">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="213c9-120">Ejecute el informe de grupo de roles de administrador para buscar los cambios en los grupos de roles de administración en un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="213c9-120">Run the administrator role group report to find the changes to management role groups within a particular time frame.</span></span>

1. <span data-ttu-id="213c9-121">En el EAC, vaya a **Administración de** cumplimiento \> **Auditoría** y, a continuación, elija **Ejecutar un informe de grupo de roles de administrador.**</span><span class="sxs-lookup"><span data-stu-id="213c9-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="213c9-122">En la **página Buscar cambios en grupos** de roles de administrador que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="213c9-122">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="213c9-123">**Fecha de inicio** y **fecha de finalización:** escriba un intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="213c9-123">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="213c9-124">De manera predeterminada, el informe busca los cambios efectuados en los grupos de roles de administrador en las últimas dos semanas.</span><span class="sxs-lookup"><span data-stu-id="213c9-124">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="213c9-125">**Seleccionar grupos de roles:** de forma predeterminada, se buscan todos los grupos de roles.</span><span class="sxs-lookup"><span data-stu-id="213c9-125">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="213c9-126">Para filtrar los resultados por grupos de roles específicos, haga clic **en Seleccionar grupos de roles**.</span><span class="sxs-lookup"><span data-stu-id="213c9-126">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="213c9-127">En el cuadro de diálogo que aparece, seleccione un grupo de roles y haga clic **en Agregar ->**.</span><span class="sxs-lookup"><span data-stu-id="213c9-127">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="213c9-128">Repita este paso tantas veces como sea necesario y, a continuación, haga clic en **Aceptar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="213c9-128">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="213c9-129">Cuando haya terminado, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="213c9-129">When you're finished, click **Search**.</span></span>

<span data-ttu-id="213c9-p108">Si se encuentran cambios con los criterios especificados, aparecerán en el panel de resultados. Haga clic en un grupo de roles de los resultados de la búsqueda para ver los cambios en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="213c9-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="213c9-132">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="213c9-132">How do you know this worked?</span></span>

<span data-ttu-id="213c9-p109">Si se ejecutó correctamente un informe de grupo de roles de administrador, los grupos de roles que cambiaron dentro del intervalo de fechas se muestran en el panel de resultados de la búsqueda. Si no hay resultados, entonces no se hicieron cambios a los grupos de funciones dentro del intervalo de fechas especificado. Si cree que debería haber resultados, cambie el intervalo de fechas y vuelva a ejecutar el informe.</span><span class="sxs-lookup"><span data-stu-id="213c9-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="213c9-136">Supervisión de cambios en la pertenencia a grupos de funciones</span><span class="sxs-lookup"><span data-stu-id="213c9-136">Monitor changes to role group membership</span></span>

<span data-ttu-id="213c9-p110">Cuando se agregan miembros a un grupo de funciones, o se quitan de él, los resultados de la búsqueda mostrados en el panel de detalles indican que la pertenencia al grupo de funciones se ha actualizado y enumera los miembros actuales. En los resultados no se indica explícitamente el usuario que se agregó o quitó.</span><span class="sxs-lookup"><span data-stu-id="213c9-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="213c9-p111">Para determinar si un usuario se agregó o quitó, tiene que comparar dos entradas independientes en el informe. Por ejemplo, veamos las siguientes entradas de registro para el grupo de roles **Servicio de asistencia**:</span><span class="sxs-lookup"><span data-stu-id="213c9-p111">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="213c9-141">1/27/2018 4:43 p.m.</span><span class="sxs-lookup"><span data-stu-id="213c9-141">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="213c9-142">Administrador</span><span class="sxs-lookup"><span data-stu-id="213c9-142">Administrator</span></span> <br> <span data-ttu-id="213c9-143">Miembros actualizados: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="213c9-143">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="213c9-144">06/06/2018 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="213c9-144">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="213c9-145">Administrador</span><span class="sxs-lookup"><span data-stu-id="213c9-145">Administrator</span></span> <br> <span data-ttu-id="213c9-146">Miembros actualizados: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="213c9-146">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="213c9-147">2/19/2018 2:12 p.m.</span><span class="sxs-lookup"><span data-stu-id="213c9-147">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="213c9-148">Administrador</span><span class="sxs-lookup"><span data-stu-id="213c9-148">Administrator</span></span> <br> <span data-ttu-id="213c9-149">Miembros actualizados: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="213c9-149">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="213c9-150">En este ejemplo, la cuenta de usuario Administrador realizó los siguientes cambios:</span><span class="sxs-lookup"><span data-stu-id="213c9-150">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="213c9-151">El 2/06/2018, agregaron el tonip de usuario.</span><span class="sxs-lookup"><span data-stu-id="213c9-151">On 2/06/2018, they added the user tonip.</span></span>
- <span data-ttu-id="213c9-152">El 19 de septiembre de 2018, quitaron el pilarp de usuario.</span><span class="sxs-lookup"><span data-stu-id="213c9-152">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="213c9-153">Usar PowerShell independiente de Exchange Online para buscar entradas de registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="213c9-153">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="213c9-154">Puede usar Exchange Online PowerShell para buscar entradas de registro de auditoría que cumplan los criterios que especifique.</span><span class="sxs-lookup"><span data-stu-id="213c9-154">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="213c9-155">Para obtener una lista de criterios de búsqueda, vea Criterios de búsqueda [Search-AdminAuditLog](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span><span class="sxs-lookup"><span data-stu-id="213c9-155">For a list of search criteria, see [Search-AdminAuditLog search criteria](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="213c9-156">Este procedimiento usa el cmdlet **Search-AdminAuditLog** y muestra los resultados de la búsqueda en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="213c9-156">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="213c9-157">Utilice este cmdlet cuando tenga que devolver un conjunto de resultados que supera los límites definidos en el cmdlet **New-AdminAuditLogSearch** o en los Informes de auditoría de la EAC.</span><span class="sxs-lookup"><span data-stu-id="213c9-157">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="213c9-158">Para buscar en el registro de auditoría los criterios que especifique, utilice la siguiente sintaxis.</span><span class="sxs-lookup"><span data-stu-id="213c9-158">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="213c9-159">De manera predeterminada, el cmdlet **Search-AdminAuditLog** devuelve un máximo de 1.000 entradas de registro.</span><span class="sxs-lookup"><span data-stu-id="213c9-159">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="213c9-160">Use el _parámetro ResultSize_ para especificar hasta 250 000 entradas de registro.</span><span class="sxs-lookup"><span data-stu-id="213c9-160">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="213c9-161">O bien, use el valor `Unlimited` para devolver todas las entradas.</span><span class="sxs-lookup"><span data-stu-id="213c9-161">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="213c9-162">En este ejemplo se buscan todas las entradas del registro de auditoría con los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="213c9-162">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="213c9-163">**Fecha de** inicio : 08/04/2018</span><span class="sxs-lookup"><span data-stu-id="213c9-163">**Start date**: 08/04/2018</span></span>
- <span data-ttu-id="213c9-164">**Fecha de** finalización : 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="213c9-164">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="213c9-165">**Id. de usuario**: `davids` , `chrisd` , `kima`</span><span class="sxs-lookup"><span data-stu-id="213c9-165">**User IDs**: `davids`, `chrisd`, `kima`</span></span>
- <span data-ttu-id="213c9-166">**Cmdlets**: **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="213c9-166">**Cmdlets**: **Set-Mailbox**</span></span>
- <span data-ttu-id="213c9-167">**Parámetros**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="213c9-167">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="213c9-p114">En este ejemplo se buscan los cambios realizados en un buzón específico. Esto resulta útil si está resolviendo problemas o necesita proporcionar información para una investigación. Se utilizan los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="213c9-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="213c9-171">**Fecha de** inicio : 05/01/2018</span><span class="sxs-lookup"><span data-stu-id="213c9-171">**Start date**: 05/01/2018</span></span>
- <span data-ttu-id="213c9-172">**Fecha de** finalización : 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="213c9-172">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="213c9-173">**Identificador de** objeto : contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="213c9-173">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="213c9-174">Si las búsquedas devuelven muchas entradas de registro, se recomienda usar el procedimiento proporcionado en **Use Exchange Online PowerShell para** buscar entradas de registro de auditoría y enviar resultados a un destinatario más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="213c9-174">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article.</span></span> <span data-ttu-id="213c9-175">El procedimiento de esta sección envía un archivo XML como dato adjunto de correo electrónico a los destinatarios que especifique, de modo que será más fácil extraer los datos que interesan.</span><span class="sxs-lookup"><span data-stu-id="213c9-175">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="213c9-176">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="213c9-176">For detailed syntax and parameter information, see [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="213c9-177">Ver los detalles de las entradas del registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="213c9-177">View details of audit log entries</span></span>

<span data-ttu-id="213c9-178">El cmdlet **Search-AdminAuditLog** devuelve los campos descritos en [Contenido del registro de auditoría](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span><span class="sxs-lookup"><span data-stu-id="213c9-178">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="213c9-179">Entre los campos que devuelve el cmdlet, **CmdletParameters** y **ModifiedProperties** contienen información adicional que no se puede ver de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="213c9-179">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="213c9-180">Para ver el contenido de los campos **CmdletParameters** y **ModifiedProperties** siga los pasos que se describen a continuación.</span><span class="sxs-lookup"><span data-stu-id="213c9-180">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="213c9-181">O bien, puede usar el procedimiento de **Usar Exchange Online PowerShell** para buscar entradas de registro de auditoría y enviar resultados a un destinatario más adelante en este artículo para crear un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="213c9-181">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article to create an XML file.</span></span>

<span data-ttu-id="213c9-182">En este procedimiento se aplican los siguientes conceptos:</span><span class="sxs-lookup"><span data-stu-id="213c9-182">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="213c9-183">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="213c9-183">about_Arrays</span></span>](/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="213c9-184">about_Variables</span><span class="sxs-lookup"><span data-stu-id="213c9-184">about_Variables</span></span>](/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="213c9-185">Decida los criterios que desea buscar, ejecute el cmdlet **Search-AdminAuditLog** y guarde los resultados en una variable utilizando el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="213c9-185">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. <span data-ttu-id="213c9-186">Cada entrada de registro de auditoría se almacena como un elemento de matriz en la variable `$Results` .</span><span class="sxs-lookup"><span data-stu-id="213c9-186">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="213c9-187">Puede seleccionar un elemento de matriz especificando su índice de elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="213c9-187">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="213c9-188">Los índices de elemento de matriz comienzan en cero (0) para el primer elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="213c9-188">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="213c9-189">Por ejemplo, para recuperar el quinto elemento de matriz, que tiene un índice de 4, utilice el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="213c9-189">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

   ```PowerShell
   $Results[4]
   ```

3. <span data-ttu-id="213c9-p119">El comando anterior devuelve la entrada de registro almacenada en el elemento de matriz 4. Para ver el contenido de los campos **CmdletParameters** y **ModifiedProperties** para esta entrada de registro, utilice los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="213c9-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. <span data-ttu-id="213c9-192">Para ver el contenido de los campos **CmdletParameters** o **ModifiedParameters** en otra entrada de registro, cambie el índice del elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="213c9-192">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>