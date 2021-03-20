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
ms.openlocfilehash: f3b6435d82d5beddf44f5920011b076b39c7dcd5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910551"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Restaurar un grupo de Microsoft 365 eliminado

Si ha eliminado un grupo, se conservará durante 30 días de forma predeterminada. Este período de 30 días se considera una "eliminación suave" porque aún se puede restaurar el grupo. Después de 30 días, el grupo y su contenido asociado se eliminan permanentemente y no se pueden restaurar.

Cuando se restaura un grupo, se restaura el siguiente contenido:
  
- Objeto, propiedades y miembros de Microsoft 365 Groups de Azure Active Directory (AD).
    
- Direcciones de correo electrónico del grupo.
    
- Exchange Online shared Inbox and calendar.
    
- Sitio de grupo y archivos de SharePoint Online.
    
- Bloc de notas de OneNote
    
- Planner
    
- Teams

- Contenido de grupo y grupo de Yammer (si el grupo de Microsoft 365 se creó a partir de Yammer)

> [!NOTE]
> En este artículo se describe la restauración de solo grupos de Microsoft 365. El resto de grupos no se pueden restaurar una vez eliminados.

## <a name="restore-a-group"></a>Restaurar un grupo

# <a name="outlook"></a>[Outlook](#tab/outlook)

Si es el propietario de un grupo de Microsoft 365, puede restaurar el grupo usted mismo en Outlook en la web siguiendo estos pasos:

1. En la [página Grupos eliminados,](https://outlook.office.com/people/group/deleted)seleccione la opción **Administrar grupos** en **el** nodo Grupos y, a continuación, **elija Eliminado**.

2. Haga clic en **la pestaña** Restaurar junto al grupo que desea restaurar.

Si el grupo eliminado no aparece aquí, póngase en contacto con un administrador.

# <a name="admin-center"></a>[Centro de administración](#tab/admin-center)

Si es un administrador global o un administrador de grupos, puede restaurar un grupo eliminado en el Centro de administración de Microsoft 365:

1. Vaya al [Centro de administración](https://admin.microsoft.com).
2. Expanda **Grupos** y, a continuación, haga clic **en Grupos eliminados.**
3. Seleccione el grupo que desea restaurar y, a continuación, haga clic en **Restaurar grupo**.

> [!NOTE]
> En algunos casos, el grupo y todos sus datos pueden tardar hasta 24 horas en restaurarse. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>¿Tiene preguntas sobre Grupos de Microsoft 365?

Visite la [Comunidad tecnológica de Microsoft](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para publicar preguntas y participar en conversaciones sobre grupos de Microsoft 365. 
  
## <a name="related-articles"></a>Artículos relacionados

[Administrar grupos de Microsoft 365 con PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
  
[Eliminar grupos mediante el cmdlet Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup)
  
[Administrar la configuración de su sitio de grupo conectado](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Eliminar un grupo en Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)