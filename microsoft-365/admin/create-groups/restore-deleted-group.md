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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Un grupo eliminado se conserva durante 30 días y aún puede restaurar el grupo. Después de 30 días, el grupo y su contenido se eliminan permanentemente.
ms.openlocfilehash: fb703240ebec219c0a1d15791782ea72be88a3a4
ms.sourcegitcommit: 88c3b9758214936d283bad0321b826fb40a2e7e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2021
ms.locfileid: "60087778"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Restaurar un grupo Microsoft 365 eliminado

Si ha eliminado un grupo, se conservará durante 30 días de forma predeterminada. Este período de 30 días se considera una "eliminación suave" porque aún se puede restaurar el grupo. Después de 30 días, el grupo y su contenido asociado se eliminan permanentemente y no se pueden restaurar.

Cuando se restaura un grupo, se restaura el siguiente contenido:
  
- Azure Active Directory (AD) Microsoft 365 de grupos, propiedades y miembros.
    
- Direcciones de correo electrónico del grupo.
    
- Exchange Online bandeja de entrada y el calendario compartidos.
    
- SharePoint Sitio de grupo en línea y archivos.
    
- Bloc de notas de OneNote
    
- Planner
    
- Teams

- Yammer de grupo y grupo (si el grupo Microsoft 365 se creó a partir de Yammer)

- Power BI área [de trabajo clásica](/power-bi/collaborate-share/service-create-workspaces)

> [!NOTE]
> En este artículo se describe la restauración de solo Microsoft 365 grupos. El resto de grupos no se pueden restaurar una vez eliminados.

## <a name="restore-a-group"></a>Restaurar un grupo

# <a name="outlook"></a>[Outlook](#tab/outlook)

Si es el propietario de un grupo Microsoft 365, puede restaurarlo usted mismo en Outlook en la Web siga estos pasos:

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

## <a name="got-questions-about-microsoft-365-groups"></a>¿Tiene preguntas sobre Microsoft 365 grupos?

Visite microsoft [Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para publicar preguntas y participar en conversaciones sobre Microsoft 365 grupos. 
  
## <a name="related-content"></a>Contenido relacionado

[Administrar Microsoft 365 con PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (artículo)\
[Eliminar grupos mediante el cmdlet Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) (artículo)\
[Administrar la configuración del sitio de grupo conectado a un grupo](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (artículo)\
[Eliminar un grupo en Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (artículo)
