---
title: Restaurar un grupo eliminado
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Obtenga información sobre cómo restaurar un grupo de Microsoft 365 eliminado.
ms.openlocfilehash: d7cf548816af1661298458f27c704d654845075d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818512"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="94b2f-103">Restaurar un grupo eliminado</span><span class="sxs-lookup"><span data-stu-id="94b2f-103">Restore a deleted Group</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="94b2f-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="94b2f-104">The admin center is changing.</span></span> <span data-ttu-id="94b2f-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="94b2f-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="94b2f-106">Si ha eliminado un grupo, se conservará durante 30 días de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="94b2f-106">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="94b2f-107">Este período de 30 días se considera una "eliminación temporal" porque todavía puede restaurar el grupo.</span><span class="sxs-lookup"><span data-stu-id="94b2f-107">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="94b2f-108">Transcurrido el plazo de 30 días, el grupo y su contenido asociado se eliminan de forma permanente y no se pueden restaurar.</span><span class="sxs-lookup"><span data-stu-id="94b2f-108">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="94b2f-109">Cuando se restaura un grupo, se restaura el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="94b2f-109">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="94b2f-110">Azure Active Directory (AD) Microsoft 365 Groups (objeto, propiedades y miembros).</span><span class="sxs-lookup"><span data-stu-id="94b2f-110">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="94b2f-111">Direcciones de correo electrónico del grupo.</span><span class="sxs-lookup"><span data-stu-id="94b2f-111">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="94b2f-112">Bandeja de entrada y calendario compartidos de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="94b2f-112">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="94b2f-113">Sitio de grupo y archivos de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="94b2f-113">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="94b2f-114">Bloc de notas de OneNote</span><span class="sxs-lookup"><span data-stu-id="94b2f-114">OneNote notebook</span></span>
    
- <span data-ttu-id="94b2f-115">Planner</span><span class="sxs-lookup"><span data-stu-id="94b2f-115">Planner</span></span>
    
- <span data-ttu-id="94b2f-116">Teams</span><span class="sxs-lookup"><span data-stu-id="94b2f-116">Teams</span></span>

- <span data-ttu-id="94b2f-117">Grupo de Yammer y contenido del grupo (si el grupo de Microsoft 365 se creó desde Yammer)</span><span class="sxs-lookup"><span data-stu-id="94b2f-117">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a><span data-ttu-id="94b2f-118">Restaurar un grupo de su propiedad mediante Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="94b2f-118">Restore a group that you own by using Outlook on the web</span></span>

<span data-ttu-id="94b2f-119">Si es el propietario de un grupo de Microsoft 365, puede restaurar el grupo personalmente en Outlook en la web siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="94b2f-119">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="94b2f-120">En la [Página grupos eliminados](https://outlook.office.com/people/group/deleted), seleccione la opción **administrar grupos** en el nodo **grupos** y, a continuación, elija **eliminado**.</span><span class="sxs-lookup"><span data-stu-id="94b2f-120">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="94b2f-121">Haga clic en la pestaña **restaurar** situada junto al grupo que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="94b2f-121">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="94b2f-122">Si el grupo eliminado no aparece aquí, póngase en contacto con un administrador.</span><span class="sxs-lookup"><span data-stu-id="94b2f-122">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="94b2f-123">Restaurar un grupo en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="94b2f-123">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="94b2f-124">Si es administrador global o administrador de grupos, puede restaurar un grupo eliminado en el centro de administración de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="94b2f-124">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="94b2f-125">Vaya al [centro de administración](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="94b2f-125">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="94b2f-126">Expanda **grupos**y, a continuación, haga clic en **grupos eliminados**.</span><span class="sxs-lookup"><span data-stu-id="94b2f-126">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="94b2f-127">Seleccione el grupo que desea restaurar y, a continuación, haga clic en **restaurar grupo**.</span><span class="sxs-lookup"><span data-stu-id="94b2f-127">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="94b2f-128">En algunos casos, puede tardar hasta 24 horas en restaurar el grupo y todos sus datos.</span><span class="sxs-lookup"><span data-stu-id="94b2f-128">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="94b2f-129">Eliminar de forma permanente un grupo de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="94b2f-129">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="94b2f-130">A veces, es posible que desee purgar un grupo de forma permanente sin esperar a que expire el período de eliminación de software de 30 días.</span><span class="sxs-lookup"><span data-stu-id="94b2f-130">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="94b2f-131">Para ello, inicie PowerShell y ejecute este comando para obtener el identificador de objeto del Grupo:</span><span class="sxs-lookup"><span data-stu-id="94b2f-131">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="94b2f-132">Anote el identificador de objeto del grupo o grupos que desea eliminar de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="94b2f-132">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="94b2f-133">Purgar el grupo elimina el grupo y sus datos para siempre.</span><span class="sxs-lookup"><span data-stu-id="94b2f-133">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="94b2f-134">Para purgar el grupo, ejecute este comando en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="94b2f-134">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="94b2f-135">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups.</span><span class="sxs-lookup"><span data-stu-id="94b2f-135">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups.</span></span> <span data-ttu-id="94b2f-136">In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span><span class="sxs-lookup"><span data-stu-id="94b2f-136">In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="94b2f-137">¿Tiene preguntas acerca de los grupos de Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="94b2f-137">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="94b2f-138">Visite [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para publicar preguntas y participar en conversaciones sobre grupos de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="94b2f-138">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="94b2f-139">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="94b2f-139">Related articles</span></span>

[<span data-ttu-id="94b2f-140">Administración de grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="94b2f-140">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
[<span data-ttu-id="94b2f-141">Eliminar grupos mediante el cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="94b2f-141">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="94b2f-142">Administrar la configuración de su sitio de grupo conectado</span><span class="sxs-lookup"><span data-stu-id="94b2f-142">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="94b2f-143">Eliminar un grupo en Outlook</span><span class="sxs-lookup"><span data-stu-id="94b2f-143">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
