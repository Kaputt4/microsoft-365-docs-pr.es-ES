---
title: Integración de SIEM con Microsoft defender para Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integre el servidor SIEM de su organización con Microsoft defender para Office 365 y eventos relacionados con amenazas en la API de administración de actividad de Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 185e6e816cfff4131d7b5af11c4e3ea9cf94b338
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843581"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Integración de SIEM con Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Si su organización usa un servidor de administración de eventos e información de seguridad (SIEM), puede integrar Microsoft defender para Office 365 con su servidor de SIEM. Puede configurar esta integración mediante la [API de administración de actividad de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

La integración de SIEM permite ver información, como malware o phish detectada por Microsoft defender para Office 365, en los informes del servidor de SIEM. 

- Para ver un ejemplo de la integración de SIEM con Microsoft defender para Office 365, vea [blog de la comunidad tecnológica: mejorar la efectividad de su SOC con defender para office 365 y la API de administración de O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Para obtener más información acerca de las API de administración de Office 365, vea [información general sobre las API de administración de office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>Cómo funciona la integración de SIEM

La API de administración de actividad de Office 365 recupera información sobre acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Microsoft 365 y Azure Active Directory de su organización. Si su organización tiene Microsoft defender para Office 365 plan 1 o 2, o Office 365 E5, puede usar el [esquema de Microsoft defender para office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).  

Recientemente, se agregaron eventos de investigación automatizada y capacidades de respuesta en [Microsoft defender para office 365 plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) a la API de actividad de administración de Office 365. Además de incluir datos sobre los detalles de la investigación principal, como ID, Name y status, la API también contiene información de alto nivel sobre las acciones y entidades de investigación.

El servidor de SIEM o un sistema similar sondea la **auditoría.** carga de trabajo general para obtener acceso a los eventos de detección. Para obtener más información, vea Introducción [a las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). 

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Tipo: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

En la tabla siguiente se resumen los valores de **AuditLogRecordType** relevantes para los eventos 365 de Microsoft defender para Office:

|Valor|Nombre del miembro|Description|
|---|---|---|
|28|ThreatIntelligence|Eventos de suplantación de identidad y malware de Exchange Online Protection y Microsoft defender para Office 365.|
|41|ThreatIntelligenceUrl|Vínculos seguros eventos de invalidación de tiempo de bloqueo y bloqueo de Microsoft defender para Office 365.|
|47|ThreatIntelligenceAtpContent|Eventos de suplantación de identidad y malware para archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams, de Microsoft defender para Office 365.|
|64|AirInvestigation|Eventos de investigación y respuesta automatizados, como detalles de investigación y artefactos relevantes, de Microsoft defender para Office 365 plan 2.|
|

> [!IMPORTANT]
> Debe ser administrador global o tener asignado el rol de administrador de seguridad para el centro de seguridad & cumplimiento para configurar la integración de SIEM con Microsoft defender para Office 365.<br/>El registro de auditoría debe estar activado para su entorno de Microsoft 365. Para obtener ayuda, consulte [activar o desactivar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="see-also"></a>Recursos adicionales

[Investigación y respuesta de amenazas de Office 365](office-365-ti.md)

[Investigación y respuesta automatizadas (AIR) en Office 365](automated-investigation-response-office.md)

