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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: Cómo activar o desactivar la característica de búsqueda de registros de auditoría en el portal de cumplimiento de Microsoft Purview para habilitar o deshabilitar la capacidad de los administradores de buscar en el registro de auditoría.
ms.openlocfilehash: 587c7f98cd04eef618508e096f290d1d299ec096
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64944533"
---
# <a name="turn-auditing-on-or-off"></a>Activar o desactivar la auditoría

El registro de auditoría se activará de forma predeterminada para Microsoft 365 y Office 365 organizaciones empresariales. Sin embargo, al configurar una nueva Microsoft 365 o Office 365 organización, debe comprobar el estado de auditoría de la organización. Para obtener instrucciones, consulte [la sección Verify the auditing status for your organization (Comprobar el estado de auditoría de su organización](#verify-the-auditing-status-for-your-organization) ) de este artículo. 

Cuando se activa la auditoría en el portal de cumplimiento de Microsoft Purview, la actividad de usuario y administrador de su organización se registra en el registro de auditoría y se conserva durante 90 días y hasta un año, en función de la licencia asignada a los usuarios. Sin embargo, su organización puede tener motivos para no querer registrar y conservar los datos de registro de auditoría. En esos casos, un administrador global puede decidir desactivar la auditoría en Microsoft 365.

> [!IMPORTANT]
> Si desactiva la auditoría en Microsoft 365, no puede usar la API de actividad de administración de Office 365 ni Microsoft Sentinel para acceder a los datos de auditoría de su organización. Desactivar la auditoría siguiendo los pasos descritos en este artículo significa que no se devolverá ningún resultado al buscar en el registro de auditoría mediante el portal de cumplimiento o al ejecutar el cmdlet **Search-UnifiedAuditLog** en Exchange Online PowerShell. Esto también significa que los registros de auditoría no estarán disponibles a través de Office 365 Management Activity API o Microsoft Sentinel.
  
## <a name="before-you-turn-auditing-on-or-off"></a>Antes de activar o desactivar la auditoría

- Debe tener asignado el rol Registros de auditoría en Exchange Online para activar o desactivar la auditoría en la organización de Microsoft 365. De forma predeterminada, este rol se asigna a los grupos de roles Administración de cumplimiento y Administración de la organización en la página **Permisos** del centro de administración de Exchange. Los administradores globales de Microsoft 365 son miembros del grupo de roles Administración de la organización en Exchange Online.

    > [!NOTE]
    > A los usuarios se les deben asignar permisos en Exchange Online para activar o desactivar la auditoría. Si asigna a los usuarios el rol Registros de auditoría en la página **Permisos** del portal de cumplimiento, no podrán activar ni desactivar la auditoría. Esto se debe a que el cmdlet subyacente es un cmdlet de PowerShell Exchange Online.

- Para obtener instrucciones paso a paso sobre cómo buscar en el registro de auditoría, consulte [Búsqueda en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md). Para obtener más información sobre la API de actividad de administración de Microsoft 365, consulte [Comenzar con las API de administración de Microsoft 365](/office/office-365-management-api/get-started-with-office-365-management-apis).

## <a name="verify-the-auditing-status-for-your-organization"></a>Comprobación del estado de auditoría de la organización

Para comprobar que la auditoría está activada para su organización, puede ejecutar el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
```

Un valor de `True` para la propiedad  _UnifiedAuditLogIngestionEnabled_ indica que la auditoría está activada. Un valor de `False` indica que la auditoría no está activada.

> [!NOTE]
> Asegúrese de ejecutar el comando anterior en Exchange Online PowerShell. No puede usar Security & Compliance PowerShell para ejecutar este comando.

## <a name="turn-on-auditing"></a>Activar la auditoría

Si la auditoría no está activada para su organización, puede activarla en el portal de cumplimiento o mediante Exchange Online PowerShell. Puede tardar varias horas después de activar la auditoría antes de poder devolver resultados al buscar en el registro de auditoría.
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>Uso del centro de cumplimiento para activar la auditoría

1. Vaya a <https://compliance.microsoft.com> e inicie sesión.

2. En el panel de navegación izquierdo del portal de cumplimiento, haga clic en **Auditar**.

   Si la auditoría no está activada para su organización, se muestra un banner que le pide que empiece a grabar la actividad de usuario y administrador.

   ![Banner en la página Auditoría.](../media/AuditingBanner.png)

3. Haga clic en el banner **Iniciar grabación de actividad de usuario y administrador** .

   El cambio puede tardar hasta 60 minutos en surtir efecto.

### <a name="use-powershell-to-turn-on-auditing"></a>Uso de PowerShell para activar la auditoría

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el siguiente comando de PowerShell para activar la auditoría.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Se muestra un mensaje que indica que el cambio puede tardar hasta 60 minutos en surtir efecto.
  
## <a name="turn-off-auditing"></a>Desactivar la auditoría

Tiene que usar Exchange Online PowerShell para desactivar la auditoría.
  
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

      El valor de para  `False` la propiedad  _UnifiedAuditLogIngestionEnabled_ indica que la auditoría está desactivada.

    - Vaya a la página **Auditoría** del portal de cumplimiento.

      Si la auditoría no está activada para su organización, se muestra un banner que le pide que empiece a grabar la actividad de usuario y administrador.

## <a name="audit-records-when-auditing-status-is-changed"></a>Registros de auditoría al cambiar el estado de la auditoría

Los cambios en el estado de auditoría de la organización se auditan por sí mismos. Esto significa que los registros de auditoría se registran cuando la auditoría está activada o desactivada. Puede buscar estos registros de auditoría en el registro de auditoría del administrador de Exchange.

Para buscar en el registro de auditoría de Exchange administrador los registros de auditoría que se generan al activar o desactivar la auditoría, ejecute el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

```powershell
Search-AdminAuditLog -Cmdlets Set-AdminAuditLogConfig -Parameters UnifiedAuditLogIngestionEnabled
```

Los registros de auditoría de estos eventos contienen información sobre cuándo se cambió el estado de auditoría, el administrador que lo cambió y la dirección IP del equipo que se usó para realizar el cambio. En las capturas de pantalla siguientes se muestran los registros de auditoría que corresponden a cambiar el estado de auditoría de la organización.

### <a name="audit-record-for-turning-on-auditing"></a>Registro de auditoría para activar la auditoría

![Registro de auditoría para activar la auditoría](../media/AuditStatusAuditingEnabled.png)

El valor de en `Confirm` la propiedad *CmdletParameters* indica que el registro de auditoría unificado se ha activado en el centro de cumplimiento o mediante la ejecución del cmdlet **Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true** .

### <a name="audit-record-for-turning-off-auditing"></a>Registro de auditoría para desactivar la auditoría

![Registro de auditoría para desactivar la auditoría](../media/AuditStatusAuditingDisabled.png)

El valor de `Confirm` no se incluye en la propiedad *CmdletParameters* . Esto indica que el registro de auditoría unificado se ha desactivado ejecutando el comando **Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false** .

Para obtener más información sobre cómo buscar en el registro de auditoría de administración de Exchange, consulte [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).
