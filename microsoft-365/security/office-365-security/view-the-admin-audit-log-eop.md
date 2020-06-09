---
title: Ver el registro de auditoría de administrador en EOP independiente
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
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Los administradores pueden obtener información sobre cómo ver y buscar el registro de auditoría de administración en Exchange Online Protection (EOP) independiente.
ms.openlocfilehash: e8c12f622c4dc382b11d03424e45c33e3afe3cbf
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613329"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="ffc63-103">Ver el registro de auditoría de administrador en EOP independiente</span><span class="sxs-lookup"><span data-stu-id="ffc63-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="ffc63-104">En las organizaciones independientes de Exchange Online Protection (EOP) que no tienen buzones de Exchange Online, puede usar el centro de administración de Exchange (EAC) o PowerShell independiente de EOP para buscar y ver las entradas en el registro de auditoría de administrador.</span><span class="sxs-lookup"><span data-stu-id="ffc63-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="ffc63-105">El registro de auditoría de administrador registra acciones específicas, basadas en los cmdlets de PowerShell independientes de EOP, realizadas por administradores y usuarios a los que se les han asignado privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="ffc63-105">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="ffc63-106">Las entradas del registro de auditoría de administración proporcionan información sobre el cmdlet que se ejecutó, los parámetros que se usaron, quién ejecutó el cmdlet y qué objetos se vieron afectados.</span><span class="sxs-lookup"><span data-stu-id="ffc63-106">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
> <ul><li><span data-ttu-id="ffc63-107">El registro de auditoría de administración está habilitado de forma predeterminada y no se puede deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="ffc63-107">Admin auditing logging is enabled by default, and you can't disable it.</span></span></li><li><span data-ttu-id="ffc63-108">El registro de auditoría de administrador no registra las acciones basadas en los cmdlets que comienzan con los verbos **Get**, **Search**o **Test**.</span><span class="sxs-lookup"><span data-stu-id="ffc63-108">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span></li><li><span data-ttu-id="ffc63-109">Las entradas de los registros de auditoría se conservan durante 90 días.</span><span class="sxs-lookup"><span data-stu-id="ffc63-109">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="ffc63-110">Cuando una entrada tiene más de 90 días, se elimina</span><span class="sxs-lookup"><span data-stu-id="ffc63-110">When an entry is older than 90 days, it's deleted</span></span></li></ul>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ffc63-111">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="ffc63-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ffc63-112">Para abrir el centro de administración de Exchange, vea [centro de administración de Exchange en EOP independiente](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="ffc63-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="ffc63-113">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="ffc63-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ffc63-114">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="ffc63-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="ffc63-115">En concreto, necesita el rol registros de auditoría o registros de auditoría con permiso de vista, que se asignan a los grupos de roles ComplianceManagement, OrganizationManagement (administradores globales) y SecurityAdministrator de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ffc63-115">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="ffc63-116">Para obtener más información, vea [permisos en EOP independiente](feature-permissions-in-eop.md) y [usar el EAC para modificar la lista de miembros de los grupos de roles](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="ffc63-116">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="ffc63-117">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="ffc63-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="ffc63-118">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="ffc63-118">Having problems?</span></span> <span data-ttu-id="ffc63-119">Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="ffc63-119">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="ffc63-120">Usar el EAC para ver el registro de auditoría de administración</span><span class="sxs-lookup"><span data-stu-id="ffc63-120">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="ffc63-121">En el EAC, vaya a auditoría de **Administración de cumplimiento** \> **Auditing**y, a continuación, elija **ejecutar el registro de auditoría de administrador**.</span><span class="sxs-lookup"><span data-stu-id="ffc63-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="ffc63-122">En la página **Buscar cambios en los grupos de roles de administrador** que se abre, elija una fecha de **Inicio** y una **fecha de finalización** (el intervalo predeterminado es las últimas dos semanas) y, a continuación, elija **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="ffc63-122">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="ffc63-123">Todos los cambios de configuración realizados durante el período de tiempo especificado se muestran y se pueden ordenar, mediante la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="ffc63-123">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="ffc63-124">**Fecha**: la fecha y la hora en que se realizó el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="ffc63-124">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="ffc63-125">La fecha y la hora se almacenan en formato de hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="ffc63-125">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="ffc63-126">**Cmdlet**: el nombre del cmdlet que se usó para realizar el cambio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="ffc63-126">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="ffc63-127">**User**: el nombre de la cuenta de usuario del usuario que realizó el cambio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="ffc63-127">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="ffc63-p107">Se mostrarán hasta 5000 entradas en varias páginas. Especifique un intervalo de fechas menor si necesita limitar los resultados. Si selecciona un resultado de la búsqueda individual, se mostrará la siguiente información adicional en el panel de detalles:</span><span class="sxs-lookup"><span data-stu-id="ffc63-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="ffc63-131">**Objeto modificado**: el objeto modificado por el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ffc63-131">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="ffc63-132">**Parameters (parámetro: valor)**: los parámetros del cmdlet que se usaron y cualquier valor especificado con el parámetro.</span><span class="sxs-lookup"><span data-stu-id="ffc63-132">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="ffc63-133">Si desea imprimir una entrada específica del registro de auditoría, elija el botón **Imprimir** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="ffc63-133">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="ffc63-134">Usar PowerShell independiente de EOP para ver el registro de auditoría de administrador</span><span class="sxs-lookup"><span data-stu-id="ffc63-134">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="ffc63-135">Puede usar la PowerShell independiente de EOP para buscar entradas de registro de auditoría que cumplan los criterios especificados.</span><span class="sxs-lookup"><span data-stu-id="ffc63-135">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="ffc63-136">Use la sintaxis que se muestre a continuación:</span><span class="sxs-lookup"><span data-stu-id="ffc63-136">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="ffc63-137">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="ffc63-137">**Notes**:</span></span>

- <span data-ttu-id="ffc63-138">Solo puede usar el parámetro _Parameters_ junto con el parámetro _cmdlets_ .</span><span class="sxs-lookup"><span data-stu-id="ffc63-138">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="ffc63-139">El parámetro _ObjectIds_ filtra los resultados por el objeto modificado por el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ffc63-139">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="ffc63-140">Un valor válido depende de cómo se representa el objeto en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="ffc63-140">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="ffc63-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ffc63-141">For example:</span></span>

  - <span data-ttu-id="ffc63-142">Nombre</span><span class="sxs-lookup"><span data-stu-id="ffc63-142">Name</span></span>
  - <span data-ttu-id="ffc63-143">Nombre distintivo canónico (por ejemplo, contoso.com/Users/Akia al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="ffc63-143">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="ffc63-144">Es probable que necesite usar otros parámetros de filtrado en este cmdlet para restringir los resultados e identificar los tipos de objetos que le interesan.</span><span class="sxs-lookup"><span data-stu-id="ffc63-144">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="ffc63-145">El parámetro _userid_ filtra los resultados por el usuario que realizó el cambio (que ejecutó el cmdlet).</span><span class="sxs-lookup"><span data-stu-id="ffc63-145">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="ffc63-146">Para los parámetros _startDate_ y _EndDate_ , si especifica un valor de fecha y hora sin una zona horaria, el valor es la hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="ffc63-146">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="ffc63-147">Para especificar un valor de fecha y hora para este parámetro, use una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="ffc63-147">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="ffc63-148">Especifique el valor de fecha y hora en UTC; por ejemplo, "2016-05-06 14:30:00z".</span><span class="sxs-lookup"><span data-stu-id="ffc63-148">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="ffc63-149">Especifique el valor de fecha y hora como una fórmula que convierte la fecha y hora de la zona horaria local en UTC: por ejemplo, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` .</span><span class="sxs-lookup"><span data-stu-id="ffc63-149">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="ffc63-150">Para obtener más información, vea [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span><span class="sxs-lookup"><span data-stu-id="ffc63-150">For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="ffc63-151">De forma predeterminada, el cmdlet devuelve un máximo de 1.000 entradas de registro.</span><span class="sxs-lookup"><span data-stu-id="ffc63-151">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="ffc63-152">Use el parámetro _resultsize_ para especificar hasta 250.000 entradas de registro.</span><span class="sxs-lookup"><span data-stu-id="ffc63-152">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="ffc63-153">O bien, use el valor `Unlimited` para devolver todas las entradas.</span><span class="sxs-lookup"><span data-stu-id="ffc63-153">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="ffc63-154">En este ejemplo se buscan todas las entradas del registro de auditoría con los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="ffc63-154">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="ffc63-155">**Fecha de inicio**: 4 de agosto de 2019</span><span class="sxs-lookup"><span data-stu-id="ffc63-155">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="ffc63-156">**Fecha de finalización**: 3 de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="ffc63-156">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="ffc63-157">**Cmdlets**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="ffc63-157">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="ffc63-158">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="ffc63-158">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="ffc63-159">Ver los detalles de las entradas del registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="ffc63-159">View details of audit log entries</span></span>

<span data-ttu-id="ffc63-160">El cmdlet **Search-AdminAuditLog** devuelve los campos descritos en la sección [contenido del registro de auditoría](#audit-log-contents) , más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="ffc63-160">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this topic.</span></span> <span data-ttu-id="ffc63-161">De los campos devueltos por el cmdlet, dos campos, **CmdletParameters** y **ModifiedProperties**, contienen información adicional que no se devuelve de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ffc63-161">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="ffc63-162">Para ver el contenido de los campos **CmdletParameters** y **ModifiedProperties** siga los pasos que se describen a continuación.</span><span class="sxs-lookup"><span data-stu-id="ffc63-162">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="ffc63-163">Decida los criterios que desea buscar, ejecute el cmdlet **Search-AdminAuditLog** y guarde los resultados en una variable utilizando el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="ffc63-163">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="ffc63-164">Cada entrada de registro de auditoría se almacena como un elemento de matriz en la variable `$Results` .</span><span class="sxs-lookup"><span data-stu-id="ffc63-164">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="ffc63-165">Puede seleccionar un elemento de matriz especificando su índice de elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="ffc63-165">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="ffc63-166">Los índices de elemento de matriz comienzan en cero (0) para el primer elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="ffc63-166">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="ffc63-167">Por ejemplo, para recuperar el quinto elemento de matriz, que tiene un índice de 4, utilice el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="ffc63-167">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="ffc63-p115">El comando anterior devuelve la entrada de registro almacenada en el elemento de matriz 4. Para ver el contenido de los campos **CmdletParameters** y **ModifiedProperties** para esta entrada de registro, utilice los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="ffc63-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="ffc63-170">Para ver el contenido de los campos **CmdletParameters** o **ModifiedParameters** en otra entrada de registro, cambie el índice del elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="ffc63-170">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="ffc63-171">Contenido del registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="ffc63-171">Audit log contents</span></span>

<span data-ttu-id="ffc63-172">Todas las entradas del registro de auditoría contienen la información que se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ffc63-172">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="ffc63-173">El registro de auditoría contiene una o varias entradas de registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="ffc63-173">The audit log contains one or more audit log entries.</span></span>

|||
|---|---|
|<span data-ttu-id="ffc63-174">**Field**</span><span class="sxs-lookup"><span data-stu-id="ffc63-174">**Field**</span></span>|<span data-ttu-id="ffc63-175">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ffc63-175">**Description**</span></span>|
|`RunspaceId`|<span data-ttu-id="ffc63-176">Este campo se usa de forma interna en EOP.</span><span class="sxs-lookup"><span data-stu-id="ffc63-176">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="ffc63-177">Este campo contiene el objeto modificado por el cmdlet especificado en el `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="ffc63-177">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="ffc63-178">Este campo contiene el nombre del cmdlet ejecutado por el usuario en el `Caller` campo.</span><span class="sxs-lookup"><span data-stu-id="ffc63-178">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="ffc63-179">Este campo contiene los parámetros que se especificaron cuando se ejecutó el cmdlet en el `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="ffc63-179">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="ffc63-180">En este campo también se almacena (aunque no es visible en la salida predeterminada) el valor especificado con el parámetro (si existe).</span><span class="sxs-lookup"><span data-stu-id="ffc63-180">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="ffc63-181">Este campo contiene las propiedades que se modificaron en el objeto en el `ObjectModified` campo.</span><span class="sxs-lookup"><span data-stu-id="ffc63-181">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="ffc63-182">Además, en este campo se almacenan el valor anterior de la propiedad y el nuevo valor almacenado, aunque no están visibles en los resultados predeterminados.</span><span class="sxs-lookup"><span data-stu-id="ffc63-182">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="ffc63-183">Este campo contiene la cuenta de usuario del usuario que ejecutó el cmdlet en el `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="ffc63-183">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="ffc63-184">Este campo se usa de forma interna en EOP.</span><span class="sxs-lookup"><span data-stu-id="ffc63-184">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="ffc63-185">Este campo especifica si el cmdlet del `CmdletName` campo se ejecutó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ffc63-185">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="ffc63-186">El valor es `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="ffc63-186">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="ffc63-187">Este campo contiene el mensaje de error generado si el cmdlet del `CmdletName` campo no se pudo completar correctamente.</span><span class="sxs-lookup"><span data-stu-id="ffc63-187">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="ffc63-188">Este campo contiene la fecha y la hora en que se ejecutó el cmdlet en el `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="ffc63-188">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="ffc63-189">La fecha y la hora se almacenan en formato de hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="ffc63-189">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="ffc63-190">Este campo indica el servidor en el que se ejecutó el cmdlet especificado en el `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="ffc63-190">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="ffc63-191">Este campo se usa de forma interna en EOP.</span><span class="sxs-lookup"><span data-stu-id="ffc63-191">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="ffc63-192">Este campo se usa de forma interna en EOP.</span><span class="sxs-lookup"><span data-stu-id="ffc63-192">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="ffc63-193">Este campo se usa de forma interna en EOP.</span><span class="sxs-lookup"><span data-stu-id="ffc63-193">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="ffc63-194">Este campo se usa de forma interna en EOP.</span><span class="sxs-lookup"><span data-stu-id="ffc63-194">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="ffc63-195">Este campo se usa de forma interna en EOP.</span><span class="sxs-lookup"><span data-stu-id="ffc63-195">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="ffc63-196">Este campo se usa de forma interna en EOP.</span><span class="sxs-lookup"><span data-stu-id="ffc63-196">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="ffc63-197">Este campo se usa de forma interna en EOP.</span><span class="sxs-lookup"><span data-stu-id="ffc63-197">This field is used internally by EOP.</span></span>|
|
