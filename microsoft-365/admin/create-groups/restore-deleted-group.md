---
title: Restaurar un grupo de Office 365 eliminado
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Obtenga información sobre cómo restaurar un grupo de Office 365 eliminado.
ms.openlocfilehash: 31d6481f87d7da219e042eefa8f004425caee133
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583167"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="12ba3-103">Restaurar un grupo de Office 365 eliminado</span><span class="sxs-lookup"><span data-stu-id="12ba3-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="12ba3-104">Si ha eliminado un grupo, se conservará durante 30 días de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="12ba3-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="12ba3-105">Este período de 30 días se considera una "eliminación temporal" porque todavía puede restaurar el grupo.</span><span class="sxs-lookup"><span data-stu-id="12ba3-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="12ba3-106">Transcurrido el plazo de 30 días, el grupo y su contenido asociado se eliminan de forma permanente y no se pueden restaurar.</span><span class="sxs-lookup"><span data-stu-id="12ba3-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="12ba3-107">Cuando se restaura un grupo, se restaura el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="12ba3-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="12ba3-108">Azure Active Directory (AD) Office 365 Groups (objeto, propiedades y miembros).</span><span class="sxs-lookup"><span data-stu-id="12ba3-108">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="12ba3-109">Direcciones de correo electrónico del grupo.</span><span class="sxs-lookup"><span data-stu-id="12ba3-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="12ba3-110">Bandeja de entrada y calendario compartidos de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="12ba3-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="12ba3-111">Sitio de grupo y archivos de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="12ba3-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="12ba3-112">Bloc de notas de OneNote</span><span class="sxs-lookup"><span data-stu-id="12ba3-112">OneNote notebook</span></span>
    
- <span data-ttu-id="12ba3-113">Planner</span><span class="sxs-lookup"><span data-stu-id="12ba3-113">Planner</span></span>
    
- <span data-ttu-id="12ba3-114">Teams</span><span class="sxs-lookup"><span data-stu-id="12ba3-114">Teams</span></span>

- <span data-ttu-id="12ba3-115">Grupo de Yammer y contenido del grupo (si se creó el grupo de Office 365 desde Yammer)</span><span class="sxs-lookup"><span data-stu-id="12ba3-115">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook"></a><span data-ttu-id="12ba3-116">Restaurar un grupo de su propiedad mediante Outlook</span><span class="sxs-lookup"><span data-stu-id="12ba3-116">Restore a group that you own by using Outlook</span></span>

<span data-ttu-id="12ba3-117">Si es el propietario de un grupo de Office 365, puede restaurar el grupo personalmente en Outlook siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="12ba3-117">If you are the owner of an Office 365 group, you can restore the group yourself in Outlook by following these steps:</span></span>

1. <span data-ttu-id="12ba3-118">En la [Página grupos eliminados](https://outlook.office.com/people/group/deleted), seleccione la opción **administrar grupos** en el nodo **grupos** y, a continuación, elija **eliminado**.</span><span class="sxs-lookup"><span data-stu-id="12ba3-118">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="12ba3-119">Haga clic en la pestaña **restaurar** situada junto al grupo que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="12ba3-119">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="12ba3-120">Si el grupo eliminado no aparece aquí, póngase en contacto con un administrador.</span><span class="sxs-lookup"><span data-stu-id="12ba3-120">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="12ba3-121">Restaurar un grupo en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="12ba3-121">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="12ba3-122">Si es administrador global o administrador de grupos, puede restaurar un grupo eliminado en el centro de administración de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="12ba3-122">If you are a global administrator or a groups admin, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="12ba3-123">Vaya al centro de administración en [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="12ba3-123">Go to the admin center at [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="12ba3-124">Expanda **grupos**y, a continuación, haga clic en **grupos eliminados**.</span><span class="sxs-lookup"><span data-stu-id="12ba3-124">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="12ba3-125">Seleccione el grupo que desea restaurar y, a continuación, haga clic en **restaurar grupo**.</span><span class="sxs-lookup"><span data-stu-id="12ba3-125">Select the group that you want to restore, and then click **Restore group**.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="12ba3-126">Eliminar permanentemente un grupo de Office 365</span><span class="sxs-lookup"><span data-stu-id="12ba3-126">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="12ba3-127">A veces, es posible que desee purgar un grupo de forma permanente sin esperar a que expire el período de eliminación de software de 30 días.</span><span class="sxs-lookup"><span data-stu-id="12ba3-127">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="12ba3-128">Para ello, inicie PowerShell y ejecute este comando para obtener el identificador de objeto del Grupo:</span><span class="sxs-lookup"><span data-stu-id="12ba3-128">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="12ba3-129">Anote el identificador de objeto del grupo o grupos que desea eliminar de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="12ba3-129">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="12ba3-130">Purgar el grupo elimina el grupo y sus datos para siempre.</span><span class="sxs-lookup"><span data-stu-id="12ba3-130">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="12ba3-131">Para purgar el grupo, ejecute este comando en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="12ba3-131">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="12ba3-p103">Para confirmar que el grupo se ha purgado correctamente, ejecute el cmdlet  *Get-AzureADMSDeletedGroup*  de nuevo para confirmar que el grupo ya no aparece en la lista de grupos eliminados temporalmente. En algunos casos, la eliminación permanente del grupo y todos sus datos puede tardar hasta 24 horas.</span><span class="sxs-lookup"><span data-stu-id="12ba3-p103">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="12ba3-134">¿Tiene preguntas sobre los grupos de Office 365?</span><span class="sxs-lookup"><span data-stu-id="12ba3-134">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="12ba3-135">Visite [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para publicar preguntas y participar en conversaciones sobre grupos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="12ba3-135">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="12ba3-136">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="12ba3-136">Related articles</span></span>

[<span data-ttu-id="12ba3-137">Administrar grupos de Office 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="12ba3-137">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="12ba3-138">Eliminar grupos mediante el cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="12ba3-138">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="12ba3-139">Administrar la configuración de su sitio de grupo conectado</span><span class="sxs-lookup"><span data-stu-id="12ba3-139">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="12ba3-140">Eliminar un grupo en Outlook</span><span class="sxs-lookup"><span data-stu-id="12ba3-140">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
