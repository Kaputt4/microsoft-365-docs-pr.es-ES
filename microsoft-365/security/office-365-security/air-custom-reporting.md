---
title: Soluciones de informes personalizadas con investigación y respuesta automatizadas
keywords: SIEM, API, AIR, autoIR, Microsoft Defender para endpoint, investigación automatizada, integración, informe personalizado
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Obtenga información sobre cómo integrar la investigación y la respuesta automatizadas con una solución de informes personalizada o de terceros.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ed752f9514f1d2c8cadeb7cbbd1d7b9311b1b5f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275017"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Soluciones de informes personalizadas o de terceros para Microsoft Defender para Office 365

Con [Microsoft Defender para Office 365,](defender-for-office-365.md)obtiene información detallada acerca de las [investigaciones automatizadas.](air-view-investigation-results.md) Sin embargo, algunas organizaciones también usan una solución de informes personalizada o de terceros. Si su organización desea integrar información sobre [investigaciones automatizadas](office-365-air.md) con dicha solución, puede usar la API de actividad Office 365 administración.

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Con [Microsoft Defender para Office 365,](defender-for-office-365.md)obtiene información detallada acerca de las [investigaciones automatizadas.](air-view-investigation-results.md) Sin embargo, algunas organizaciones también usan una solución de informes personalizada o de terceros. Si su organización desea integrar información acerca de las investigaciones automatizadas con dicha solución, puede usar la API de Office 365 actividad de administración.

|Recurso|Descripción|
|:---|:---|
|[Información general de las API de administración de Office 365](/office/office-365-management-api/office-365-management-apis-overview)|La API Office 365 actividad de administración proporciona información sobre diversos eventos y acciones de usuario, administrador, sistema y directiva de Microsoft 365 y Azure Active Directory de actividad.|
|[Introducción a las API de administración de Office 365](/office/office-365-management-api/get-started-with-office-365-management-apis)|La API Office 365 management usa Azure AD para proporcionar servicios de autenticación para que la aplicación obtenga acceso a Microsoft 365 datos. Siga los pasos de este artículo para configurar esto.|
|[Referencia de las API de Actividad de administración de Office 365](/office/office-365-management-api/office-365-management-activity-api-reference)|Puede usar la API de Office 365 actividad de administración para recuperar información sobre acciones y eventos de usuario, administrador, sistema y directiva de Microsoft 365 y registros de actividad de Azure AD. Lea este artículo para obtener más información sobre cómo funciona.|
|[Esquema de la API de Actividad de administración de Office 365](/office/office-365-management-api/office-365-management-activity-api-schema)|Obtenga información general sobre el [esquema común](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) y el esquema de investigación y respuesta de defender para [Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) y amenazas para obtener información sobre tipos específicos de datos disponibles a través de la API de actividad de administración Office 365 administración.|
|

## <a name="see-also"></a>Vea también

- [Microsoft Defender para Office 365](defender-for-office-365.md)
- [Investigación y respuesta automatizadas en Microsoft 365 Defender](/microsoft-365/security/defender/m365d-autoir)
