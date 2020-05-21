---
title: Activar o desactivar la búsqueda de registros de auditoría
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
description: Puede activar la característica de búsqueda de registros de auditoría en el centro de seguridad & cumplimiento. Si cambia de opinión, puede desactivar la opción en cualquier momento. Cuando la búsqueda de registros de auditoría está desactivada, los administradores no pueden buscar en el registro de auditoría de Microsoft 365 la actividad de usuario y de administrador de su organización.
ms.openlocfilehash: f3d88f62f466d9c868dfc6addb5865e144f5223b
ms.sourcegitcommit: 56772bed89516cebc5eb370e292ccfbb4889cb38
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330794"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="4bf58-105">Activar o desactivar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="4bf58-105">Turn audit log search on or off</span></span>

<span data-ttu-id="4bf58-106">Usted (u otro administrador) deben activar el registro de auditoría antes de empezar a buscar en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="4bf58-106">You (or another admin) must turn on audit logging before you can start searching the audit log.</span></span> <span data-ttu-id="4bf58-107">Cuando se activa la búsqueda de registros de auditoría en el centro de seguridad & cumplimiento, la actividad de usuario y administrador de la organización se registra en el registro de auditoría y se conserva durante 90 días, y hasta un año según la licencia asignada a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4bf58-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="4bf58-108">Sin embargo, es posible que su organización tenga motivos para no querer registrar y conservar los datos del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="4bf58-108">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="4bf58-109">En esos casos, un administrador global puede decidir desactivar la auditoría en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4bf58-109">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4bf58-110">Si desactiva la búsqueda de registros de auditoría en Microsoft 365, no podrá usar la API de actividad de administración de Office 365 o Azure Sentinel para acceder a los datos de auditoría de su organización.</span><span class="sxs-lookup"><span data-stu-id="4bf58-110">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="4bf58-111">La desactivación de la búsqueda de registros de auditoría siguiendo los pasos descritos en este artículo significa que no se devolverán resultados cuando busque en el registro de auditoría mediante el centro de seguridad & cumplimiento o cuando ejecute el cmdlet **Search-UnifiedAuditLog** en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4bf58-111">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="4bf58-112">Esto también significa que los registros de auditoría no estarán disponibles a través de la API de actividad de administración de Office 365 o de Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="4bf58-112">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="4bf58-113">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="4bf58-113">Before you begin</span></span>

- <span data-ttu-id="4bf58-114">Debe tener asignado el rol registros de auditoría en Exchange Online para activar o desactivar la búsqueda de registros de auditoría en su organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4bf58-114">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="4bf58-115">De forma predeterminada, este rol se asigna a los grupos de roles administración de cumplimiento y administración de la organización en la página **permisos** del centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="4bf58-115">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="4bf58-116">Los administradores globales de Microsoft 365 son miembros del grupo de roles administración de la organización en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4bf58-116">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4bf58-117">Los usuarios deben tener asignados permisos en Exchange Online para activar o desactivar la búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="4bf58-117">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="4bf58-118">Si asigna a los usuarios el rol registros de auditoría en la página **permisos** del centro de seguridad & cumplimiento, no podrán activar o desactivar la búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="4bf58-118">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="4bf58-119">Esto se debe a que el cmdlet subyacente es un cmdlet de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4bf58-119">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
    
