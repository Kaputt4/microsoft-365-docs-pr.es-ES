---
title: Activar o desactivar la búsqueda de registros de auditoría de Office 365
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
description: Puede activar la característica de búsqueda de registros de auditoría en el centro de seguridad & cumplimiento. Si cambia de opinión, puede desactivar la opción en cualquier momento. Cuando la búsqueda de registros de auditoría está desactivada, los administradores no pueden buscar en el registro de auditoría de Office 365 la actividad de usuario y de administrador de su organización.
ms.openlocfilehash: dfa637bfe6df0e4643d96a921a604ea5d0deba9b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601377"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="32f2d-105">Activar o desactivar la búsqueda de registros de auditoría de Office 365</span><span class="sxs-lookup"><span data-stu-id="32f2d-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="32f2d-106">Usted (u otro administrador) deben activar el registro de auditoría para poder empezar a buscar en el registro de auditoría de Office 365.</span><span class="sxs-lookup"><span data-stu-id="32f2d-106">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log.</span></span> <span data-ttu-id="32f2d-107">Cuando se activa la búsqueda de registros de auditoría en el centro de seguridad & cumplimiento, la actividad de usuario y administrador de la organización se registra en el registro de auditoría y se conserva durante 90 días.</span><span class="sxs-lookup"><span data-stu-id="32f2d-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days.</span></span> <span data-ttu-id="32f2d-108">Sin embargo, es posible que su organización no desee registrar y conservar los datos del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="32f2d-108">However, your organization may not want to record and retain audit log data.</span></span> <span data-ttu-id="32f2d-109">O puede que esté usando una aplicación de administración de eventos e información de seguridad (SIEM) de terceros para acceder a los datos de auditoría.</span><span class="sxs-lookup"><span data-stu-id="32f2d-109">Or you may be using a third-party security information and event management (SIEM) application to access your auditing data.</span></span> <span data-ttu-id="32f2d-110">En esos casos, un administrador global puede desactivar la búsqueda de registros de auditoría en Office 365.</span><span class="sxs-lookup"><span data-stu-id="32f2d-110">In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="32f2d-111">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="32f2d-111">Before you begin</span></span>

- <span data-ttu-id="32f2d-112">Debe tener asignado el rol registros de auditoría en Exchange Online para activar o desactivar la búsqueda de registros de auditoría en su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="32f2d-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization.</span></span> <span data-ttu-id="32f2d-113">De forma predeterminada, este rol se asigna a los grupos de roles administración de cumplimiento y administración de la organización en la página **permisos** del centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="32f2d-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="32f2d-114">Los administradores globales de Office 365 son miembros del grupo de funciones de administración de la organización en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="32f2d-114">Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="32f2d-115">Los usuarios deben tener asignados permisos en Exchange Online para activar o desactivar la búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="32f2d-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="32f2d-116">Si asigna a los usuarios el rol registros de auditoría en la página **permisos** del centro de seguridad & cumplimiento, no podrán activar o desactivar la búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="32f2d-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="32f2d-117">Esto se debe a que el cmdlet subyacente es un cmdlet de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="32f2d-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="32f2d-118">Si desactiva la búsqueda de registros de auditoría en Office 365, no podrá usar la API de actividad de administración de Office 365 para acceder a los datos de auditoría de su organización.</span><span class="sxs-lookup"><span data-stu-id="32f2d-118">If you turn off audit log search in Office 365, you can't use the Office 365 Management Activity API to access auditing data for your organization.</span></span> <span data-ttu-id="32f2d-119">La desactivación de la búsqueda de registros de auditoría siguiendo los pasos descritos en este artículo significa que no se devolverán resultados cuando busque en el registro de auditoría mediante el centro de seguridad & cumplimiento o cuando ejecute el cmdlet **Search-UnifiedAuditLog** en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32f2d-119">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="32f2d-120">Esto también significa que los registros de auditoría no estarán disponibles a través de la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="32f2d-120">This also means that your audit logs won't be available through the Office 365 Management Activity API.</span></span>  
    
