---
title: Identificación de los cmdlets de PowerShell disponibles para la retención
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: normal
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-compliance
description: Identifique los cmdlets de PowerShell para la retención que admiten la configuración a escala, la automatización o podría ser necesario para escenarios de configuración avanzada.
ms.openlocfilehash: 23dda0c7e5cdc2ce52c2dfca8e5ab575d5653b99
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66625993"
---
# <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a>Cmdlets de PowerShell para directivas de retención y etiquetas de retención

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Use las secciones siguientes para identificar los principales cmdlets de PowerShell que están disponibles para las directivas de retención y las etiquetas de retención que podría necesitar para la configuración a escala, scripts automatizados o escenarios de configuración avanzada. Para obtener la lista completa de cmdlets, consulte la [lista de retención de directivas y cumplimiento](/powershell/module/exchange#policy-and-compliance-retention) de la documentación de PowerShell.

Antes de usar estos cmdlets, primero debe [conectarse a PowerShell del Centro de cumplimiento de seguridad &](/powershell/exchange/connect-to-scc-powershell).

En las descripciones siguientes, una directiva de retención puede hacer referencia a una directiva de retención (sin etiquetas) o a una directiva de etiquetas de retención. Cada directiva define si es estática o adaptable y las ubicaciones de la directiva que se va a aplicar. A continuación, la directiva requiere una regla para completar la configuración.

Por ejemplo:
- Una directiva de retención necesita una regla que defina la configuración de retención, como conservar durante cinco años y, a continuación, eliminar.

Cuando se usan etiquetas de retención, contienen la configuración de retención y sus directivas necesitan reglas diferentes:
- Una directiva de etiquetas de retención que publique necesita una regla que defina qué etiquetas se deben mostrar en las aplicaciones.
- Una directiva de etiqueta de retención de aplicación automática necesita una regla que defina la etiqueta que se va a aplicar y las condiciones para aplicar la etiqueta.

## <a name="retention-cmdlets-for-most-locations"></a>Cmdlets de retención para la mayoría de las ubicaciones

Use los cmdlets de la tabla siguiente cuando las ubicaciones sean **correo electrónico de Exchange**, **sitios de SharePoint**, **cuentas de OneDrive**, **Grupos de Microsoft 365**, **Skype Empresarial**, **carpetas públicas de Exchange**, **mensajes de chat de Teams** o **mensajes de canal de Teams**.

No use estos cmdlets cuando las ubicaciones son para mensajes de canal privado de Teams, mensajes de usuario de Yammer o mensajes de la comunidad de Yammer. Estas ubicaciones tienen cmdlets alternativos que se identifican en la [sección siguiente](#retention-cmdlets-specific-to-teams-private-channels-and-yammer).

|Cmdlet|Descripción|Ubicaciones aplicables|
|:-----|:-----|:-----|:-----|
|[Enable-ComplianceTagStorage](/powershell/module/exchange/enable-compliancetagstorage) <br /><br /> [Get-ComplianceTagStorage](/powershell/module/exchange/enable-compliancetagstorage) |Una operación única para crear almacenamiento o ver ese almacenamiento para etiquetas de retención |Correo electrónico de Exchange <br /><br />Sitios de SharePoint <br /><br /> Cuentas de OneDrive <br /><br /> Grupos de Microsoft 365|
|[Get-ComplianceTag](/powershell/module/exchange/get-compliancetag)<br /><br> [New-ComplianceTag](/powershell/module/exchange/new-compliancetag) <br /><br> [Remove-ComplianceTag](/powershell/module/exchange/remove-compliancetag) <br /><br> [Set-ComplianceTag](/powershell/module/exchange/set-compliancetag) |Ver, crear, eliminar y configurar etiquetas de retención |Correo electrónico de Exchange <br /><br /> Sitios de SharePoint <br /><br /> Cuentas de OneDrive<br /><br /> Grupos de Microsoft 365|
|[Get-RecordReviewNotificationTemplateConfig](/powershell/module/exchange/get-recordreviewnotificationtemplateconfig) <br /><br /> [Set-RecordReviewNotificationTemplateConfig](/powershell/module/exchange/remove-retentioncompliancepolicy)  |Visualización o configuración de la configuración para la notificación de revisión de eliminación y la configuración de recordatorio |Correo electrónico de Exchange <br /><br /> Sitios de SharePoint <br /><br /> Cuentas de OneDrive <br /><br /> Grupos de Microsoft 365|
|[Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy) <br /><br /> [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) <br /><br /> [Remove-RetentionCompliancePolicy](/powershell/module/exchange/remove-retentioncompliancepolicy) <br /><br /> [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) |Ver, crear, eliminar y configurar directivas para la retención |Correo electrónico de Exchange <br /><br /> Sitios de SharePoint <br /><br /> Cuentas de OneDrive<br /><br /> Grupos de Microsoft 365 <br /><br /> Skype Empresarial <br /><br /> Carpetas públicas de Exchange <br /><br /> Mensajes de chat de Teams <br /><br /> Mensajes de canal de Teams |
|[Get-RetentionComplianceRule](/powershell/module/exchange/get-retentioncompliancepolicy) <br /><br /> [New-RetentionComplianceRule](/powershell/module/exchange/get-retentioncompliancepolicy) <br /><br /> [Set-RetentionComplianceRule](/powershell/module/exchange/set-retentioncompliancerule) <br /><br /> [Remove-RetentionComplianceRule](/powershell/module/exchange/remove-retentioncompliancerule)  | Visualización, creación, configuración y eliminación de las directivas para las etiquetas de retención o retención |Correo electrónico de Exchange <br /><br /> Sitios de SharePoint <br /><br /> Cuentas de OneDrive <br /><br /> Grupos de Microsoft 365 <br /><br /> Skype Empresarial <br /><br /> Carpetas públicas de Exchange <br /><br /> Mensajes de chat de Teams <br /><br /> Mensajes de canal de Teams |

## <a name="retention-cmdlets-specific-to-teams-private-channels-and-yammer"></a>Cmdlets de retención específicos de los canales privados de Teams y Yammer

Use los siguientes cmdlets cuando las ubicaciones sean para **mensajes de canal privado de Teams**, **mensajes de usuario de Yammer** o mensajes de **la comunidad de Yammer**.

Cuando las ubicaciones son para mensajes de chat de Teams, mensajes de canal de Teams, correo electrónico de Exchange, sitios de SharePoint, cuentas de OneDrive, Grupos de Microsoft 365, Skype Empresarial o carpetas públicas de Exchange, use los cmdlets enumerados en la [sección anterior](#retention-cmdlets-for-most-locations).

|Cmdlet|Descripción|Ubicaciones aplicables|
|:-----|:-----|:-----|:-----|
|[Get-AppRetentionCompliancePolicy](/powershell/module/exchange/get-appretentioncompliancepolicy) <br /><br> [New-AppRetentionCompliancePolicy](/powershell/module/exchange/new-appretentioncompliancepolicy) <br /><br> [Remove-AppRetentionCompliancePolicy](/powershell/module/exchange/remove-appretentioncompliancepolicy) <br /><br> [Set-AppRetentionCompliancePolicy](/powershell/module/exchange/remove-appretentioncompliancepolicy) | Ver, crear, eliminar y configurar directivas de retención |Mensajes del canal privado de Teams <br /><br /> Mensajes del usuario de Yammer <br /><br /> Mensajes de la comunidad de Yammer|
|[Get-AppRetentionComplianceRule](/powershell/module/exchange/get-appretentioncompliancerule) <br /><br /> [New-AppRetentionComplianceRule](/powershell/module/exchange/new-appretentioncompliancerule) <br /><br /> [Remove-AppRetentionComplianceRule](/powershell/module/exchange/remove-appretentioncompliancerule) <br /><br /> [Set-AppRetentionComplianceRule](/powershell/module/exchange/remove-appretentioncompliancerule) | Ver, crear, eliminar y configurar las opciones de retención para las directivas de retención |Mensajes del canal privado de Teams <br /><br /> Mensajes del usuario de Yammer <br /><br /> Mensajes de la comunidad de Yammer|

## <a name="configuration-guidance"></a>Instrucciones de configuración

Use las páginas de ayuda asociadas a cada cmdlet para obtener información detallada y ejemplos.

Para obtener ayuda guiada para crear y publicar etiquetas de retención, consulte [Creación y publicación de etiquetas de retención mediante PowerShell](bulk-create-publish-labels-using-powershell.md).