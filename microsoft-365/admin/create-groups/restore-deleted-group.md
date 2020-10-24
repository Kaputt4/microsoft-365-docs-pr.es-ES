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
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="f320a-103">Restaurar un grupo de Microsoft 365 eliminado</span><span class="sxs-lookup"><span data-stu-id="f320a-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="f320a-104">Si ha eliminado un grupo, se conservará durante 30 días de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f320a-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="f320a-105">Este período de 30 días se considera una "eliminación temporal" porque todavía puede restaurar el grupo.</span><span class="sxs-lookup"><span data-stu-id="f320a-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="f320a-106">Transcurrido el plazo de 30 días, el grupo y su contenido asociado se eliminan de forma permanente y no se pueden restaurar.</span><span class="sxs-lookup"><span data-stu-id="f320a-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="f320a-107">Cuando se restaura un grupo, se restaura el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="f320a-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="f320a-108">Azure Active Directory (AD) Microsoft 365 Groups (objeto, propiedades y miembros).</span><span class="sxs-lookup"><span data-stu-id="f320a-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="f320a-109">Direcciones de correo electrónico del grupo.</span><span class="sxs-lookup"><span data-stu-id="f320a-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="f320a-110">Bandeja de entrada y calendario compartidos de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f320a-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="f320a-111">Sitio de grupo y archivos de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f320a-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="f320a-112">Bloc de notas de OneNote</span><span class="sxs-lookup"><span data-stu-id="f320a-112">OneNote notebook</span></span>
    
- <span data-ttu-id="f320a-113">Planner</span><span class="sxs-lookup"><span data-stu-id="f320a-113">Planner</span></span>
    
- <span data-ttu-id="f320a-114">Teams</span><span class="sxs-lookup"><span data-stu-id="f320a-114">Teams</span></span>

- <span data-ttu-id="f320a-115">Grupo de Yammer y contenido del grupo (si el grupo de Microsoft 365 se creó desde Yammer)</span><span class="sxs-lookup"><span data-stu-id="f320a-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="f320a-116">En este artículo se describe cómo restaurar sólo los grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f320a-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="f320a-117">Todos los demás grupos no se pueden restaurar una vez eliminados.</span><span class="sxs-lookup"><span data-stu-id="f320a-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="f320a-118">Restaurar un grupo</span><span class="sxs-lookup"><span data-stu-id="f320a-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="f320a-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="f320a-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="f320a-120">Si es el propietario de un grupo de Microsoft 365, puede restaurar el grupo personalmente en Outlook en la web siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f320a-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="f320a-121">En la [Página grupos eliminados](https://outlook.office.com/people/group/deleted), seleccione la opción **administrar grupos** en el nodo **grupos** y, a continuación, elija **eliminado**.</span><span class="sxs-lookup"><span data-stu-id="f320a-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="f320a-122">Haga clic en la pestaña **restaurar** situada junto al grupo que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="f320a-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="f320a-123">Si el grupo eliminado no aparece aquí, póngase en contacto con un administrador.</span><span class="sxs-lookup"><span data-stu-id="f320a-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="f320a-124">Centro de administración</span><span class="sxs-lookup"><span data-stu-id="f320a-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="f320a-125">Si es administrador global o administrador de grupos, puede restaurar un grupo eliminado en el centro de administración de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="f320a-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="f320a-126">Vaya al [Centro de administración](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f320a-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="f320a-127">Expanda **grupos**y, a continuación, haga clic en **grupos eliminados**.</span><span class="sxs-lookup"><span data-stu-id="f320a-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="f320a-128">Seleccione el grupo que desea restaurar y, a continuación, haga clic en **restaurar grupo**.</span><span class="sxs-lookup"><span data-stu-id="f320a-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="f320a-129">En algunos casos, puede tardar hasta 24 horas en restaurar el grupo y todos sus datos.</span><span class="sxs-lookup"><span data-stu-id="f320a-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="f320a-130">¿Tiene preguntas acerca de los grupos de Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="f320a-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="f320a-131">Visite [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para publicar preguntas y participar en conversaciones sobre grupos de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f320a-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="f320a-132">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="f320a-132">Related articles</span></span>

[<span data-ttu-id="f320a-133">Administración de grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f320a-133">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="f320a-134">Eliminar grupos mediante el cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="f320a-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="f320a-135">Administrar la configuración de su sitio de grupo conectado</span><span class="sxs-lookup"><span data-stu-id="f320a-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="f320a-136">Eliminar un grupo en Outlook</span><span class="sxs-lookup"><span data-stu-id="f320a-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
