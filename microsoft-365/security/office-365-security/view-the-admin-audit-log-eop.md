---
title: Ver el registro de auditoría de administrador en EOP independiente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Los administradores pueden aprender a ver y buscar en el registro de auditoría de administración en Exchange Online Protection (EOP) independiente.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ed1d1eb121c06e6f5727e8782ba1d8bc8d23a99
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205040"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="e8992-103">Ver el registro de auditoría de administrador en EOP independiente</span><span class="sxs-lookup"><span data-stu-id="e8992-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="e8992-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="e8992-104">**Applies to**</span></span>
- [<span data-ttu-id="e8992-105">Exchange Online Protection independiente</span><span class="sxs-lookup"><span data-stu-id="e8992-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e8992-106">En organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, puede usar el Centro de administración de Exchange (EAC) o PowerShell de EOP independiente para buscar y ver entradas en el registro de auditoría de administración.</span><span class="sxs-lookup"><span data-stu-id="e8992-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="e8992-107">El registro de auditoría de administración registra acciones específicas, basadas en cmdlets de PowerShell EOP independientes, realizadas por administradores y usuarios a los que se les han asignado privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="e8992-107">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="e8992-108">Las entradas del registro de auditoría de administración proporcionan información sobre qué cmdlet se ejecutó, qué parámetros se usaron, quién ejecutó el cmdlet y qué objetos se vieron afectados.</span><span class="sxs-lookup"><span data-stu-id="e8992-108">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="e8992-109">El registro de auditoría de administradores está habilitado de forma predeterminada y no se puede deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="e8992-109">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="e8992-110">El registro de auditoría de administración no registra acciones basadas en cmdlets que comienzan con los verbos **Get**, **Search** o **Test**.</span><span class="sxs-lookup"><span data-stu-id="e8992-110">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="e8992-111">Las entradas de los registros de auditoría se conservan durante 90 días.</span><span class="sxs-lookup"><span data-stu-id="e8992-111">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="e8992-112">Cuando una entrada tiene más de 90 días, se elimina</span><span class="sxs-lookup"><span data-stu-id="e8992-112">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e8992-113">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="e8992-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e8992-114">Para abrir el Centro de administración de Exchange, vea [Centro de administración de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="e8992-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="e8992-115">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="e8992-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e8992-116">Debe tener asignados permisos en Exchange Online Protection antes de poder realizar los procedimientos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="e8992-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="e8992-117">En concreto, necesita el  rol **Registros** de auditoría o Registros de auditoría de solo vista, que están asignados a los grupos de roles Administración de la **organización,** Administración de cumplimiento y Administrador **de** seguridad de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e8992-117">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="e8992-118">Para obtener más información, vea [Permissions in standalone EOP](feature-permissions-in-eop.md) y [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="e8992-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="e8992-119">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este artículo, vea [Métodos abreviados](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para el Centro de administración de Exchange en Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="e8992-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="e8992-120">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="e8992-120">Having problems?</span></span> <span data-ttu-id="e8992-121">Pida ayuda en el foro de [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) .</span><span class="sxs-lookup"><span data-stu-id="e8992-121">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="e8992-122">Usar el EAC para ver el registro de auditoría de administración</span><span class="sxs-lookup"><span data-stu-id="e8992-122">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="e8992-123">En el EAC, vaya a **Administración de** cumplimiento Auditoría \> **y,** a continuación, elija **Ejecutar el informe de registro de auditoría de administración**.</span><span class="sxs-lookup"><span data-stu-id="e8992-123">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="e8992-124">En la **página Buscar** cambios en grupos de roles de administrador que se abre, elija una fecha de inicio y una fecha de finalización **(el** intervalo predeterminado es las dos últimas semanas) y, **a** continuación, **elija Buscar**.</span><span class="sxs-lookup"><span data-stu-id="e8992-124">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="e8992-125">Todos los cambios de configuración realizados durante el período de tiempo especificado se muestran y se pueden ordenar, mediante la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="e8992-125">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="e8992-126">**Fecha:** fecha y hora en que se realizó el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="e8992-126">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="e8992-127">La fecha y la hora se almacenan en formato de hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="e8992-127">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="e8992-128">**Cmdlet:** el nombre del cmdlet que se usó para realizar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="e8992-128">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="e8992-129">**Usuario:** nombre de la cuenta de usuario del usuario que realizó el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="e8992-129">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="e8992-p107">Se mostrarán hasta 5000 entradas en varias páginas. Especifique un intervalo de fechas menor si necesita limitar los resultados. Si selecciona un resultado de la búsqueda individual, se mostrará la siguiente información adicional en el panel de detalles:</span><span class="sxs-lookup"><span data-stu-id="e8992-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="e8992-133">**Objeto modificado:** el objeto modificado por el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e8992-133">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="e8992-134">**Parámetros (Parameter:Value):** los parámetros de cmdlet que se usaron y cualquier valor especificado con el parámetro.</span><span class="sxs-lookup"><span data-stu-id="e8992-134">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="e8992-135">Si desea imprimir una entrada específica del registro de auditoría, elija el botón **Imprimir** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="e8992-135">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="e8992-136">Usar PowerShell de EOP independiente para ver el registro de auditoría de administración</span><span class="sxs-lookup"><span data-stu-id="e8992-136">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="e8992-137">Puede usar PowerShell de EOP independiente para buscar entradas de registro de auditoría que cumplan los criterios especificados.</span><span class="sxs-lookup"><span data-stu-id="e8992-137">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="e8992-138">Utilice la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e8992-138">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="e8992-139">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="e8992-139">**Notes**:</span></span>

- <span data-ttu-id="e8992-140">Solo puede usar el parámetro _Parameters_ junto con el _parámetro Cmdlets._</span><span class="sxs-lookup"><span data-stu-id="e8992-140">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="e8992-141">El _parámetro ObjectIds_ filtra los resultados del objeto modificado por el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e8992-141">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="e8992-142">Un valor válido depende de cómo se represente el objeto en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="e8992-142">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="e8992-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e8992-143">For example:</span></span>

  - <span data-ttu-id="e8992-144">Nombre</span><span class="sxs-lookup"><span data-stu-id="e8992-144">Name</span></span>
  - <span data-ttu-id="e8992-145">Nombre canónico distintivo (por ejemplo, contoso.com/Users/Akia Al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="e8992-145">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="e8992-146">Es probable que deba usar otros parámetros de filtrado en este cmdlet para restringir los resultados e identificar los tipos de objetos que le interesan.</span><span class="sxs-lookup"><span data-stu-id="e8992-146">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="e8992-147">El _parámetro UserIds_ filtra los resultados del usuario que realizó el cambio (que ejecutó el cmdlet).</span><span class="sxs-lookup"><span data-stu-id="e8992-147">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="e8992-148">Para los _parámetros StartDate_ y _EndDate,_ si especifica un valor de fecha y hora sin zona horaria, el valor se encuentra en Hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="e8992-148">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="e8992-149">Para especificar un valor de fecha y hora para este parámetro, use una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e8992-149">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="e8992-150">Especifique el valor de fecha y hora en UTC; por ejemplo, "2016-05-06 14:30:00z".</span><span class="sxs-lookup"><span data-stu-id="e8992-150">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="e8992-151">Especifique el valor de fecha y hora como fórmula que convierte la fecha y hora de la zona horaria local a UTC: Por ejemplo, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` .</span><span class="sxs-lookup"><span data-stu-id="e8992-151">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="e8992-152">Para obtener más información, vea [Get-Date](/powershell/module/microsoft.powershell.utility/get-date).</span><span class="sxs-lookup"><span data-stu-id="e8992-152">For more information, see [Get-Date](/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="e8992-153">El cmdlet devuelve un máximo de 1.000 entradas de registro de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e8992-153">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="e8992-154">Use el _parámetro ResultSize_ para especificar hasta 250 000 entradas de registro.</span><span class="sxs-lookup"><span data-stu-id="e8992-154">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="e8992-155">O bien, use el valor `Unlimited` para devolver todas las entradas.</span><span class="sxs-lookup"><span data-stu-id="e8992-155">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="e8992-156">En este ejemplo se buscan todas las entradas del registro de auditoría con los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="e8992-156">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="e8992-157">**Fecha de inicio:** 4 de agosto de 2019</span><span class="sxs-lookup"><span data-stu-id="e8992-157">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="e8992-158">**Fecha de finalización:** 3 de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="e8992-158">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="e8992-159">**Cmdlets**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="e8992-159">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="e8992-160">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="e8992-160">For detailed syntax and parameter information, see [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="e8992-161">Ver los detalles de las entradas del registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="e8992-161">View details of audit log entries</span></span>

<span data-ttu-id="e8992-162">El cmdlet **Search-AdminAuditLog** devuelve los campos descritos en la sección [Contenidos](#audit-log-contents) del registro de auditoría más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="e8992-162">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this article.</span></span> <span data-ttu-id="e8992-163">De los campos devueltos por el cmdlet, dos campos, **CmdletParameters** y **ModifiedProperties,** contienen información adicional que no se devuelve de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e8992-163">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="e8992-164">Para ver el contenido de los campos **CmdletParameters** y **ModifiedProperties** siga los pasos que se describen a continuación.</span><span class="sxs-lookup"><span data-stu-id="e8992-164">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="e8992-165">Decida los criterios que desea buscar, ejecute el cmdlet **Search-AdminAuditLog** y guarde los resultados en una variable utilizando el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="e8992-165">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="e8992-166">Cada entrada de registro de auditoría se almacena como un elemento de matriz en la variable `$Results` .</span><span class="sxs-lookup"><span data-stu-id="e8992-166">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="e8992-167">Puede seleccionar un elemento de matriz especificando su índice de elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="e8992-167">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="e8992-168">Los índices de elemento de matriz comienzan en cero (0) para el primer elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="e8992-168">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="e8992-169">Por ejemplo, para recuperar el quinto elemento de matriz, que tiene un índice de 4, utilice el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="e8992-169">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="e8992-p115">El comando anterior devuelve la entrada de registro almacenada en el elemento de matriz 4. Para ver el contenido de los campos **CmdletParameters** y **ModifiedProperties** para esta entrada de registro, utilice los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="e8992-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="e8992-172">Para ver el contenido de los campos **CmdletParameters** o **ModifiedParameters** en otra entrada de registro, cambie el índice del elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="e8992-172">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="e8992-173">Contenido del registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="e8992-173">Audit log contents</span></span>

<span data-ttu-id="e8992-174">Todas las entradas del registro de auditoría contienen la información que se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e8992-174">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="e8992-175">El registro de auditoría contiene una o varias entradas de registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="e8992-175">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="e8992-176">Field</span><span class="sxs-lookup"><span data-stu-id="e8992-176">Field</span></span>|<span data-ttu-id="e8992-177">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8992-177">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="e8992-178">EOP usa internamente este campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-178">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="e8992-179">Este campo contiene el objeto modificado por el cmdlet especificado en el `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-179">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="e8992-180">Este campo contiene el nombre del cmdlet que el usuario ha ejecutado en el `Caller` campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-180">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="e8992-181">Este campo contiene los parámetros que se especificaron cuando se ejecutaba el cmdlet `CmdletName` del campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-181">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="e8992-182">En este campo también se almacena (aunque no es visible en la salida predeterminada) el valor especificado con el parámetro (si existe).</span><span class="sxs-lookup"><span data-stu-id="e8992-182">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="e8992-183">Este campo contiene las propiedades que se modificaron en el objeto del `ObjectModified` campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-183">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="e8992-184">Además, en este campo se almacenan el valor anterior de la propiedad y el nuevo valor almacenado, aunque no están visibles en los resultados predeterminados.</span><span class="sxs-lookup"><span data-stu-id="e8992-184">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="e8992-185">Este campo contiene la cuenta de usuario del usuario que ejecutó el cmdlet en el `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-185">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="e8992-186">EOP usa internamente este campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-186">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="e8992-187">Este campo especifica si el cmdlet del `CmdletName` campo se ejecutó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e8992-187">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="e8992-188">El valor es o `True` `False` .</span><span class="sxs-lookup"><span data-stu-id="e8992-188">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="e8992-189">Este campo contiene el mensaje de error generado si el cmdlet del `CmdletName` campo no se pudo completar correctamente.</span><span class="sxs-lookup"><span data-stu-id="e8992-189">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="e8992-190">Este campo contiene la fecha y hora en que se ha ejecutado el cmdlet `CmdletName` del campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-190">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="e8992-191">La fecha y la hora se almacenan en formato de hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="e8992-191">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="e8992-192">Este campo indica el servidor en el que se ha ejecutado el cmdlet especificado `CmdletName` en el campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-192">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="e8992-193">EOP usa internamente este campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-193">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="e8992-194">EOP usa internamente este campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-194">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="e8992-195">EOP usa internamente este campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-195">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="e8992-196">EOP usa internamente este campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-196">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="e8992-197">EOP usa internamente este campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-197">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="e8992-198">EOP usa internamente este campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-198">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="e8992-199">EOP usa internamente este campo.</span><span class="sxs-lookup"><span data-stu-id="e8992-199">This field is used internally by EOP.</span></span>|
|