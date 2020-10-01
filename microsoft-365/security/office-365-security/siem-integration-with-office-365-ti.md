---
title: Integración de SIEM con la protección contra amenazas avanzada
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
description: Integre el servidor de SIEM de su organización con la protección contra amenazas avanzada de Office 365 y eventos de amenazas relacionados en la API de administración de actividad de Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 544093960570fe0e68ac47dc7bf9965fba2d30a1
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327170"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>Integración de SIEM con la protección contra amenazas avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Si su organización usa un servidor de incidentes de seguridad y de administración de eventos (SIEM), puede integrar Office 365 Advanced Threat Protection (Office 365 ATP) con su servidor de SIEM. Puede configurar esta integración mediante la [API de administración de actividad de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

La integración de SIEM permite ver información, como malware o phish detectada por Office 365 ATP, en los informes del servidor de SIEM. 

- Para ver un ejemplo de la integración de SIEM con Office 365 ATP, vea [blog de la comunidad tecnológica: mejorar la efectividad de su SOC con office 365 ATP y la API de administración de O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Para obtener más información acerca de las API de administración de Office 365, vea [información general sobre las API de administración de office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>Cómo funciona la integración de SIEM

La API de administración de actividad de Office 365 recupera información sobre acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Microsoft 365 y Azure Active Directory de su organización. Si su organización tiene Office 365 ATP plan 1 o 2, o Office 365 E5, puede usar el [esquema ATP de office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).  

Recientemente, los eventos de las capacidades automatizadas de investigación y respuesta en [office 365 ATP plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) se agregaron a la API de actividad de administración de Office 365. Además de incluir datos sobre los detalles de la investigación principal, como ID, Name y status, la API también contiene información de alto nivel sobre las acciones y entidades de investigación.

El servidor de SIEM o un sistema similar sondea la **auditoría.** carga de trabajo general para obtener acceso a los eventos de detección. Para obtener más información, vea Introducción [a las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). 

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Tipo: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

En la siguiente tabla se resumen los valores de **AuditLogRecordType** relevantes para los eventos de ATP de Office 365:

|Valor|Nombre del miembro|Description|
|---|---|---|
|28|ThreatIntelligence|Eventos de suplantación de identidad y malware de Exchange Online Protection y Office 365 ATP.|
|41|ThreatIntelligenceUrl|Vínculos seguros eventos de invalidación de tiempo de bloqueo y bloqueo de la ATP de Office 365.|
|47|ThreatIntelligenceAtpContent|Eventos de suplantación de identidad y malware para archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams desde Office 365 ATP.|
|64|AirInvestigation|Investigación automatizada y eventos de respuesta, como detalles de investigación y artefactos relevantes, de Office 365 ATP plan 2.|
|

> [!IMPORTANT]
> Debe ser administrador global o tener asignado el rol de administrador de seguridad para el centro de seguridad & cumplimiento para configurar la integración de SIEM con la protección contra amenazas avanzada de Office 365.<br/>El registro de auditoría debe estar activado para su entorno de Microsoft 365. Para obtener ayuda, consulte [activar o desactivar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="see-also"></a>Vea también

[Investigación y respuesta de amenazas de Office 365](office-365-ti.md)

[Investigación y respuesta automatizadas (AIR) en Office 365](automated-investigation-response-office.md)


