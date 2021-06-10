---
title: Restaurar un grupo Microsoft 365 eliminado
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Un grupo eliminado se conserva durante 30 días y aún puede restaurar el grupo. Después de 30 días, el grupo y su contenido se eliminan permanentemente.
ms.openlocfilehash: 2c20c2bd3ce91331e7160132047dbf3ecd79c4b8
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635743"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="3c7f8-104">Restaurar un grupo Microsoft 365 eliminado</span><span class="sxs-lookup"><span data-stu-id="3c7f8-104">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="3c7f8-105">Si ha eliminado un grupo, se conservará durante 30 días de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-105">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="3c7f8-106">Este período de 30 días se considera una "eliminación suave" porque aún se puede restaurar el grupo.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-106">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="3c7f8-107">Después de 30 días, el grupo y su contenido asociado se eliminan permanentemente y no se pueden restaurar.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-107">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="3c7f8-108">Cuando se restaura un grupo, se restaura el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="3c7f8-108">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="3c7f8-109">Azure Active Directory (AD) Microsoft 365 de grupos, propiedades y miembros.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-109">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="3c7f8-110">Direcciones de correo electrónico del grupo.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-110">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="3c7f8-111">Exchange Online bandeja de entrada y el calendario compartidos.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-111">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="3c7f8-112">SharePoint Sitio de grupo en línea y archivos.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-112">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="3c7f8-113">Bloc de notas de OneNote</span><span class="sxs-lookup"><span data-stu-id="3c7f8-113">OneNote notebook</span></span>
    
- <span data-ttu-id="3c7f8-114">Planner</span><span class="sxs-lookup"><span data-stu-id="3c7f8-114">Planner</span></span>
    
- <span data-ttu-id="3c7f8-115">Teams</span><span class="sxs-lookup"><span data-stu-id="3c7f8-115">Teams</span></span>

- <span data-ttu-id="3c7f8-116">Yammer de grupo y grupo (si el grupo Microsoft 365 se creó a partir de Yammer)</span><span class="sxs-lookup"><span data-stu-id="3c7f8-116">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="3c7f8-117">En este artículo se describe la restauración de solo Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-117">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="3c7f8-118">El resto de grupos no se pueden restaurar una vez eliminados.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-118">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="3c7f8-119">Restaurar un grupo</span><span class="sxs-lookup"><span data-stu-id="3c7f8-119">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="3c7f8-120">Outlook</span><span class="sxs-lookup"><span data-stu-id="3c7f8-120">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="3c7f8-121">Si es el propietario de un grupo Microsoft 365, puede restaurarlo usted mismo en Outlook web siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3c7f8-121">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="3c7f8-122">En la [página Grupos eliminados,](https://outlook.office.com/people/group/deleted)seleccione la opción **Administrar grupos** en **el** nodo Grupos y, a continuación, **elija Eliminado**.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-122">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="3c7f8-123">Haga clic en **la pestaña** Restaurar junto al grupo que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-123">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="3c7f8-124">Si el grupo eliminado no aparece aquí, póngase en contacto con un administrador.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-124">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="3c7f8-125">Centro de administración</span><span class="sxs-lookup"><span data-stu-id="3c7f8-125">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="3c7f8-126">Si es un administrador global o un administrador de grupos, puede restaurar un grupo eliminado en el centro Microsoft 365 administración:</span><span class="sxs-lookup"><span data-stu-id="3c7f8-126">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="3c7f8-127">Vaya al [Centro de administración](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3c7f8-127">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="3c7f8-128">Expanda **Grupos** y, a continuación, haga clic **en Grupos eliminados.**</span><span class="sxs-lookup"><span data-stu-id="3c7f8-128">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="3c7f8-129">Seleccione el grupo que desea restaurar y, a continuación, haga clic en **Restaurar grupo**.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-129">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="3c7f8-130">En algunos casos, el grupo y todos sus datos pueden tardar hasta 24 horas en restaurarse.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-130">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="3c7f8-131">¿Tiene preguntas sobre Microsoft 365 grupos?</span><span class="sxs-lookup"><span data-stu-id="3c7f8-131">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="3c7f8-132">Visite microsoft [Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para publicar preguntas y participar en conversaciones sobre Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="3c7f8-132">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="3c7f8-133">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="3c7f8-133">Related content</span></span>

<span data-ttu-id="3c7f8-134">[Administrar Microsoft 365 con PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="3c7f8-134">[Manage Microsoft 365 Groups with PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (article)</span></span>\
<span data-ttu-id="3c7f8-135">[Eliminar grupos mediante el cmdlet Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) (artículo)</span><span class="sxs-lookup"><span data-stu-id="3c7f8-135">[Delete groups using the Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup) (article)</span></span>\
<span data-ttu-id="3c7f8-136">[Administrar la configuración del sitio de grupo conectado a un grupo](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (artículo)</span><span class="sxs-lookup"><span data-stu-id="3c7f8-136">[Manage your group-connected team site settings](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (article)</span></span>\
<span data-ttu-id="3c7f8-137">[Eliminar un grupo en Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (artículo)</span><span class="sxs-lookup"><span data-stu-id="3c7f8-137">[Delete a group in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (article)</span></span>