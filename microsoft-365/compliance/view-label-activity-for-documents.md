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
ms.openlocfilehash: e21bb867044b2a6644b125aad9983ce3518f70ee
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053352"
---
# <a name="view-label-activity-for-documents"></a><span data-ttu-id="94868-103">Ver la actividad de etiquetas de documentos</span><span class="sxs-lookup"><span data-stu-id="94868-103">View label activity for documents</span></span>

<span data-ttu-id="94868-p101">Después de crear las etiquetas, puede verificar que se aplicaron en el contenido según lo previsto. Con el Explorador de actividad de etiquetas en el Centro de seguridad y cumplimiento de &amp;, puede buscar y visualizar rápidamente actividades de etiquetas de todo el contenido en SharePoint OneDrive para la Empresa en los últimos 30 días. Estos son datos en tiempo real que le ofrecen una vista clara de lo que ocurre en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="94868-p101">After you create your labels, you'll want to verify that they're being applied to content as you intended. With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days. This is real-time data that gives you a clear view into what's happening in your tenant.</span></span>
  
<span data-ttu-id="94868-107">Por ejemplo, con el Explorador de actividad de etiquetas, puede:</span><span class="sxs-lookup"><span data-stu-id="94868-107">For example, with the Label Activity Explorer, you can:</span></span>
  
- <span data-ttu-id="94868-108">Ver el número de veces que cada etiqueta se aplicó cada día (hasta 30 días).</span><span class="sxs-lookup"><span data-stu-id="94868-108">View how many times each label was applied on each day (up to 30 days).</span></span>
    
- <span data-ttu-id="94868-109">Ver quién etiquetó exactamente cada archivo y en qué fecha, además de un vínculo al sitio donde se encuentra el archivo.</span><span class="sxs-lookup"><span data-stu-id="94868-109">See who labeled exactly which file on which date, along with a link to the site where that file resides.</span></span>
    
- <span data-ttu-id="94868-110">Ver los archivos donde se cambiaron o quitaron etiquetas, cuáles son las etiquetas nuevas y anteriores, y quién realizó el cambio.</span><span class="sxs-lookup"><span data-stu-id="94868-110">View which files had labels changed or removed, what the old and new labels are, and who made the change.</span></span>
    
- <span data-ttu-id="94868-p102">Filtre los datos para ver toda la actividad de etiquetas de una etiqueta, archivo o usuario específicos. También puede filtrar la actividad de etiquetas por ubicación (SharePoint o OneDrive para la Empresa), así como filtrar dependiendo de si la etiqueta se aplicó automáticamente o de forma manual.</span><span class="sxs-lookup"><span data-stu-id="94868-p102">Filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
    
- <span data-ttu-id="94868-p103">Vea la actividad de etiquetas de carpetas, así como de documentos individuales. Próximamente, podrá mostrarse el número de archivos de la carpeta que se etiquetaron como resultado de etiquetar la carpeta.</span><span class="sxs-lookup"><span data-stu-id="94868-p103">View label activity for folders as well as individual documents. Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span></span>
    
<span data-ttu-id="94868-115">Encontrará el Explorador de actividad de etiquetas en el &amp;Centro de seguridad y cumplimiento > **Gobierno de información** > **Explorador de actividad de etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="94868-115">You can find the Label Activity Explorer in the Security &amp; Compliance Center > **Information governance** > **Label activity explorer**.</span></span>
  
<span data-ttu-id="94868-116">Tenga en cuenta que, para usar el Explorador de actividad de etiquetas, se necesita una suscripción de Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="94868-116">Note that the Label Activity Explorer requires an Office 365 Enterprise E5 subscription.</span></span>
  
![Explorador de actividad de etiquetas](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a><span data-ttu-id="94868-118">Ver actividades de etiquetas de archivos o carpetas</span><span class="sxs-lookup"><span data-stu-id="94868-118">View label activities for files or folders</span></span>

<span data-ttu-id="94868-p104">En la parte superior del Explorador de actividad de etiquetas, puede ver las actividades de archivos o carpetas. Tenga en cuenta que en la actividad de carpeta solo se incluye la carpeta en sí, no se incluyen los archivos dentro de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="94868-p104">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders. Note that folder activity includes only the folder itself, not the files inside the folder.</span></span>
  
<span data-ttu-id="94868-p105">Puede que quiera ver la actividad de etiquetas de las carpetas porque, si etiqueta una carpeta, todos los archivos dentro de esa carpeta también se etiquetarán (excepto los archivos donde se aplicó una etiqueta de forma explícita). Por lo tanto, etiquetar carpetas podría afectar a un número elevado de archivos. Para obtener más información, vea [Aplicar una etiqueta de retención predeterminada a todo el contenido de una biblioteca, carpeta o conjunto de documentos de SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="94868-p105">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them). Therefore, labeling folders might affect a significant number of files. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
  
![Menú desplegable donde se muestran actividades de etiquetas de archivos y carpetas](../media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a><span data-ttu-id="94868-125">Actividades de etiquetas</span><span class="sxs-lookup"><span data-stu-id="94868-125">Label activities</span></span>

 <span data-ttu-id="94868-p106">En **Actividades de etiquetas**, se incluyen todas las acciones de etiquetado: **agregar**, **quitar** o **cambiar** una etiqueta. Puede usar esta vista para obtener información completa sobre el número de archivos en los que se aplicó cada etiqueta por día.</span><span class="sxs-lookup"><span data-stu-id="94868-p106">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label. You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span></span> 
  
### <a name="label-changes"></a><span data-ttu-id="94868-128">Cambios de etiquetas</span><span class="sxs-lookup"><span data-stu-id="94868-128">Label changes</span></span>

 <span data-ttu-id="94868-p107">En **Cambios de etiquetas**, se incluyen las acciones que pueden ser arriesgadas, como **quitar** o **cambiar** una etiqueta. Puede usar esta vista para ver rápidamente esas acciones arriesgadas y el usuario que las realizó. En la lista de actividades debajo del gráfico, puede seleccionar un archivo y, después, en el panel de detalles de la parte derecha, hacer clic en un vínculo a ese archivo.</span><span class="sxs-lookup"><span data-stu-id="94868-p107">**Label changes** includes the potentially risky actions of **removing** or **changing** a label. You can use this view to quickly see such risky actions and the user who performed them. In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span></span> 
  
![Panel de detalles para actividad de etiquetas](../media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a><span data-ttu-id="94868-133">Filtrar actividad de etiquetas</span><span class="sxs-lookup"><span data-stu-id="94868-133">Filter label activity</span></span>

<span data-ttu-id="94868-p108">Puede filtrar rápidamente los datos para ver toda la actividad de etiquetas de una etiqueta, archivo o usuario específicos. También puede filtrar la actividad de etiquetas por ubicación (SharePoint o OneDrive para la Empresa), así como filtrar dependiendo de si la etiqueta se aplicó automáticamente o de forma manual.</span><span class="sxs-lookup"><span data-stu-id="94868-p108">You can quickly filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
  
![Filtros para actividad de etiquetas](../media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  

