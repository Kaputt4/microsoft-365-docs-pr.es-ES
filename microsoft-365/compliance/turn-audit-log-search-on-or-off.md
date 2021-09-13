---
title: Activar o desactivar la auditoría
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
description: Cómo activar o desactivar la característica de búsqueda de registro de auditoría en el Centro de cumplimiento de Microsoft 365 para habilitar o deshabilitar la capacidad de los administradores de buscar en el registro de auditoría.
ms.openlocfilehash: 2c9331534035d0f0cf23a2dbec09f338a6f6a32b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216280"
---
# <a name="turn-auditing-on-or-off"></a>Activar o desactivar la auditoría

El registro de auditoría estará activado de forma predeterminada para Microsoft 365 y Office 365 organizaciones empresariales. Sin embargo, al configurar una nueva organización Microsoft 365 o Office 365, debe comprobar el estado de auditoría de la organización. Para obtener instrucciones, consulte [la sección Comprobar el estado](#verify-the-auditing-status-for-your-organization) de auditoría de su organización en este artículo. 

Cuando la auditoría en el Centro de cumplimiento de Microsoft 365 está activada, la actividad de usuario y administrador de su organización se registra en el registro de auditoría y se retiene durante 90 días y hasta un año, según la licencia asignada a los usuarios. Sin embargo, es posible que la organización tenga motivos para no querer registrar y conservar los datos del registro de auditoría. En esos casos, un administrador global puede decidir desactivar la auditoría en Microsoft 365.

> [!IMPORTANT]
> Si desactiva la auditoría en Microsoft 365, no puede usar la API de actividad de administración de Office 365 ni Azure Sentinel para obtener acceso a los datos de auditoría de su organización. Desactivar la auditoría siguiendo los pasos descritos en este artículo significa que no se devolverá ningún resultado al buscar en el registro de auditoría mediante el Centro de cumplimiento de Microsoft 365 o al ejecutar el cmdlet **Search-UnifiedAuditLog** en Exchange Online PowerShell. Esto también significa que los registros de auditoría no estarán disponibles a través de la API Office 365 actividad de administración o Azure Sentinel.
  
## <a name="before-you-turn-auditing-on-or-off"></a>Antes de activar o desactivar la auditoría

- Debe tener asignado el rol Registros de auditoría en Exchange Online para activar o desactivar la auditoría en su Microsoft 365 organización. De forma predeterminada, este rol se asigna a los  grupos de roles Administración de cumplimiento y Administración de la organización en la página Permisos del centro Exchange administración. Los administradores globales de Microsoft 365 son miembros del grupo de roles Administración de la organización en Exchange Online.

    > [!NOTE]
    > Los usuarios deben tener asignados permisos en Exchange Online para activar o desactivar la auditoría. Si asigna a los usuarios  el rol Registros de auditoría en la página Permisos de la Centro de cumplimiento de Microsoft 365, no podrán activar o desactivar la auditoría. Esto se debe a que el cmdlet subyacente es Exchange Online cmdlet de PowerShell.

- Para obtener instrucciones paso a paso sobre cómo buscar en el registro de auditoría, vea [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md). Para obtener más información acerca de la API Microsoft 365 actividad de administración, vea Introducción [a Microsoft 365 API de administración](/office/office-365-management-api/get-started-with-office-365-management-apis).

## <a name="verify-the-auditing-status-for-your-organization"></a>Comprobar el estado de auditoría de la organización

Para comprobar que la auditoría está activada para su organización, puede ejecutar el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
```

Un valor de `True` la  _propiedad UnifiedAuditLogIngestionEnabled_ indica que la auditoría está activada. Un valor de `False` indica que la auditoría no está activada.

## <a name="turn-on-auditing"></a>Activar la auditoría

Si la auditoría no está activada para su organización, puede activarla en el Centro de cumplimiento de Microsoft 365 o mediante Exchange Online PowerShell. Puede tardar varias horas después de activar la auditoría antes de que pueda devolver resultados al buscar en el registro de auditoría.
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>Usar el Centro de cumplimiento para activar la auditoría

1. Vaya a <https://compliance.microsoft.com> e inicie sesión.

2. En el panel de navegación izquierdo de la Centro de cumplimiento de Microsoft 365, haga clic en **Auditar**.

   Si la auditoría no está activada para su organización, se muestra un banner que le pedirá que comience a grabar la actividad de usuario y administrador.

   ![Banner en la página Auditoría.](../media/AuditingBanner.png)

3. Haga clic en **el banner Iniciar registro de actividad de usuario y** administrador.

   El cambio puede tardar hasta 60 minutos en tener efecto.

### <a name="use-powershell-to-turn-on-auditing"></a>Usar PowerShell para activar la auditoría

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el siguiente comando de PowerShell para activar la auditoría.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Se muestra un mensaje que indica que el cambio puede tardar hasta 60 minutos en tener efecto.
  
## <a name="turn-off-auditing"></a>Desactivar la auditoría

Debe usar powershell Exchange Online para desactivar la auditoría.
  
1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el siguiente comando de PowerShell para desactivar la auditoría.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Después de un tiempo, compruebe que la auditoría está desactivada (deshabilitada). Hay dos formas de hacerlo:

    - En Exchange Online PowerShell, ejecute el siguiente comando:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      El valor de  `False` la  _propiedad UnifiedAuditLogIngestionEnabled_ indica que la auditoría está desactivada.

    - Vaya a la **página Auditoría** de la Centro de cumplimiento de Microsoft 365.

      Si la auditoría no está activada para su organización, se muestra un banner que le pedirá que comience a grabar la actividad de usuario y administrador.

## <a name="audit-records-when-auditing-status-is-changed"></a>Registros de auditoría cuando se cambia el estado de auditoría

Los cambios en el estado de auditoría de la organización se auditan a sí mismos. Esto significa que los registros de auditoría se registran cuando la auditoría está activada o desactivada. Puede buscar en el Exchange de auditoría de administración de estos registros de auditoría.

Para buscar en el Exchange de auditoría del administrador los registros de auditoría que se generan al activar o desactivar la auditoría, ejecute el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

```powershell
Search-AdminAuditLog -Cmdlets Set-AdminAuditLogConfig -Parameters UnifiedAuditLogIngestionEnabled
```

Los registros de auditoría de estos eventos contienen información sobre cuándo se cambió el estado de auditoría, el administrador que lo cambió y la dirección IP del equipo que se usó para realizar el cambio. Las capturas de pantalla siguientes muestran registros de auditoría que corresponden a cambiar el estado de auditoría de la organización.

### <a name="audit-record-for-turning-on-auditing"></a>Registro de auditoría para activar la auditoría

![Registro de auditoría para activar la auditoría](../media/AuditStatusAuditingEnabled.png)

El valor de en la propiedad CmdletParameters indica que el registro de auditoría unificado se ha activado en el centro de cumplimiento o ejecutando el `Confirm` cmdlet **Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true.** 

### <a name="audit-record-for-turning-off-auditing"></a>Registro de auditoría para desactivar la auditoría

![Registro de auditoría para desactivar la auditoría](../media/AuditStatusAuditingDisabled.png)

El valor de `Confirm` no se incluye en la propiedad *CmdletParameters.* Esto indica que el registro de auditoría unificado se ha desactivado ejecutando el comando **Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false.**

Para obtener más información acerca de la búsqueda Exchange registro de auditoría de administración, vea [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).