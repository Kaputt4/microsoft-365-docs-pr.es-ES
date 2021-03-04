---
title: Activar o desactivar la búsqueda de registros de auditoría
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
ms.custom: seo-marvel-apr2020
description: Cómo activar o desactivar la característica de búsqueda de registro de auditoría en el Centro de seguridad y cumplimiento de & para habilitar o deshabilitar la capacidad de los administradores de buscar en el registro de auditoría.
ms.openlocfilehash: 3f3e1b913dd163e74f9e5359de772dfcbf3bd786
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423681"
---
# <a name="turn-audit-log-search-on-or-off"></a>Activar o desactivar la búsqueda de registros de auditoría

El registro de auditoría está activado de forma predeterminada para organizaciones de Microsoft 365 y Office 365 Enterprise. Esto incluye las organizaciones con suscripciones a E3/G3 o E5/G5. Cuando la búsqueda del registro de auditoría en el centro de cumplimiento está activada, la actividad de usuario y administrador de su organización se registra en el registro de auditoría y se retiene durante 90 días y hasta un año, según la licencia asignada a los usuarios. Sin embargo, es posible que la organización tenga motivos para no querer registrar y conservar los datos del registro de auditoría. En esos casos, un administrador global puede decidir desactivar la auditoría en Microsoft 365.

> [!IMPORTANT]
> Si desactiva la búsqueda de registro de auditoría en Microsoft 365, no puede usar la API de actividad de administración de Office 365 o Azure Sentinel para obtener acceso a los datos de auditoría de su organización. Desactivar la búsqueda de registro de auditoría siguiendo los pasos descritos en este artículo significa que no se devolverá ningún resultado cuando busque en el registro de auditoría mediante el Centro de seguridad & cumplimiento o cuando ejecute el cmdlet **Search-UnifiedAuditLog** en Exchange Online PowerShell. Esto también significa que los registros de auditoría no estarán disponibles a través de la API de actividad de administración de Office 365 o Azure Sentinel.
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>Antes de activar o desactivar la búsqueda del registro de auditoría

- Debe tener asignado el rol Registros de auditoría en Exchange Online para activar o desactivar la búsqueda del registro de auditoría en su organización de Microsoft 365. De forma predeterminada, este rol se asigna a los  grupos de roles Administración de cumplimiento y Administración de la organización en la página Permisos del Centro de administración de Exchange. Los administradores globales de Microsoft 365 son miembros del grupo de roles Administración de la organización en Exchange Online. 
    
    > [!NOTE]
    > Los usuarios deben tener asignados permisos en Exchange Online para activar o desactivar la búsqueda del registro de auditoría. Si asigna a los usuarios  el rol Registros de auditoría en la página Permisos del Centro de seguridad y cumplimiento de &, no podrán activar o desactivar la búsqueda del registro de auditoría. Esto se debe a que el cmdlet subyacente es un cmdlet de PowerShell de Exchange Online. 
    
- Para obtener instrucciones paso a paso sobre cómo buscar en el registro de auditoría, vea [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md). Para obtener más información acerca de la API de actividad de administración de Microsoft 365, vea Introducción a las API de administración de [Microsoft 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).

- Para comprobar que la búsqueda de registros de auditoría está activada, puede ejecutar el comando siguiente en PowerShell de Exchange Online:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    El valor de  `True` la  _propiedad UnifiedAuditLogIngestionEnabled_ indica que la búsqueda del registro de auditoría está activada. 
    
## <a name="turn-on-audit-log-search"></a>Activar la búsqueda del registro de auditoría

Si la búsqueda del registro de auditoría no está activada para su organización, puede activarla en el centro de cumplimiento o mediante Exchange Online PowerShell. Puede tardar varias horas después de activar la búsqueda del registro de auditoría antes de que pueda devolver resultados al buscar en el registro de auditoría.
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a>Usar el Centro de cumplimiento para activar la búsqueda del registro de auditoría

1. [Vaya al Centro de cumplimiento](https://protection.office.com) e inicie sesión.

2. En el Centro de cumplimiento, vaya a **Búsqueda de** registro de auditoría  >  **de búsqueda.**

   Si la búsqueda del registro de auditoría no está activada para su organización, se muestra un banner que dice que la auditoría debe estar activada para registrar la actividad de usuario y administrador.

3. Haga **clic en Activar auditoría**.

    ![Haga clic en Activar auditoría](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    El banner se actualiza para decir que el registro de auditoría se está preparando y que puede buscar actividad de usuario y administrador en unas horas.

### <a name="use-powershell-to-turn-on-audit-log-search"></a>Usar PowerShell para activar la búsqueda del registro de auditoría

1. [Conectarse a Exchange Online mediante PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Ejecute el siguiente comando de PowerShell para activar la búsqueda del registro de auditoría en Office 365.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Se muestra un mensaje que indica que el cambio puede tardar hasta 60 minutos en tener efecto.
  
## <a name="turn-off-audit-log-search"></a>Desactivar la búsqueda del registro de auditoría

Debe usar Exchange Online PowerShell para desactivar la búsqueda del registro de auditoría.
  
1. [Conectarse a Exchange Online mediante PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Ejecute el siguiente comando de PowerShell para desactivar la búsqueda del registro de auditoría.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Después de un tiempo, compruebe que la búsqueda del registro de auditoría está desactivada (deshabilitada). Puede realizar esto de dos maneras:

    - En Exchange Online PowerShell, ejecute el siguiente comando:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      El valor de  `False` la  _propiedad UnifiedAuditLogIngestionEnabled_ indica que la búsqueda del registro de auditoría está desactivada. 

    - En el [Centro de cumplimiento,](https://protection.office.com)vaya a **Búsqueda de** registro de auditoría de \> **búsqueda.**

      Se muestra un banner que dice que la auditoría debe estar activada para registrar la actividad de usuario y administrador.
