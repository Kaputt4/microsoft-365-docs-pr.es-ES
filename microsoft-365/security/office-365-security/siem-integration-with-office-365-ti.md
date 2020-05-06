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
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: Integre el servidor de SIEM de su organización con la protección contra amenazas avanzada de Office 365 y eventos de amenazas relacionados en la API de administración de actividad de Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0527a998e7049960df840c7756ef5deaafaf5ade
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035277"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>Integración de SIEM con la protección contra amenazas avanzada

Si su organización usa un servidor de incidentes de seguridad y de administración de eventos (SIEM), puede integrar la protección contra amenazas avanzada de Office 365 con el servidor de SIEM. La integración de SIEM permite ver información, como malware o phish detectada por la protección avanzada de Office 365, en los informes del servidor de SIEM. Para configurar la integración de SIEM, use la [API de administración de actividad de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

La API de administración de actividad de Office 365 recupera información sobre acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Microsoft 365 para empresas y Azure Active Directory de su organización. El [esquema de protección contra amenazas avanzada de office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) funciona con la protección contra amenazas avanzada, de modo que si su organización tiene el plan 1 de la protección contra amenazas avanzada de Office 365 o bien el plan 2 u Office 365 E5, puede usar esa misma API para la integración del servidor de Siem. 

Como parte de nuestras actualizaciones recientes, también hemos agregado eventos de las capacidades de investigación y respuesta automatizadas en Office 365 ATP plan 2 dentro de la API de actividad de administración de Office 365. Además de incluir datos sobre los detalles de la investigación principal, como ID, Name y status, también contiene información de alto nivel sobre las acciones y entidades de investigación.   

El servidor de SIEM u otro sistema similar debe sondear la **auditoría. general** Workload para acceder a los eventos de detección. Para obtener más información, vea Introducción [a las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). Además, los siguientes valores de **AuditLogRecordType** son relevantes para los eventos de ATP de Office 365:

### <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Tipo: Edm.Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

|Valor|Nombre del miembro|Descripción|
|:-----|:-----|:-----|
|28|ThreatIntelligence|Eventos de suplantación de identidad y malware de Exchange Online Protection y Protección contra amenazas avanzada de Office 365.|
|41|ThreatIntelligenceUrl|Vínculos seguros ATP tiempo de bloqueo y bloqueo de eventos de invalidación de la protección contra amenazas avanzada de Office 365.|
|47|ThreatIntelligenceAtpContent|Eventos de suplantación de identidad y malware para archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams de la protección contra amenazas avanzada de Office 365.|
|64|AirInvestigation|Investigación automatizada y eventos de respuesta, como detalles de investigación y artefactos relevantes del plan 2 de protección contra amenazas avanzada de Office 365.|


> [!IMPORTANT]
> Debe ser administrador global o tener asignado el rol de administrador de seguridad para el centro de seguridad & cumplimiento para configurar la integración de SIEM con la protección contra amenazas avanzada de Office 365.<br/>El registro de auditoría debe estar activado para su entorno de Microsoft 365. Para obtener ayuda, consulte [activar o desactivar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Temas relacionados

[Investigación y respuesta de amenazas de Office 365](office-365-ti.md)

[Investigación y respuesta automatizadas (AIR) en Office 365](automated-investigation-response-office.md)

[Protección contra amenazas avanzada de Office 365](office-365-atp.md)

[Informes inteligentes y opiniones del centro de seguridad &amp; y cumplimiento](reports-and-insights-in-security-and-compliance.md)
  
[Permisos en el centro &amp; de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md)
  
