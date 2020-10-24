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
# <a name="restore-a-deleted-microsoft-365-group"></a>Restaurar un grupo de Microsoft 365 eliminado

Si ha eliminado un grupo, se conservará durante 30 días de forma predeterminada. Este período de 30 días se considera una "eliminación temporal" porque todavía puede restaurar el grupo. Transcurrido el plazo de 30 días, el grupo y su contenido asociado se eliminan de forma permanente y no se pueden restaurar.

Cuando se restaura un grupo, se restaura el siguiente contenido:
  
- Azure Active Directory (AD) Microsoft 365 Groups (objeto, propiedades y miembros).
    
- Direcciones de correo electrónico del grupo.
    
- Bandeja de entrada y calendario compartidos de Exchange Online.
    
- Sitio de grupo y archivos de SharePoint Online.
    
- Bloc de notas de OneNote
    
- Planner
    
- Teams

- Grupo de Yammer y contenido del grupo (si el grupo de Microsoft 365 se creó desde Yammer)

> [!NOTE]
> En este artículo se describe cómo restaurar sólo los grupos de Microsoft 365. Todos los demás grupos no se pueden restaurar una vez eliminados.

## <a name="restore-a-group"></a>Restaurar un grupo

# <a name="outlook"></a>[Outlook](#tab/outlook)

Si es el propietario de un grupo de Microsoft 365, puede restaurar el grupo personalmente en Outlook en la web siguiendo estos pasos:

1. En la [Página grupos eliminados](https://outlook.office.com/people/group/deleted), seleccione la opción **administrar grupos** en el nodo **grupos** y, a continuación, elija **eliminado**.

2. Haga clic en la pestaña **restaurar** situada junto al grupo que desea restaurar.

Si el grupo eliminado no aparece aquí, póngase en contacto con un administrador.

# <a name="admin-center"></a>[Centro de administración](#tab/admin-center)

Si es administrador global o administrador de grupos, puede restaurar un grupo eliminado en el centro de administración de Microsoft 365:

1. Vaya al [Centro de administración](https://admin.microsoft.com).
2. Expanda **grupos**y, a continuación, haga clic en **grupos eliminados**.
3. Seleccione el grupo que desea restaurar y, a continuación, haga clic en **restaurar grupo**.

> [!NOTE]
> En algunos casos, puede tardar hasta 24 horas en restaurar el grupo y todos sus datos. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>¿Tiene preguntas acerca de los grupos de Microsoft 365?

Visite [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para publicar preguntas y participar en conversaciones sobre grupos de 365 de Microsoft. 
  
## <a name="related-articles"></a>Artículos relacionados

[Administración de grupos de Microsoft 365 con PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[Eliminar grupos mediante el cmdlet Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Administrar la configuración de su sitio de grupo conectado](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Eliminar un grupo en Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
