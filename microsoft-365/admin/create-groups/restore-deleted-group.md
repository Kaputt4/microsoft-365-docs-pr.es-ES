---
title: Restauración de un grupo de Microsoft 365 eliminado
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Un grupo eliminado se conserva durante 30 días y todavía se puede restaurar el grupo. Después de 30 días, el grupo y su contenido se eliminan permanentemente.
ms.openlocfilehash: ea154fa9a1533fdabf4cc9b1a8a6c50cd62cacff
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68726736"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Restauración de un grupo de Microsoft 365 eliminado

Si ha eliminado un grupo, se conservará durante 30 días de forma predeterminada. Este período de 30 días se considera una "eliminación temporal" porque todavía puede restaurar el grupo. Después de 30 días, el grupo y su contenido asociado se eliminan permanentemente y no se pueden restaurar.

Cuando se restaura un grupo, se restaura el siguiente contenido:
  
- Azure Active Directory (AD) Grupos de Microsoft 365 objeto, propiedades y miembros.
    
- Direcciones de correo electrónico del grupo.
    
- Exchange Online bandeja de entrada y calendario compartidos.
    
- Archivos y sitios de equipo de SharePoint Online.
    
- Bloc de notas de OneNote
    
- Planner
    
- Teams

- Contenido de grupo y grupo de Yammer (si el grupo de Microsoft 365 se creó a partir de Yammer)

- Área de [trabajo de](/power-bi/collaborate-share/service-create-workspaces) Power BI clásico

> [!NOTE]
> En este artículo se describe cómo restaurar solo grupos de Microsoft 365. El resto de grupos no se pueden restaurar una vez eliminados.

## <a name="restore-a-group"></a>Restauración de un grupo

# <a name="outlook"></a>[Outlook](#tab/outlook)

Si es el propietario de un grupo de Microsoft 365, puede restaurarlo usted mismo en Outlook en la Web siguiendo estos pasos:

1. En la [página Grupos eliminados](https://outlook.office.com/people/group/deleted), seleccione la opción **Administrar grupos** en el nodo **Grupos** y, a continuación, elija **Eliminado**.

2. Haga clic en la pestaña **Restaurar** situada junto al grupo que desea restaurar.

Si el grupo eliminado no aparece aquí, póngase en contacto con un administrador.

# <a name="admin-center"></a>[centro de Administración](#tab/admin-center)

Si es administrador global o administrador de grupos, puede restaurar un grupo eliminado en el Centro de administración de Microsoft 365:

1. Vaya al [Centro de administración](https://admin.microsoft.com).
2. Expanda **Grupos** y, a continuación, haga clic en **Grupos eliminados**.
3. Seleccione el grupo que desea restaurar y, a continuación, haga clic en **Restaurar grupo**.

> [!NOTE]
> En algunos casos, el grupo y todos sus datos pueden tardar hasta 24 horas en restaurarse. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>¿Tienes preguntas sobre Grupos de Microsoft 365?

Visite el [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para publicar preguntas y participar en conversaciones sobre grupos de Microsoft 365. 
  
## <a name="related-content"></a>Contenido relacionado

[Administración de Grupos de Microsoft 365 con PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (artículo)\
[Eliminar grupos mediante el cmdlet Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) (artículo)\
[Administrar la configuración del sitio del equipo conectado al grupo](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (artículo)\
[Eliminar un grupo en Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (artículo)
