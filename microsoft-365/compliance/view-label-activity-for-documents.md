---
title: Ver la actividad de etiquetas de documentos
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 5/9/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Obtenga información acerca de cómo usar el Explorador de actividad de etiquetas en el Centro de seguridad y cumplimiento de Microsoft 365 para buscar actividades de etiquetas y visualizarlas.
ms.openlocfilehash: 9cf505575a17c8f6eb4d48e609d358f9c988965f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819030"
---
# <a name="view-label-activity-for-documents"></a><span data-ttu-id="c2ac4-103">Ver la actividad de etiquetas de documentos</span><span class="sxs-lookup"><span data-stu-id="c2ac4-103">View label activity for documents</span></span>

<span data-ttu-id="c2ac4-104">After you create your labels, you'll want to verify that they're being applied to content as you intended.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-104">After you create your labels, you'll want to verify that they're being applied to content as you intended.</span></span> <span data-ttu-id="c2ac4-105">With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-105">With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days.</span></span> <span data-ttu-id="c2ac4-106">This is real-time data that gives you a clear view into what's happening in your tenant.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-106">This is real-time data that gives you a clear view into what's happening in your tenant.</span></span>
  
<span data-ttu-id="c2ac4-107">Por ejemplo, con el Explorador de actividad de etiquetas, puede:</span><span class="sxs-lookup"><span data-stu-id="c2ac4-107">For example, with the Label Activity Explorer, you can:</span></span>
  
- <span data-ttu-id="c2ac4-108">Ver el número de veces que cada etiqueta se aplicó cada día (hasta 30 días).</span><span class="sxs-lookup"><span data-stu-id="c2ac4-108">View how many times each label was applied on each day (up to 30 days).</span></span>
    
- <span data-ttu-id="c2ac4-109">Ver quién etiquetó exactamente cada archivo y en qué fecha, además de un vínculo al sitio donde se encuentra el archivo.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-109">See who labeled exactly which file on which date, along with a link to the site where that file resides.</span></span>
    
- <span data-ttu-id="c2ac4-110">Ver los archivos donde se cambiaron o quitaron etiquetas, cuáles son las etiquetas nuevas y anteriores, y quién realizó el cambio.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-110">View which files had labels changed or removed, what the old and new labels are, and who made the change.</span></span>
    
- <span data-ttu-id="c2ac4-111">Filter the data to see all the label activity for a specific label, file, or user.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-111">Filter the data to see all the label activity for a specific label, file, or user.</span></span> <span data-ttu-id="c2ac4-112">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-112">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
    
- <span data-ttu-id="c2ac4-113">View label activity for folders as well as individual documents.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-113">View label activity for folders as well as individual documents.</span></span> <span data-ttu-id="c2ac4-114">Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-114">Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span></span>
    
<span data-ttu-id="c2ac4-115">Encontrará el Explorador de actividad de etiquetas en el &amp;Centro de seguridad y cumplimiento > **Gobierno de información** > **Explorador de actividad de etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-115">You can find the Label Activity Explorer in the Security &amp; Compliance Center > **Information governance** > **Label activity explorer**.</span></span>
  
<span data-ttu-id="c2ac4-116">Tenga en cuenta que, para usar el Explorador de actividad de etiquetas, se necesita una suscripción de Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-116">Note that the Label Activity Explorer requires an Office 365 Enterprise E5 subscription.</span></span>
  
![Explorador de actividad de etiquetas](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a><span data-ttu-id="c2ac4-118">Ver actividades de etiquetas de archivos o carpetas</span><span class="sxs-lookup"><span data-stu-id="c2ac4-118">View label activities for files or folders</span></span>

<span data-ttu-id="c2ac4-119">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-119">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders.</span></span> <span data-ttu-id="c2ac4-120">Note that folder activity includes only the folder itself, not the files inside the folder.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-120">Note that folder activity includes only the folder itself, not the files inside the folder.</span></span>
  
<span data-ttu-id="c2ac4-121">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them).</span><span class="sxs-lookup"><span data-stu-id="c2ac4-121">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them).</span></span> <span data-ttu-id="c2ac4-122">Therefore, labeling folders might affect a significant number of files.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-122">Therefore, labeling folders might affect a significant number of files.</span></span> <span data-ttu-id="c2ac4-123">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="c2ac4-123">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
  
![Menú desplegable donde se muestran actividades de etiquetas de archivos y carpetas](../media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a><span data-ttu-id="c2ac4-125">Actividades de etiquetas</span><span class="sxs-lookup"><span data-stu-id="c2ac4-125">Label activities</span></span>

 <span data-ttu-id="c2ac4-126">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-126">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label.</span></span> <span data-ttu-id="c2ac4-127">You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-127">You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span></span> 
  
### <a name="label-changes"></a><span data-ttu-id="c2ac4-128">Cambios de etiquetas</span><span class="sxs-lookup"><span data-stu-id="c2ac4-128">Label changes</span></span>

 <span data-ttu-id="c2ac4-129">**Label changes** includes the potentially risky actions of **removing** or **changing** a label.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-129">**Label changes** includes the potentially risky actions of **removing** or **changing** a label.</span></span> <span data-ttu-id="c2ac4-130">You can use this view to quickly see such risky actions and the user who performed them.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-130">You can use this view to quickly see such risky actions and the user who performed them.</span></span> <span data-ttu-id="c2ac4-131">In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-131">In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span></span> 
  
![Panel de detalles para actividad de etiquetas](../media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a><span data-ttu-id="c2ac4-133">Filtrar actividad de etiquetas</span><span class="sxs-lookup"><span data-stu-id="c2ac4-133">Filter label activity</span></span>

<span data-ttu-id="c2ac4-134">You can quickly filter the data to see all the label activity for a specific label, file, or user.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-134">You can quickly filter the data to see all the label activity for a specific label, file, or user.</span></span> <span data-ttu-id="c2ac4-135">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span><span class="sxs-lookup"><span data-stu-id="c2ac4-135">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
  
![Filtros para actividad de etiquetas](../media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  

