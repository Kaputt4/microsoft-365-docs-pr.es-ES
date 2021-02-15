---
title: Restaurar un grupo de Microsoft 365 eliminado
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
description: Obtenga información sobre cómo restaurar un grupo de Microsoft 365 eliminado.
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753248"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="bad70-103">Restaurar un grupo de Microsoft 365 eliminado</span><span class="sxs-lookup"><span data-stu-id="bad70-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="bad70-104">Si ha eliminado un grupo, se conservará durante 30 días de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bad70-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="bad70-105">Este período de 30 días se considera una "eliminación de forma flexible" porque aún se puede restaurar el grupo.</span><span class="sxs-lookup"><span data-stu-id="bad70-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="bad70-106">Después de 30 días, el grupo y su contenido asociado se eliminan permanentemente y no se pueden restaurar.</span><span class="sxs-lookup"><span data-stu-id="bad70-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="bad70-107">Cuando se restaura un grupo, se restaura el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="bad70-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="bad70-108">Objeto, propiedades y miembros de Grupos de Microsoft 365 de Azure Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="bad70-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="bad70-109">Direcciones de correo electrónico del grupo.</span><span class="sxs-lookup"><span data-stu-id="bad70-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="bad70-110">Bandeja de entrada y calendario compartidos de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bad70-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="bad70-111">Sitio de grupo y archivos de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bad70-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="bad70-112">Bloc de notas de OneNote</span><span class="sxs-lookup"><span data-stu-id="bad70-112">OneNote notebook</span></span>
    
- <span data-ttu-id="bad70-113">Planner</span><span class="sxs-lookup"><span data-stu-id="bad70-113">Planner</span></span>
    
- <span data-ttu-id="bad70-114">Teams</span><span class="sxs-lookup"><span data-stu-id="bad70-114">Teams</span></span>

- <span data-ttu-id="bad70-115">Contenido de grupo y grupo de Yammer (si el grupo de Microsoft 365 se creó a partir de Yammer)</span><span class="sxs-lookup"><span data-stu-id="bad70-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="bad70-116">En este artículo se describe la restauración solo de grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bad70-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="bad70-117">Los demás grupos no se pueden restaurar una vez eliminados.</span><span class="sxs-lookup"><span data-stu-id="bad70-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="bad70-118">Restaurar un grupo</span><span class="sxs-lookup"><span data-stu-id="bad70-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="bad70-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="bad70-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="bad70-120">Si es el propietario de un grupo de Microsoft 365, puede restaurar el grupo usted mismo en Outlook en la Web siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bad70-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="bad70-121">En la [página Grupos eliminados,](https://outlook.office.com/people/group/deleted)seleccione **la** opción Administrar grupos en **el** nodo Grupos y, a continuación, elija **Eliminado**.</span><span class="sxs-lookup"><span data-stu-id="bad70-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="bad70-122">Haga clic en **la pestaña** Restaurar junto al grupo que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="bad70-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="bad70-123">Si el grupo eliminado no aparece aquí, póngase en contacto con un administrador.</span><span class="sxs-lookup"><span data-stu-id="bad70-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="bad70-124">Centro de administración</span><span class="sxs-lookup"><span data-stu-id="bad70-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="bad70-125">Si es un administrador global o un administrador de grupos, puede restaurar un grupo eliminado en el Centro de administración de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="bad70-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="bad70-126">Vaya al [Centro de administración](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="bad70-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="bad70-127">Expanda **Grupos y,** a continuación, haga clic **en Grupos eliminados.**</span><span class="sxs-lookup"><span data-stu-id="bad70-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="bad70-128">Seleccione el grupo que desea restaurar y, a continuación, haga clic en **Restaurar grupo.**</span><span class="sxs-lookup"><span data-stu-id="bad70-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="bad70-129">En algunos casos, el grupo y todos sus datos pueden tardar hasta 24 horas en restaurarse.</span><span class="sxs-lookup"><span data-stu-id="bad70-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="bad70-130">¿Tiene preguntas sobre Grupos de Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="bad70-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="bad70-131">Visite microsoft [Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para publicar preguntas y participar en conversaciones sobre grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bad70-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="bad70-132">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="bad70-132">Related articles</span></span>

[<span data-ttu-id="bad70-133">Administrar grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="bad70-133">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="bad70-134">Eliminar grupos mediante el cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="bad70-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="bad70-135">Administrar la configuración de su sitio de grupo conectado</span><span class="sxs-lookup"><span data-stu-id="bad70-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="bad70-136">Eliminar un grupo en Outlook</span><span class="sxs-lookup"><span data-stu-id="bad70-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
