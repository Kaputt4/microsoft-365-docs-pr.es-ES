---
title: Administrar directivas de retención de registros de auditoría
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Las directivas de retención de registros de auditoría forman parte de las nuevas capacidades de Auditoría avanzada en Microsoft 365. Una directiva de retención de registro de auditoría le permite especificar durante cuánto tiempo se conservan los registros de auditoría en su organización.
ms.openlocfilehash: 2ac95d9bb9c13b6bf0c0e31d17b4fb46c30c492a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687363"
---
# <a name="manage-audit-log-retention-policies"></a>Administrar directivas de retención de registros de auditoría

Puede crear y administrar directivas de retención de registros de auditoría en el Centro de seguridad y cumplimiento. Las directivas de retención de registros de auditoría forman parte de las nuevas capacidades de Auditoría avanzada en Microsoft 365. Una directiva de retención de registro de auditoría le permite especificar durante cuánto tiempo se conservan los registros de auditoría en su organización. Puede conservar los registros de auditoría hasta por 10 años. Puede crear directivas en función de los siguientes criterios:

- Todas las actividades en uno o más servicios de Microsoft 365

- Actividades específicas (en un servicio de Microsoft 365) realizadas por todos los usuarios o por usuarios específicos

- Un nivel de prioridad que especifique qué directiva prevalece en caso de que tenga varias directivas en su organización

## <a name="default-audit-log-retention-policy"></a>Directivas de retención de registros de auditoría predeterminadas