- <span data-ttu-id="32f2d-121">Para obtener instrucciones paso a paso sobre cómo buscar en el registro de auditoría de Office 365, vea [Buscar el registro de auditoría en el centro de seguridad & cumplimiento](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="32f2d-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="32f2d-122">Activar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="32f2d-122">Turn on audit log search</span></span>

<span data-ttu-id="32f2d-123">Puede usar el centro de seguridad & cumplimiento o PowerShell para activar la búsqueda de registros de auditoría en Office 365.</span><span class="sxs-lookup"><span data-stu-id="32f2d-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Office 365.</span></span> <span data-ttu-id="32f2d-124">Puede tardar varias horas después de activar la búsqueda de registros de auditoría para poder devolver los resultados cuando busque en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="32f2d-124">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="32f2d-125">Debe tener asignado el rol registros de auditoría en Exchange Online para activar la búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="32f2d-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="32f2d-126">Usar el centro de seguridad & cumplimiento para activar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="32f2d-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="32f2d-127">En el centro de seguridad & cumplimiento, vaya a búsqueda de **registros de auditoría**de **búsqueda** \> .</span><span class="sxs-lookup"><span data-stu-id="32f2d-127">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
   <span data-ttu-id="32f2d-128">Se muestra un banner en el que se indica que se debe activar la auditoría para registrar la actividad de usuario y de administrador.</span><span class="sxs-lookup"><span data-stu-id="32f2d-128">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

2. <span data-ttu-id="32f2d-129">Haga clic en **Activar auditoría**.</span><span class="sxs-lookup"><span data-stu-id="32f2d-129">Click **Turn on auditing**.</span></span>
    
    ![Haga clic en activar auditoría](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="32f2d-131">El banner se actualiza para indicar que se está preparando el registro de auditoría y que puede buscar la actividad de usuario y de administrador en unas horas.</span><span class="sxs-lookup"><span data-stu-id="32f2d-131">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="32f2d-132">Usar PowerShell para activar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="32f2d-132">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="32f2d-133">Conectarse a Exchange Online mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="32f2d-133">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="32f2d-134">Ejecute el siguiente comando de PowerShell para activar la búsqueda de registros de auditoría en Office 365.</span><span class="sxs-lookup"><span data-stu-id="32f2d-134">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="32f2d-135">Se muestra un mensaje que indica que puede tardar hasta 60 minutos para que el cambio surta efecto.</span><span class="sxs-lookup"><span data-stu-id="32f2d-135">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="32f2d-136">Desactivar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="32f2d-136">Turn off audit log search</span></span>

<span data-ttu-id="32f2d-137">Debe usar PowerShell remoto conectado a su organización de Exchange Online para desactivar la búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="32f2d-137">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="32f2d-138">De forma similar a activar la búsqueda de registros de auditoría, debe tener asignado el rol registros de auditoría en Exchange Online para desactivar la búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="32f2d-138">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="32f2d-139">Conectarse a Exchange Online mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="32f2d-139">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="32f2d-140">Ejecute el siguiente comando de PowerShell para desactivar la búsqueda de registros de auditoría en Office 365.</span><span class="sxs-lookup"><span data-stu-id="32f2d-140">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="32f2d-141">Después de un rato, compruebe que la búsqueda de registros de auditoría está desactivada (deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="32f2d-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="32f2d-142">Puede realizar esto de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="32f2d-142">There are two ways to do this:</span></span>
    
    - <span data-ttu-id="32f2d-143">En PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="32f2d-143">In PowerShell, run the following command:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      <span data-ttu-id="32f2d-144">El valor de `False` para la propiedad _UnifiedAuditLogIngestionEnabled_ indica que la búsqueda de registros de auditoría está desactivada.</span><span class="sxs-lookup"><span data-stu-id="32f2d-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="32f2d-145">En el centro de seguridad & cumplimiento, vaya a búsqueda de **registros de auditoría**de **búsqueda** \> .</span><span class="sxs-lookup"><span data-stu-id="32f2d-145">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
      <span data-ttu-id="32f2d-146">Se muestra un banner en el que se indica que se debe activar la auditoría para poder registrar la actividad de usuario y de administrador.</span><span class="sxs-lookup"><span data-stu-id="32f2d-146">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>
