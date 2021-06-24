---
title: Activar o desactivar la auditoría
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: Cómo activar o desactivar la característica de búsqueda de registro de auditoría en el Centro de cumplimiento de Microsoft 365 para habilitar o deshabilitar la capacidad de los administradores de buscar en el registro de auditoría.
ms.openlocfilehash: 7c55443eda9a99ff4ef153d8564fd9ac43fcc549
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105313"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="76477-103">Activar o desactivar la auditoría</span><span class="sxs-lookup"><span data-stu-id="76477-103">Turn auditing on or off</span></span>

<span data-ttu-id="76477-104">El registro de auditoría está activado de forma predeterminada para organizaciones de Microsoft 365 y Office 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="76477-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="76477-105">Esto incluye las organizaciones con suscripciones a E3/G3 o E5/G5.</span><span class="sxs-lookup"><span data-stu-id="76477-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="76477-106">Cuando la auditoría en el centro de cumplimiento está activada, la actividad de usuario y administrador de su organización se registra en el registro de auditoría y se retiene durante 90 días y hasta un año, según la licencia asignada a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="76477-106">When auditing in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="76477-107">Sin embargo, es posible que la organización tenga motivos para no querer registrar y conservar los datos del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="76477-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="76477-108">En esos casos, un administrador global puede decidir desactivar la auditoría en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76477-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76477-109">Si desactiva la auditoría en Microsoft 365, no puede usar la API de actividad de administración de Office 365 ni Azure Sentinel para obtener acceso a los datos de auditoría de su organización.</span><span class="sxs-lookup"><span data-stu-id="76477-109">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="76477-110">Desactivar la auditoría siguiendo los pasos descritos en este artículo significa que no se devolverá ningún resultado al buscar en el registro de auditoría mediante el Centro de seguridad y cumplimiento de & o al ejecutar el cmdlet **Search-UnifiedAuditLog** en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76477-110">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="76477-111">Esto también significa que los registros de auditoría no estarán disponibles a través de la API Office 365 actividad de administración o Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="76477-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="76477-112">Antes de activar o desactivar la auditoría</span><span class="sxs-lookup"><span data-stu-id="76477-112">Before you turn auditing on or off</span></span>

- <span data-ttu-id="76477-113">Debe tener asignado el rol Registros de auditoría en Exchange Online para activar o desactivar la auditoría en su Microsoft 365 organización.</span><span class="sxs-lookup"><span data-stu-id="76477-113">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="76477-114">De forma predeterminada, este rol se asigna a los  grupos de roles Administración de cumplimiento y Administración de la organización en la página Permisos del centro Exchange administración.</span><span class="sxs-lookup"><span data-stu-id="76477-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="76477-115">Los administradores globales de Microsoft 365 son miembros del grupo de roles Administración de la organización en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="76477-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="76477-116">Los usuarios deben tener asignados permisos en Exchange Online para activar o desactivar la auditoría.</span><span class="sxs-lookup"><span data-stu-id="76477-116">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="76477-117">Si asigna a los usuarios  el rol Registros de auditoría en la página Permisos del Centro de seguridad y cumplimiento de &, no podrán activar o desactivar la auditoría.</span><span class="sxs-lookup"><span data-stu-id="76477-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="76477-118">Esto se debe a que el cmdlet subyacente es Exchange Online cmdlet de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76477-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span>

- <span data-ttu-id="76477-119">Para obtener instrucciones paso a paso sobre cómo buscar en el registro de auditoría, vea [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="76477-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="76477-120">Para obtener más información acerca de la API Microsoft 365 actividad de administración, vea Introducción [a Microsoft 365 API de administración](/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="76477-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="76477-121">Para comprobar que la auditoría está activada, puede ejecutar el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="76477-121">To verify that auditing is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="76477-122">El valor de  `True` la  _propiedad UnifiedAuditLogIngestionEnabled_ indica que la auditoría está activada.</span><span class="sxs-lookup"><span data-stu-id="76477-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> 

## <a name="turn-on-auditing"></a><span data-ttu-id="76477-123">Activar la auditoría</span><span class="sxs-lookup"><span data-stu-id="76477-123">Turn on auditing</span></span>

<span data-ttu-id="76477-124">Si la auditoría no está activada para su organización, puede activarla en el centro de cumplimiento o mediante Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76477-124">If auditing is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="76477-125">Puede tardar varias horas después de activar la auditoría antes de que pueda devolver resultados al buscar en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="76477-125">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="76477-126">Usar el Centro de cumplimiento para activar la auditoría</span><span class="sxs-lookup"><span data-stu-id="76477-126">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="76477-127">Vaya a <https://compliance.microsoft.com> e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="76477-127">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="76477-128">En el panel de navegación izquierdo de la Centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todo** y, a continuación, haga clic en **Auditar**.</span><span class="sxs-lookup"><span data-stu-id="76477-128">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

   <span data-ttu-id="76477-129">Si la auditoría no está activada para su organización, se muestra un banner que le pedirá que comience a grabar la actividad de usuario y administrador.</span><span class="sxs-lookup"><span data-stu-id="76477-129">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![Banner en la página Auditoría](../media/AuditingBanner.png)

3. <span data-ttu-id="76477-131">Haga clic en **el banner Iniciar registro de actividad de usuario y** administrador.</span><span class="sxs-lookup"><span data-stu-id="76477-131">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="76477-132">El cambio puede tardar hasta 60 minutos en tener efecto.</span><span class="sxs-lookup"><span data-stu-id="76477-132">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="76477-133">Usar PowerShell para activar la auditoría</span><span class="sxs-lookup"><span data-stu-id="76477-133">Use PowerShell to turn on auditing</span></span>

1. [<span data-ttu-id="76477-134">Conectarse al PowerShell de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="76477-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="76477-135">Ejecute el siguiente comando de PowerShell para activar la auditoría en Office 365.</span><span class="sxs-lookup"><span data-stu-id="76477-135">Run the following PowerShell command to turn on auditing in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="76477-136">Se muestra un mensaje que indica que el cambio puede tardar hasta 60 minutos en tener efecto.</span><span class="sxs-lookup"><span data-stu-id="76477-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="76477-137">Desactivar la auditoría</span><span class="sxs-lookup"><span data-stu-id="76477-137">Turn off auditing</span></span>

<span data-ttu-id="76477-138">Debe usar powershell Exchange Online para desactivar la auditoría.</span><span class="sxs-lookup"><span data-stu-id="76477-138">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. [<span data-ttu-id="76477-139">Conectarse al PowerShell de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="76477-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="76477-140">Ejecute el siguiente comando de PowerShell para desactivar la auditoría.</span><span class="sxs-lookup"><span data-stu-id="76477-140">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="76477-141">Después de un tiempo, compruebe que la auditoría está desactivada (deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="76477-141">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="76477-142">Hay dos formas de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="76477-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="76477-143">En Exchange Online PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="76477-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="76477-144">El valor de  `False` la  _propiedad UnifiedAuditLogIngestionEnabled_ indica que la auditoría está desactivada.</span><span class="sxs-lookup"><span data-stu-id="76477-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="76477-145">Vaya a la **página Auditoría** de la Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76477-145">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="76477-146">Si la auditoría no está activada para su organización, se muestra un banner que le pedirá que comience a grabar la actividad de usuario y administrador.</span><span class="sxs-lookup"><span data-stu-id="76477-146">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