Auditoría avanzada en Microsoft 365 proporciona una directiva de retención de registros de auditoría predeterminada para todas las organizaciones. Esta directiva conserva todos los registros de auditoría de Exchange Online, SharePoint Online, OneDrive para la Empresa y Azure Active Directory durante un año. Esta directiva predeterminada conserva los registros de auditoría que contienen el valor de **Exchange**, **SharePoint**, **OneDrive**, **AzureActiveDirectory** para la propiedad de **Carga de trabajo** (que es el servicio en el que se produjo la actividad). La directiva predeterminada no se puede modificar. Vea la sección [Más información](#more-information) en este artículo para obtener una lista de los tipos de registros para cada carga de trabajo que se incluye en la directiva predeterminada.

> [!NOTE]
> La directiva de retención de registros de auditoría predeterminada solo se aplica a los registros de auditoría para la actividad realizada por usuarios que tienen asignada una licencia de Office 365 o Microsoft 365 E5, o que tienen una licencia del complemento de Cumplimiento de Microsoft 365 E5 o de eDiscovery y Auditoría de Microsoft 365 E5 Si no tiene usuarios o invitados de E5 en su organización, los registros de auditoría correspondientes se conservarán durante 90 días.

## <a name="before-you-create-an-audit-log-retention-policy"></a>Antes de crear una directiva de retención de registros de auditoría

- Debe tener asignado el rol de Configuración de la organización en el Centro de seguridad y cumplimiento para crear o modificar una directiva de retención de auditoría.

- Puede tener un máximo de 50 directivas de retención de registros de auditoría en su organización.

- Para conservar un registro de auditoría durante más de 90 días (y hasta un año), el usuario que ha generado dicho registro (mediante una actividad de auditoría) debe tener asignada una licencia de Office 365 E5 o Microsoft 365 E5, o tener una licencia de complemento de Cumplimiento de Microsoft 365 E5 o E5 eDiscovery y Auditoría. Para conservar los registros de auditoría durante 10 años, el usuario que genera el registro de auditoría también debe tener asignada una licencia del complemento de retención de registro de auditoría de 10 años además de una licencia E5.

- Todas las directivas de retención de registros de auditoría personalizadas (creadas por su organización) tienen prioridad sobre la directiva de retención predeterminada. Por ejemplo, si crea una directiva de retención de registros de auditoría para la actividad del buzón de Exchange que tiene un período de retención inferior a un año, los registros de auditoría de las actividades de buzón de Exchange se conservarán durante la duración más corta especificada en la directiva personalizada.

## <a name="create-an-audit-log-retention-policy"></a>Crear una directiva de retención de registros de auditoría

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión con la cuenta de usuario que tenga asignado el rol de Configuración en la página Permisos de la organización en el Centro de seguridad y cumplimiento.

2. En el panel izquierdo del Centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todo**, y luego haga clic en **Auditoría**.

3. Haga clic en la pestaña **Auditar directivas de retención**.

4. Haga clic en **Crear directiva de retención de auditoría** y, después, complete los siguientes campos en la página flotante:

    ![Página flotante de la directiva de retención de la nueva auditoría](../media/CreateAuditLogRetentionPolicy.png)

   1. **Nombre de directiva:** el nombre de la directiva de retención de registros de auditoría. Este nombre debe ser único en su organización y no puede cambiarse después de crear la directiva.

   2. **Descripción:** es opcional, pero le resultará útil para proporcionar información sobre la directiva (como el tipo de registro o la carga de trabajo, los usuarios especificados en la directiva y la duración).

   3. **Usuarios:** seleccione uno o más usuarios para aplicar la directiva. Si deja este cuadro en blanco, la directiva se aplicará a todos los usuarios. Si deja en blanco **Tipo de registro**, deberá seleccionar un usuario.

   4. **Tipo de registro:** el tipo de registro de auditoría al que se aplica la directiva. Si deja en blanco esta propiedad, debe seleccionar un usuario en el cuadro **Usuarios**. Puede seleccionar un único tipo de registro o varios tipos de registro:

   - Si selecciona un único tipo de registro, el campo **Actividades** se mostrará dinámicamente. Puede usar la lista desplegable para seleccionar las actividades del tipo de registro seleccionado a las que desea aplicar la directiva. Si no elige actividades específicas, la directiva se aplicará a todas las actividades del tipo de registro seleccionado.

   - Si selecciona varios tipos de registro, no podrá seleccionar actividades. La directiva se aplicará a todas las actividades de los tipos de registro seleccionados.

   5. **Duración:** es la cantidad de tiempo que se conservarán los registros de auditoría que cumplan los criterios de la directiva.

   6. **Prioridad:** este valor determina el orden en el que se procesan las directivas de retención de registros de auditoría de su organización. Un valor más alto indica una prioridad mayor. Por ejemplo, una directiva con un valor de prioridad de **5** tendría prioridad sobre una directiva con un valor de prioridad de **0**. Como se ha explicado anteriormente, cualquier directiva de retención de registros de auditoría personalizada tiene prioridad sobre la directiva predeterminada para su organización.

5. Haga clic en **Guardar** para crear la nueva directiva de retención de registros de auditoría.

   La nueva directiva se muestra en la lista de la pestaña **Auditar directivas de retención**.

## <a name="manage-audit-log-retention-policies"></a>Administrar directivas de retención de registros de auditoría

Las directivas de retención de registros de auditoría se muestran en la pestaña **Auditar directivas de retención** (también denominada *panel*). Puede usar el panel para ver, editar y eliminar directivas de retención de auditoría.

### <a name="view-policies-in-the-dashboard"></a>Ver directivas en el panel

Las directivas de retención de registros de auditoría se muestran en el panel. Una ventaja de ver las directivas en el panel es que puede hacer clic en la columna **Prioridad** para enumerar las directivas en la prioridad en que se aplican. Como se explicó previamente, un valor más alto indica una prioridad mayor.

![Columna Prioridad en el panel de directivas de retención de auditoría](../media/AuditLogRetentionDashboardPriority.png)

También puede seleccionar una directiva para mostrar su configuración en la página flotante.

> [!NOTE]
> La directiva de retención de registros de auditoría predeterminada de la organización no se muestra en el panel.

### <a name="edit-policies-in-the-dashboard"></a>Editar directivas en el panel

Para editar una directiva, selecciónela para mostrar la página de control flotante. Puede modificar una o más opciones de configuración y, después, guardar los cambios.


> [!IMPORTANT]
> Si usa el cmdlet **New-UnifiedAuditLogRetentionPolicy**, es posible crear una directiva de retención de registros de auditoría para las actividades y los tipos de registros que no están disponibles en la herramienta **Crear directivas de retención de auditoría** en el panel. En este caso, no podrá editar la directiva (por ejemplo, cambiar la duración de la retención o agregar y quitar actividades) desde el panel **Directivas de retención de auditoría**. Solo podrá ver y eliminar la directiva en el centro de cumplimiento. Para editar la Directiva, tendrá que usar el cmdlet [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) en el centro de seguridad y cumplimiento de PowerShell.<br/><br/>**Sugerencia:** se muestra un mensaje en la parte superior de la página de salida para las directivas que se deben editar con PowerShell.

### <a name="delete-policies-in-the-dashboard"></a>Eliminar directivas en el panel

Para eliminar una directiva, haga clic en el icono **Eliminar** ![Eliminar icono](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg) y, después, confirme que quiere eliminar la directiva. La directiva se quita del panel, pero puede tardar hasta 30 minutos en quitarse la directiva de la organización.

## <a name="create-and-manage-audit-log-retention-policies-in-powershell"></a>Crear y administrar directivas de retención de registros de auditoría en PowerShell

También puede usar PowerShell del Centro de seguridad y cumplimiento para crear y administrar directivas de retención de registros de auditoría. Uno de los motivos para usar PowerShell es crear una directiva para un tipo de registro o actividad que no esté disponible en la interfaz de usuario.

### <a name="create-an-audit-log-retention-policy-in-powershell"></a>Crear una directiva de retención de registros de auditoría en PowerShell

Siga estos pasos para crear una directiva de retención de registros de auditoría en PowerShell:

1. [Conectarse a PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell).

2. Ejecute el siguiente comando para crear una directiva de retención de registros de auditoría.

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TenYears -Priority 100
   ```

    En este ejemplo se crea una directiva de retención de registros de auditoría denominada "Directiva de auditoría de Microsoft Teams" con esta configuración:

   - Una descripción de la directiva.

   - Conserva todas las actividades de Microsoft Teams (definidas en el parámetro *RecordType*).

   - Conserva los registros de auditoría de Microsoft Teams por 10 años.

   - Una prioridad de 100.

Este es otro ejemplo para la creación de una directiva de retención de registros de auditoría. Esta directiva conserva los registros de auditoría de la actividad "el usuario inició sesión" durante seis meses para el usuario admin@contoso.onmicrosoft.com.

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

Para obtener más información, consulte [New-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/new-unifiedauditlogretentionpolicy).

### <a name="view-policies-in-powershell"></a>Ver directivas en PowerShell

Use el cmdlet [Get-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/get-unifiedauditlogretentionpolicy) en PowerShell del Centro de seguridad y cumplimiento para ver directivas de retención de registros de auditoría.

Este es un comando de ejemplo para mostrar la configuración para todas directivas de retención de registros de auditoría en su organización. Este comando ordena las directivas de mayor a menor prioridad.

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> El cmdlet **Get-UnifiedAuditLogRetentionPolicy** no devuelve la directiva de retención de registros de auditoría predeterminada para su organización.

### <a name="edit-policies-in-powershell"></a>Editar directivas en PowerShell

Use el cmdlet [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) en PowerShell del Centro de seguridad y cumplimiento para editar una directiva de retención de registros de auditoría existente.

### <a name="delete-policies-in-powershell"></a>Eliminar directivas en PowerShell

Use el cmdlet [Remove-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/remove-unifiedauditlogretentionpolicy) en PowerShell del Centro de seguridad y cumplimiento para eliminar una directiva de retención de registros de auditoría. La directiva puede tardar hasta 30 minutos para eliminarse por completo de su organización.

## <a name="more-information"></a>Más información

Como se ha indicado anteriormente, los registros de auditoría para las operaciones en Azure Active Directory, Exchange Online, SharePoint Online y OneDrive para la Empresa se conservan durante un año de forma predeterminada. En la siguiente tabla se enumeran todos los tipos de registro (para cada uno de estos servicios) incluidos en la directiva de retención de registros de auditoría predeterminada. Esto significa que los registros de auditoría de cualquier operación con este tipo de registro se conservan durante un año, a menos que una directiva de retención de registros de auditoría personalizada tenga prioridad para un tipo de registro, una operación o un usuario específicos. El valor Enum (que se muestra como el valor de la propiedad RecordType en un registro de auditoría) para cada tipo de registro se muestra entre paréntesis.

|AzureActiveDirectory |Exchange  |SharePoint o OneDrive|
|:---------|:---------|:---------|
|AzureActiveDirectory (8)|ExchangeAdmin (1)|ComplianceDLPSharePoint (11)|
|AzureActiveDirectoryAccountLogon (9)|ExchangeItem (2)|ComplianceDLPSharePointClassification (33)|
|AzureActiveDirectoryStsLogon (15)|Campaña (62)|Proyecto (35)|
||ComplianceDLPExchange (13)|SharePoint (4)|
||ComplianceSupervisionExchange (68)|SharePointCommentOperation (37)|
||CustomerKeyServiceEncryption (69)|SharePointContentTypeOperation (55)|
||ExchangeAggregatedOperation (19)|SharePointFieldOperation (56)|
||ExchangeItemAggregated (50)|SharePointFileOperation (6)|
||ExchangeItemGroup (3)|SharePointListOperation (36)|
||InformationBarrierPolicyApplication (53)|SharePointSharingOperation (14)|
||||
