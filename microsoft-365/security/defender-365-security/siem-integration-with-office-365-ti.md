---
title: Integración de SIEM con Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integre el servidor SIEM de su organización con Microsoft Defender para Office 365 y eventos de amenazas relacionados en la API de administración de actividades de Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a456ee970015aea5936ae86ec009cb2ff46e99c2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072504"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Integración de SIEM con Microsoft Defender para Office 365

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Si su organización usa un servidor de administración de eventos y información de seguridad (SIEM), puede integrar Microsoft Defender para Office 365 con el servidor SIEM. Puede configurar esta integración mediante la API de administración de actividades [de Office 365](/office/office-365-management-api/office-365-management-activity-api-reference).

La integración de SIEM permite ver información, como malware o phish detectado por Microsoft Defender para Office 365, en los informes del servidor SIEM.

- Para ver un ejemplo de integración de SIEM con Microsoft Defender para Office 365, vea [tech community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Para obtener más información sobre las API de administración de Office 365, vea [Office 365 Management API overview](/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>Cómo funciona la integración de SIEM

La API de administración de actividades de Office 365 recupera información sobre acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Microsoft 365 y Azure Active Directory de su organización. Si su organización tiene Microsoft Defender para Office 365 Plan 1 o 2 u Office 365 E5, puede usar el esquema de [Microsoft Defender para Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).

Recientemente, los eventos de las capacidades automatizadas de investigación y respuesta en [Microsoft Defender para Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) se agregaron a la API de actividad de administración de Office 365. Además de incluir datos sobre los detalles principales de la investigación, como el identificador, el nombre y el estado, la API también contiene información de alto nivel sobre las acciones y entidades de investigación.

El servidor SIEM u otro sistema similar sondea la carga de **trabajo audit.general** para obtener acceso a eventos de detección. Para obtener más información, vea Introducción a las API de administración [de Office 365.](/office/office-365-management-api/get-started-with-office-365-management-apis)

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Tipo: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

En la tabla siguiente se resumen los valores **de AuditLogRecordType** relevantes para eventos de Microsoft Defender para Office 365:

|Valor|Nombre del miembro|Descripción|
|---|---|---|
|28|ThreatIntelligence|Eventos de suplantación de identidad y malware de Exchange Online Protection y Microsoft Defender para Office 365.|
|41|ThreatIntelligenceUrl|Eventos de invalidación de bloqueo y tiempo de bloqueo de vínculos seguros de Microsoft Defender para Office 365.|
|47|ThreatIntelligenceAtpContent|Eventos de suplantación de identidad y malware para archivos en SharePoint Online, OneDrive para la Empresa y Microsoft Teams, de Microsoft Defender para Office 365.|
|64|AirInvestigation|Eventos automatizados de investigación y respuesta, como detalles de investigación y artefactos relevantes, de Microsoft Defender para Office 365 Plan 2.|
|

> [!IMPORTANT]
> Debe ser un administrador global o tener asignado el rol de administrador de seguridad para el Centro de seguridad & cumplimiento para configurar la integración de SIEM con Microsoft Defender para Office 365.
>
> El registro de auditoría debe estar activado para el entorno de Microsoft 365. Para obtener ayuda con esto, vea Activar o desactivar la búsqueda [del registro de auditoría.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>Ver también

[Investigación y respuesta de amenazas de Office 365](office-365-ti.md)

[Investigación y respuesta automatizadas (AIR) en Office 365](automated-investigation-response-office.md)