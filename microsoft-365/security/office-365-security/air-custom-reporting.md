---
title: Soluciones de informes personalizadas con investigación y respuesta automatizadas
keywords: SIEM, API, AIR, autoIR, Microsoft Defender para punto de conexión, investigación automatizada, integración, informe personalizado
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- m365-security
- m365initiative-defender-office365
description: Obtenga información sobre cómo integrar la investigación y la respuesta automatizadas con una solución de informes personalizada o de terceros.
ms.date: 01/29/2021
ms.custom:
- air
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 3fa8841972a521515c6952116d25b8fb1654650f
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68084229"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Soluciones de informes personalizadas o de terceros para Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Con [Microsoft Defender para Office 365](defender-for-office-365.md), obtendrá [información detallada sobre las investigaciones automatizadas](air-view-investigation-results.md). Sin embargo, algunas organizaciones también usan una solución de informes personalizada o de terceros. Si su organización quiere integrar información sobre [investigaciones automatizadas](office-365-air.md) con dicha solución, puede usar la API de actividad de administración de Office 365.

Con [Microsoft Defender para Office 365](defender-for-office-365.md), obtendrá [información detallada sobre las investigaciones automatizadas](air-view-investigation-results.md). Sin embargo, algunas organizaciones también usan una solución de informes personalizada o de terceros. Si su organización quiere integrar información sobre investigaciones automatizadas con dicha solución, puede usar la API de actividad de administración de Office 365.

|Recurso|Descripción|
|:---|:---|
|[Información general de las API de administración de Office 365](/office/office-365-management-api/office-365-management-apis-overview)|La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Microsoft 365 y Azure Active Directory.|
|[Introducción a las API de administración de Office 365](/office/office-365-management-api/get-started-with-office-365-management-apis)|La API de administración de Office 365 usa Azure AD para proporcionar servicios de autenticación para que la aplicación acceda a los datos de Microsoft 365. Siga los pasos de este artículo para configurarlo.|
|[Referencia de las API de Actividad de administración de Office 365](/office/office-365-management-api/office-365-management-activity-api-reference)|Puede usar la API de actividad de administración de Office 365 para recuperar información sobre las acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Microsoft 365 y Azure AD. Lea este artículo para obtener más información sobre cómo funciona esto.|
|[Esquema de la API de Actividad de administración de Office 365](/office/office-365-management-api/office-365-management-activity-api-schema)|Obtenga información general sobre el [esquema común](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) y el esquema de [investigación y respuesta de Defender para Office 365 y amenazas](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para obtener información sobre tipos específicos de datos disponibles a través de la API de actividad de administración de Office 365.|

## <a name="see-also"></a>Vea también

- [Microsoft Defender para Office 365](defender-for-office-365.md)
- [Investigación y respuesta automatizadas en Microsoft 365 Defender](/microsoft-365/security/defender/m365d-autoir)