- <span data-ttu-id="4bf58-120">Para obtener instrucciones paso a paso sobre cómo buscar en el registro de auditoría, vea [Buscar en el registro de auditoría del centro de seguridad & cumplimiento](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="4bf58-120">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="4bf58-121">Para obtener más información sobre la API de actividad de administración de Microsoft 365, consulte Introducción [a las API de administración de microsoft 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="4bf58-121">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="4bf58-122">Activar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="4bf58-122">Turn on audit log search</span></span>

<span data-ttu-id="4bf58-123">Puede usar el centro de seguridad & cumplimiento o PowerShell para activar la búsqueda de registros de auditoría en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4bf58-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Microsoft 365.</span></span> <span data-ttu-id="4bf58-124">Puede tardar varias horas después de activar la búsqueda de registros de auditoría para poder devolver los resultados cuando busque en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="4bf58-124">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="4bf58-125">Debe tener asignado el rol registros de auditoría en Exchange Online para activar la búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="4bf58-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="4bf58-126">Usar el centro de seguridad & cumplimiento para activar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="4bf58-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="4bf58-127">[Vaya al centro de seguridad & cumplimiento](https://protection.office.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="4bf58-127">[Go to the Security & Compliance Center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="4bf58-128">En el centro de seguridad & cumplimiento, vaya a búsqueda de registros de auditoría de **búsqueda** \> **Audit log search**.</span><span class="sxs-lookup"><span data-stu-id="4bf58-128">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>

   <span data-ttu-id="4bf58-129">Se muestra un banner en el que se indica que se debe activar la auditoría para registrar la actividad de usuario y de administrador.</span><span class="sxs-lookup"><span data-stu-id="4bf58-129">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="4bf58-130">Haga clic en **Activar auditoría**.</span><span class="sxs-lookup"><span data-stu-id="4bf58-130">Click **Turn on auditing**.</span></span>

    ![Haga clic en activar auditoría](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="4bf58-132">El banner se actualiza para indicar que se está preparando el registro de auditoría y que puede buscar la actividad de usuario y de administrador en unas horas.</span><span class="sxs-lookup"><span data-stu-id="4bf58-132">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="4bf58-133">Usar PowerShell para activar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="4bf58-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="4bf58-134">Conectarse a Exchange Online mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bf58-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="4bf58-135">Ejecute el siguiente comando de PowerShell para activar la búsqueda de registros de auditoría en Office 365.</span><span class="sxs-lookup"><span data-stu-id="4bf58-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="4bf58-136">Se muestra un mensaje que indica que puede tardar hasta 60 minutos para que el cambio surta efecto.</span><span class="sxs-lookup"><span data-stu-id="4bf58-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="4bf58-137">Desactivar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="4bf58-137">Turn off audit log search</span></span>

<span data-ttu-id="4bf58-138">Debe usar PowerShell remoto conectado a su organización de Exchange Online para desactivar la búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="4bf58-138">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="4bf58-139">De forma similar a activar la búsqueda de registros de auditoría, debe tener asignado el rol registros de auditoría en Exchange Online para desactivar la búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="4bf58-139">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="4bf58-140">Conectarse a Exchange Online mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bf58-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="4bf58-141">Ejecute el siguiente comando de PowerShell para desactivar la búsqueda de registros de auditoría en Office 365.</span><span class="sxs-lookup"><span data-stu-id="4bf58-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="4bf58-142">Después de un rato, compruebe que la búsqueda de registros de auditoría está desactivada (deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="4bf58-142">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="4bf58-143">Puede realizar esto de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="4bf58-143">There are two ways to do this:</span></span>

    - <span data-ttu-id="4bf58-144">En PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4bf58-144">In PowerShell, run the following command:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      <span data-ttu-id="4bf58-145">El valor de `False` para la propiedad _UnifiedAuditLogIngestionEnabled_ indica que la búsqueda de registros de auditoría está desactivada.</span><span class="sxs-lookup"><span data-stu-id="4bf58-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="4bf58-146">En el [centro de seguridad & cumplimiento](https://protection.office.com), vaya a búsqueda de registros de auditoría de **búsqueda** \> **Audit log search**.</span><span class="sxs-lookup"><span data-stu-id="4bf58-146">In the [Security & Compliance Center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="4bf58-147">Se muestra un banner en el que se indica que se debe activar la auditoría para poder registrar la actividad de usuario y de administrador.</span><span class="sxs-lookup"><span data-stu-id="4bf58-147">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>