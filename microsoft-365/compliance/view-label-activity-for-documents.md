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
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127277"
---
# <a name="view-label-activity-for-documents"></a>Ver la actividad de etiquetas de documentos

After you create your labels, you'll want to verify that they're being applied to content as you intended. With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days. This is real-time data that gives you a clear view into what's happening in your tenant.
  
Por ejemplo, con el Explorador de actividad de etiquetas, puede:
  
- Ver el número de veces que cada etiqueta se aplicó cada día (hasta 30 días).
    
- Ver quién etiquetó exactamente cada archivo y en qué fecha, además de un vínculo al sitio donde se encuentra el archivo.
    
- Ver los archivos donde se cambiaron o quitaron etiquetas, cuáles son las etiquetas nuevas y anteriores, y quién realizó el cambio.
    
- Filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.
    
- View label activity for folders as well as individual documents. Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.
    
Encontrará el Explorador de actividad de etiquetas en el &amp;Centro de seguridad y cumplimiento > **Gobierno de información** > **Explorador de actividad de etiquetas**.
  
Tenga en cuenta que, para usar el Explorador de actividad de etiquetas, se necesita una suscripción de Office 365 Enterprise E5.
  
![Explorador de actividad de etiquetas](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a>Ver actividades de etiquetas de archivos o carpetas

At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders. Note that folder activity includes only the folder itself, not the files inside the folder.
  
You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them). Therefore, labeling folders might affect a significant number of files. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
  
![Menú desplegable donde se muestran actividades de etiquetas de archivos y carpetas](../media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a>Actividades de etiquetas

 **Label activities** includes all label actions: **adding**, **removing**, or **changing** a label. You can use this view to get a comprehensive look at how many files each label's been applied to per day. 
  
### <a name="label-changes"></a>Cambios de etiquetas

 **Label changes** includes the potentially risky actions of **removing** or **changing** a label. You can use this view to quickly see such risky actions and the user who performed them. In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right. 
  
![Panel de detalles para actividad de etiquetas](../media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a>Filtrar actividad de etiquetas

You can quickly filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.
  
![Filtros para actividad de etiquetas](../media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  

