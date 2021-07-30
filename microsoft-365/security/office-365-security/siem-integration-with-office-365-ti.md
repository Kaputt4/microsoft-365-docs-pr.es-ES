---
title: Integración de SIEM con Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integre el servidor SIEM de su organización con Microsoft Defender para Office 365 eventos de amenazas relacionados en la API de administración Office 365 actividad.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0cf5206b1b821f876aa810ba2bf280ba2f426544
ms.sourcegitcommit: b3091791196828883d8284497561027df692d109
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2021
ms.locfileid: "53663868"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Integración de SIEM con Microsoft Defender para Office 365

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Si su organización usa un servidor de administración de eventos y de información de seguridad (SIEM), puede integrar Microsoft Defender para Office 365 con el servidor SIEM. Puede configurar esta integración mediante la API de administración Office 365 [actividad](/office/office-365-management-api/office-365-management-activity-api-reference).

La integración de SIEM permite ver información, como malware o phish detectado por Microsoft Defender para Office 365, en los informes del servidor SIEM.

- Para ver un ejemplo de integración de SIEM con Microsoft Defender para Office 365, consulte Tech [Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).
- Para obtener más información sobre las API de Office 365 administración, vea Office 365 introducción a las [API de administración.](/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>Cómo funciona la integración de SIEM

La API Office 365 administración de actividades recupera información sobre acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad Microsoft 365 y Azure Active Directory de la organización. Si su organización tiene Microsoft Defender para Office 365 plan 1 o 2, o Office 365 E5, puede usar Microsoft Defender para [Office 365 esquema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).

Recientemente, los eventos de las capacidades automatizadas de investigación y respuesta en [Microsoft Defender para Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) se agregaron a la API Office 365 actividad de administración. Además de incluir datos sobre los detalles principales de la investigación, como el identificador, el nombre y el estado, la API también contiene información de alto nivel sobre las acciones y entidades de investigación.

El servidor SIEM u otro sistema similar sondea la carga de **trabajo audit.general** para obtener acceso a eventos de detección. Para obtener más información, vea [Introducción a Office 365 API de administración](/office/office-365-management-api/get-started-with-office-365-management-apis).

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Tipo: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

En la tabla siguiente se resumen los valores **de AuditLogRecordType** que son relevantes para Microsoft Defender para Office 365 eventos:

| Valor | Nombre del miembro | Descripción |
|---|---|---|
| 28| ThreatIntelligence | Eventos de suplantación de identidad y malware de Exchange Online Protection y Microsoft Defender para Office 365. |
| 41| ThreatIntelligenceUrl | Caja fuerte Vincula el tiempo de bloqueo y bloquea eventos de invalidación de Microsoft Defender para Office 365. |
| 47| ThreatIntelligenceAtpContent | Eventos de suplantación de identidad y malware para archivos de SharePoint Online, OneDrive para la Empresa y Microsoft Teams, desde Microsoft Defender para Office 365. |
| 64| AirInvestigation | Eventos automatizados de investigación y respuesta, como detalles de investigación y artefactos relevantes, de Microsoft Defender para Office 365 Plan 2. |
|

> [!IMPORTANT]
> Debe tener asignado el rol administrador global o administrador de seguridad en el portal de Microsoft 365 Defender para configurar la integración de SIEM con Microsoft Defender para Office 365. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).
>
> El registro de auditoría debe estar activado para el Microsoft 365 de auditoría. Para obtener ayuda con esto, vea Activar o desactivar la búsqueda [del registro de auditoría.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>Consulta también

[Investigación y respuesta de amenazas de Office 365](office-365-ti.md)

[Investigación y respuesta automatizadas (AIR) en Office 365](automated-investigation-response-office.md)