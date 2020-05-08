---
title: Restaurar un grupo eliminado
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Obtenga información sobre cómo restaurar un grupo de Microsoft 365 eliminado.
ms.openlocfilehash: 9d432d6ddb7e41b6560329b562c24f392a424412
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140529"
---
# <a name="restore-a-deleted-group"></a>Restaurar un grupo eliminado

::: moniker range="o365-21vianet"

> [!NOTE]
> El centro de administración está cambiando. Si su experiencia no coincide con los detalles que se presentan aquí, vea [acerca del nuevo centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

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

## <a name="restore-a-group-that-you-own-by-using-outlook"></a>Restaurar un grupo de su propiedad mediante Outlook

Si es el propietario de un grupo de Microsoft 365, puede restaurar el grupo personalmente en Outlook siguiendo estos pasos:

1. En la [Página grupos eliminados](https://outlook.office.com/people/group/deleted), seleccione la opción **administrar grupos** en el nodo **grupos** y, a continuación, elija **eliminado**.

2. Haga clic en la pestaña **restaurar** situada junto al grupo que desea restaurar.

Si el grupo eliminado no aparece aquí, póngase en contacto con un administrador.

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>Restaurar un grupo en el centro de administración de Microsoft 365

Si es administrador global o administrador de grupos, puede restaurar un grupo eliminado en el centro de administración de Microsoft 365:

1. Vaya al [centro de administración](https://admin.microsoft.com).
2. Expanda **grupos**y, a continuación, haga clic en **grupos eliminados**.
3. Seleccione el grupo que desea restaurar y, a continuación, haga clic en **restaurar grupo**.
  
## <a name="permanently-delete-a-microsoft-365-group"></a>Eliminar de forma permanente un grupo de 365 de Microsoft

A veces, es posible que desee purgar un grupo de forma permanente sin esperar a que expire el período de eliminación de software de 30 días. Para ello, inicie PowerShell y ejecute este comando para obtener el identificador de objeto del Grupo:
  
```
Get-AzureADMSDeletedGroup
```

Anote el identificador de objeto del grupo o grupos que desea eliminar de forma permanente.
  
> [!CAUTION]
> Purgar el grupo elimina el grupo y sus datos para siempre. 
  
Para purgar el grupo, ejecute este comando en PowerShell:
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

Para confirmar que el grupo se ha purgado correctamente, ejecute el cmdlet  *Get-AzureADMSDeletedGroup*  de nuevo para confirmar que el grupo ya no aparece en la lista de grupos eliminados temporalmente. En algunos casos, la eliminación permanente del grupo y todos sus datos puede tardar hasta 24 horas. 
  
## <a name="got-questions-about-microsoft-365-groups"></a>¿Tiene preguntas acerca de los grupos de Microsoft 365?

Visite [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para publicar preguntas y participar en conversaciones sobre grupos de 365 de Microsoft. 
  
## <a name="related-articles"></a>Artículos relacionados

[Administración de grupos de Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
[Eliminar grupos mediante el cmdlet Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Administrar la configuración de su sitio de grupo conectado](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[Eliminar un grupo en Outlook](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
