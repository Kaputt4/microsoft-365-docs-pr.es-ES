---
title: Activar o desactivar la búsqueda de registros de auditoría de Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: Puede activar la característica de búsqueda de registros de auditoría en el centro de seguridad & cumplimiento. Si cambia de opinión, puede desactivar la opción en cualquier momento. Cuando la búsqueda de registros de auditoría está desactivada, los administradores no pueden buscar en el registro de auditoría de Office 365 la actividad de usuario y de administrador de su organización.
ms.openlocfilehash: 92a781ddb1fd4f5b41198f31ebff6bba9745d21d
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240219"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a>Activar o desactivar la búsqueda de registros de auditoría de Office 365

Usted (u otro administrador) deben activar el registro de auditoría para poder empezar a buscar en el registro de auditoría de Office 365. Cuando se activa la búsqueda de registros de auditoría en el centro de seguridad & cumplimiento, la actividad de usuario y administrador de la organización se registra en el registro de auditoría y se conserva durante 90 días, y hasta un año según la licencia asignada a los usuarios. Sin embargo, es posible que su organización tenga motivos para no querer registrar y conservar los datos del registro de auditoría. En esos casos, un administrador global puede decidir desactivar la auditoría en Office 365.

> [!IMPORTANT]
> Si desactiva la búsqueda de registros de auditoría en Office 365, no podrá usar la API de actividad de administración de Office 365 o Azure Sentinel para acceder a los datos de auditoría de su organización. La desactivación de la búsqueda de registros de auditoría siguiendo los pasos descritos en este artículo significa que no se devolverán resultados cuando busque en el registro de auditoría mediante el centro de seguridad & cumplimiento o cuando ejecute el cmdlet **Search-UnifiedAuditLog** en Exchange Online PowerShell. Esto también significa que los registros de auditoría no estarán disponibles a través de la API de actividad de administración de Office 365 o de Azure Sentinel.
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe tener asignado el rol registros de auditoría en Exchange Online para activar o desactivar la búsqueda de registros de auditoría en su organización de Office 365. De forma predeterminada, este rol se asigna a los grupos de roles administración de cumplimiento y administración de la organización en la página **permisos** del centro de administración de Exchange. Los administradores globales de Office 365 son miembros del grupo de funciones de administración de la organización en Exchange Online. 
    
    > [!NOTE]
    > Los usuarios deben tener asignados permisos en Exchange Online para activar o desactivar la búsqueda de registros de auditoría. Si asigna a los usuarios el rol registros de auditoría en la página **permisos** del centro de seguridad & cumplimiento, no podrán activar o desactivar la búsqueda de registros de auditoría. Esto se debe a que el cmdlet subyacente es un cmdlet de Exchange Online. 
    
- Para obtener instrucciones paso a paso sobre cómo buscar en el registro de auditoría de Office 365, vea [Buscar el registro de auditoría en el centro de seguridad & cumplimiento](search-the-audit-log-in-security-and-compliance.md). Para obtener más información sobre la API de actividad de administración 365 de Office, vea Introducción [a las API de administración de office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).
    
## <a name="turn-on-audit-log-search"></a>Activar la búsqueda de registros de auditoría

Puede usar el centro de seguridad & cumplimiento o PowerShell para activar la búsqueda de registros de auditoría en Office 365. Puede tardar varias horas después de activar la búsqueda de registros de auditoría para poder devolver los resultados cuando busque en el registro de auditoría. Debe tener asignado el rol registros de auditoría en Exchange Online para activar la búsqueda de registros de auditoría.
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a>Usar el centro de seguridad & cumplimiento para activar la búsqueda de registros de auditoría

1. En el centro de seguridad & cumplimiento, vaya a búsqueda de **registros de auditoría**de **búsqueda** \> .
    
   Se muestra un banner en el que se indica que se debe activar la auditoría para registrar la actividad de usuario y de administrador.

2. Haga clic en **Activar auditoría**.
    
    ![Haga clic en activar auditoría](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    El banner se actualiza para indicar que se está preparando el registro de auditoría y que puede buscar la actividad de usuario y de administrador en unas horas.
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a>Usar PowerShell para activar la búsqueda de registros de auditoría

1. [Conectarse a Exchange Online mediante PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Ejecute el siguiente comando de PowerShell para activar la búsqueda de registros de auditoría en Office 365.
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Se muestra un mensaje que indica que puede tardar hasta 60 minutos para que el cambio surta efecto.
  
## <a name="turn-off-audit-log-search"></a>Desactivar la búsqueda de registros de auditoría

Debe usar PowerShell remoto conectado a su organización de Exchange Online para desactivar la búsqueda de registros de auditoría. De forma similar a activar la búsqueda de registros de auditoría, debe tener asignado el rol registros de auditoría en Exchange Online para desactivar la búsqueda de registros de auditoría.
  
1. [Conectarse a Exchange Online mediante PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Ejecute el siguiente comando de PowerShell para desactivar la búsqueda de registros de auditoría en Office 365.
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Después de un rato, compruebe que la búsqueda de registros de auditoría está desactivada (deshabilitada). Puede realizar esto de dos maneras:
    
    - En PowerShell, ejecute el siguiente comando:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      El valor de `False` para la propiedad _UnifiedAuditLogIngestionEnabled_ indica que la búsqueda de registros de auditoría está desactivada. 
    
    - En el centro de seguridad & cumplimiento, vaya a búsqueda de **registros de auditoría**de **búsqueda** \> .
    
      Se muestra un banner en el que se indica que se debe activar la auditoría para poder registrar la actividad de usuario y de administrador.
