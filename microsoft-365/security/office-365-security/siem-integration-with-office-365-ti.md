---
title: Integración de SIEM con Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: ''
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- m365-security
description: Integre el servidor SIEM de su organización con Microsoft Defender para Office 365 y eventos de amenazas relacionados en la API de administración de actividad de Office 365.
ms.custom: seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 3b628cd2981ebe64f97633dff3398321a4aea6d1
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68626827"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Integración de SIEM con Microsoft Defender para Office 365

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

Si su organización usa un servidor de administración de eventos e información de seguridad (SIEM), puede integrar Microsoft Defender para Office 365 con el servidor SIEM. Puede configurar esta integración mediante la [API de administración de actividad de Office 365](/office/office-365-management-api/office-365-management-activity-api-reference).

La integración siem permite ver información, como malware o phish detectados por Microsoft Defender para Office 365, en los informes del servidor SIEM.

- Para ver un ejemplo de integración de SIEM con Microsoft Defender para Office 365, consulte [el blog de tech community: Improve the Effectiveness of your SOC with Defender para Office 365 and the O365 Management API(Blog de tech community: Mejora de la eficacia de su SOC con Defender para Office 365 y la API de administración de O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)).
- Para obtener más información sobre las API de administración de Office 365, consulte [introducción a las API de administración de Office 365](/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>Funcionamiento de la integración siem

La API de administración de actividad de Office 365 recupera información sobre las acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Microsoft 365 y Azure Active Directory de la organización. Si su organización tiene Microsoft Defender para Office 365 plan 1 o 2, o Office 365 E5, puede usar el [esquema de Microsoft Defender para Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).

Recientemente, los eventos de las funcionalidades automatizadas de investigación y respuesta en [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) se agregaron a la API de actividad de administración de Office 365. Además de incluir datos sobre los detalles principales de la investigación, como el identificador, el nombre y el estado, la API también contiene información de alto nivel sobre las acciones de investigación y las entidades.

El servidor SIEM u otro sistema similar sondea la carga de trabajo **audit.general** para acceder a los eventos de detección. Para más información, consulte [Introducción a las API de administración de Office 365](/office/office-365-management-api/get-started-with-office-365-management-apis).

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Tipo: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

En la tabla siguiente se resumen los valores de **AuditLogRecordType** que son relevantes para los eventos de Microsoft Defender para Office 365:<br/><br/>

| Valor | Nombre del miembro | Descripción |
|---|---|---|
| 28| ThreatIntelligence | Eventos de suplantación de identidad y malware de Exchange Online Protection y Microsoft Defender para Office 365. |
| 41| ThreatIntelligenceUrl | Eventos de invalidación de bloque y tiempo de bloqueo de vínculos seguros de Microsoft Defender para Office 365. |
| 47| ThreatIntelligenceAtpContent | Eventos de phishing y malware para archivos en SharePoint Online, OneDrive para la Empresa y Microsoft Teams, desde Microsoft Defender para Office 365. |
| 64| AirInvestigation | Eventos de investigación y respuesta automatizados, como detalles de la investigación y artefactos pertinentes, de Microsoft Defender para Office 365 Plan 2. |

> [!IMPORTANT]
> Debe tener asignado el rol de administrador global o administrador de seguridad en el portal de Microsoft 365 Defender para configurar la integración siem con Microsoft Defender para Office 365. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).
>
> El registro de auditoría debe estar activado para el entorno de Microsoft 365. Para obtener ayuda con esto, consulte [Activar o desactivar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="see-also"></a>Vea también

[Investigación y respuesta de amenazas de Office 365](office-365-ti.md)

[Investigación y respuesta automatizadas (AIR) en Office 365](automated-investigation-response-office.md)
