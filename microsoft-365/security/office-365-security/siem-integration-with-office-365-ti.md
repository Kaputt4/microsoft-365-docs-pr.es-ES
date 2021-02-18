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
description: Integre el servidor SIEM de su organización con Microsoft Defender para Office 365 y los eventos de amenazas relacionados en la API de administración de actividad de Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f637750a31b5034d2ee1110ab0070fa6abcda49b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290398"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Integración de SIEM con Microsoft Defender para Office 365

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Si su organización usa un servidor de administración de eventos e información de seguridad (SIEM), puede integrar Microsoft Defender para Office 365 con el servidor SIEM. Puede configurar esta integración con la API de administración de actividad [de Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

La integración de SIEM le permite ver información, como malware o phishing detectado por Microsoft Defender para Office 365, en los informes del servidor SIEM.

- Para ver un ejemplo de integración de SIEM con Microsoft Defender para Office 365, vea el blog de Tech Community: Mejorar la eficacia de los SOC con Defender para Office 365 y la API de administración de [O365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

- Para obtener más información sobre las API de administración de Office 365, vea información general sobre las API de [administración de Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>Funcionamiento de la integración de SIEM

La API de administración de actividad de Office 365 recupera información sobre acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Microsoft 365 y Azure Active Directory de su organización. Si su organización tiene Microsoft Defender para Office 365 Plan 1 o 2, u Office 365 E5, puede usar el esquema de Microsoft Defender para [Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)

Recientemente, se agregaron eventos de investigación automatizada y capacidades de respuesta en Microsoft Defender para [Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) a la API de actividad de administración de Office 365. Además de incluir datos sobre detalles principales de la investigación, como id., nombre y estado, la API también contiene información de alto nivel sobre las acciones y entidades de investigación.

El servidor SIEM u otro sistema similar sondea la carga de **trabajo audit.general** para obtener acceso a eventos de detección. Para obtener más información, vea Introducción a las API de administración [de Office 365.](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Tipo: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

En la tabla siguiente se resumen los valores **de AuditLogRecordType** que son relevantes para los eventos de Microsoft Defender para Office 365:

|Valor|Nombre del miembro|Descripción|
|---|---|---|
|28|ThreatIntelligence|Eventos de suplantación de identidad y malware de Exchange Online Protection y Microsoft Defender para Office 365.|
|41|ThreatIntelligenceUrl|Eventos de tiempo de bloqueo y bloqueo de Vínculos seguros de Microsoft Defender para Office 365.|
|47|ThreatIntelligenceAtpContent|Eventos de suplantación de identidad (phishing) y malware para archivos en SharePoint Online, OneDrive para la Empresa y Microsoft Teams desde Microsoft Defender para Office 365.|
|64|AirInvestigation|Eventos de investigación y respuesta automatizados, como detalles de investigación y artefactos relevantes, de Microsoft Defender para Office 365 Plan 2.|
|

> [!IMPORTANT]
> Debe ser administrador global o tener asignado el rol de administrador de seguridad para el Centro de seguridad & Cumplimiento para configurar la integración de SIEM con Microsoft Defender para Office 365.
>
> El registro de auditoría debe estar activado para su entorno de Microsoft 365. Para obtener ayuda con esto, vea Activar o desactivar la búsqueda [del registro de auditoría.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>Vea también

[Investigación y respuesta de amenazas de Office 365](office-365-ti.md)

[Investigación y respuesta automatizada (AIR) en Office 365](automated-investigation-response-office.md)

