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
ms.custom: seo-marvel-apr2020
description: Cómo activar o desactivar la característica de búsqueda de registro de auditoría en el Centro de seguridad y cumplimiento de & para habilitar o deshabilitar la capacidad de los administradores de buscar en el registro de auditoría.
ms.openlocfilehash: 3f3e1b913dd163e74f9e5359de772dfcbf3bd786
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423681"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="cae06-103">Activar o desactivar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="cae06-103">Turn audit log search on or off</span></span>

<span data-ttu-id="cae06-104">El registro de auditoría está activado de forma predeterminada para organizaciones de Microsoft 365 y Office 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cae06-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="cae06-105">Esto incluye las organizaciones con suscripciones a E3/G3 o E5/G5.</span><span class="sxs-lookup"><span data-stu-id="cae06-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="cae06-106">Cuando la búsqueda del registro de auditoría en el centro de cumplimiento está activada, la actividad de usuario y administrador de su organización se registra en el registro de auditoría y se retiene durante 90 días y hasta un año, según la licencia asignada a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="cae06-106">When audit log search in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="cae06-107">Sin embargo, es posible que la organización tenga motivos para no querer registrar y conservar los datos del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="cae06-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="cae06-108">En esos casos, un administrador global puede decidir desactivar la auditoría en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cae06-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cae06-109">Si desactiva la búsqueda de registro de auditoría en Microsoft 365, no puede usar la API de actividad de administración de Office 365 o Azure Sentinel para obtener acceso a los datos de auditoría de su organización.</span><span class="sxs-lookup"><span data-stu-id="cae06-109">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="cae06-110">Desactivar la búsqueda de registro de auditoría siguiendo los pasos descritos en este artículo significa que no se devolverá ningún resultado cuando busque en el registro de auditoría mediante el Centro de seguridad & cumplimiento o cuando ejecute el cmdlet **Search-UnifiedAuditLog** en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cae06-110">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="cae06-111">Esto también significa que los registros de auditoría no estarán disponibles a través de la API de actividad de administración de Office 365 o Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="cae06-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="cae06-112">Antes de activar o desactivar la búsqueda del registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="cae06-112">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="cae06-113">Debe tener asignado el rol Registros de auditoría en Exchange Online para activar o desactivar la búsqueda del registro de auditoría en su organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cae06-113">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="cae06-114">De forma predeterminada, este rol se asigna a los  grupos de roles Administración de cumplimiento y Administración de la organización en la página Permisos del Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="cae06-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="cae06-115">Los administradores globales de Microsoft 365 son miembros del grupo de roles Administración de la organización en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cae06-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="cae06-116">Los usuarios deben tener asignados permisos en Exchange Online para activar o desactivar la búsqueda del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="cae06-116">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="cae06-117">Si asigna a los usuarios  el rol Registros de auditoría en la página Permisos del Centro de seguridad y cumplimiento de &, no podrán activar o desactivar la búsqueda del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="cae06-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="cae06-118">Esto se debe a que el cmdlet subyacente es un cmdlet de PowerShell de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cae06-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 
    
- <span data-ttu-id="cae06-119">Para obtener instrucciones paso a paso sobre cómo buscar en el registro de auditoría, vea [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="cae06-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="cae06-120">Para obtener más información acerca de la API de actividad de administración de Microsoft 365, vea Introducción a las API de administración de [Microsoft 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="cae06-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="cae06-121">Para comprobar que la búsqueda de registros de auditoría está activada, puede ejecutar el comando siguiente en PowerShell de Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="cae06-121">To verify that audit log search is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="cae06-122">El valor de  `True` la  _propiedad UnifiedAuditLogIngestionEnabled_ indica que la búsqueda del registro de auditoría está activada.</span><span class="sxs-lookup"><span data-stu-id="cae06-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned on.</span></span> 
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="cae06-123">Activar la búsqueda del registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="cae06-123">Turn on audit log search</span></span>

<span data-ttu-id="cae06-124">Si la búsqueda del registro de auditoría no está activada para su organización, puede activarla en el centro de cumplimiento o mediante Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cae06-124">If audit log search is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="cae06-125">Puede tardar varias horas después de activar la búsqueda del registro de auditoría antes de que pueda devolver resultados al buscar en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="cae06-125">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="cae06-126">Usar el Centro de cumplimiento para activar la búsqueda del registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="cae06-126">Use the compliance center to turn on audit log search</span></span>

1. <span data-ttu-id="cae06-127">[Vaya al Centro de cumplimiento](https://protection.office.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="cae06-127">[Go to the compliance center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="cae06-128">En el Centro de cumplimiento, vaya a **Búsqueda de** registro de auditoría  >  **de búsqueda.**</span><span class="sxs-lookup"><span data-stu-id="cae06-128">In the compliance center, go to **Search** > **Audit log search**.</span></span>

   <span data-ttu-id="cae06-129">Si la búsqueda del registro de auditoría no está activada para su organización, se muestra un banner que dice que la auditoría debe estar activada para registrar la actividad de usuario y administrador.</span><span class="sxs-lookup"><span data-stu-id="cae06-129">If audit log search is not turned on for your organization, a banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="cae06-130">Haga **clic en Activar auditoría**.</span><span class="sxs-lookup"><span data-stu-id="cae06-130">Click **Turn on auditing**.</span></span>

    ![Haga clic en Activar auditoría](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="cae06-132">El banner se actualiza para decir que el registro de auditoría se está preparando y que puede buscar actividad de usuario y administrador en unas horas.</span><span class="sxs-lookup"><span data-stu-id="cae06-132">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="cae06-133">Usar PowerShell para activar la búsqueda del registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="cae06-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="cae06-134">Conectarse a Exchange Online mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="cae06-134">Connect to Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="cae06-135">Ejecute el siguiente comando de PowerShell para activar la búsqueda del registro de auditoría en Office 365.</span><span class="sxs-lookup"><span data-stu-id="cae06-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="cae06-136">Se muestra un mensaje que indica que el cambio puede tardar hasta 60 minutos en tener efecto.</span><span class="sxs-lookup"><span data-stu-id="cae06-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="cae06-137">Desactivar la búsqueda del registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="cae06-137">Turn off audit log search</span></span>

<span data-ttu-id="cae06-138">Debe usar Exchange Online PowerShell para desactivar la búsqueda del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="cae06-138">You have to use Exchange Online PowerShell to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="cae06-139">Conectarse a Exchange Online mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="cae06-139">Connect to Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="cae06-140">Ejecute el siguiente comando de PowerShell para desactivar la búsqueda del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="cae06-140">Run the following PowerShell command to turn off audit log search.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="cae06-141">Después de un tiempo, compruebe que la búsqueda del registro de auditoría está desactivada (deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="cae06-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="cae06-142">Puede realizar esto de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="cae06-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="cae06-143">En Exchange Online PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="cae06-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="cae06-144">El valor de  `False` la  _propiedad UnifiedAuditLogIngestionEnabled_ indica que la búsqueda del registro de auditoría está desactivada.</span><span class="sxs-lookup"><span data-stu-id="cae06-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="cae06-145">En el [Centro de cumplimiento,](https://protection.office.com)vaya a **Búsqueda de** registro de auditoría de \> **búsqueda.**</span><span class="sxs-lookup"><span data-stu-id="cae06-145">In the [compliance center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="cae06-146">Se muestra un banner que dice que la auditoría debe estar activada para registrar la actividad de usuario y administrador.</span><span class="sxs-lookup"><span data-stu-id="cae06-146">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>
