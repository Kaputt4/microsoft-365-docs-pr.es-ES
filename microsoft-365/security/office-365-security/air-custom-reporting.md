---
title: Soluciones de informes personalizadas con investigación y respuesta automatizadas
keywords: SIEM, API, AIR, autoIR, ATP, investigación automatizada, integración, informe personalizado
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
description: Obtenga información sobre cómo integrar la investigación automatizada y la respuesta con una solución de informes personalizada o de terceros.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a66a89a13182570259bcb8be4134c21d13e22391
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175816"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Soluciones de informes personalizadas o de terceros para Microsoft Defender para Office 365

Con [Microsoft Defender para Office 365,](office-365-atp.md)obtiene información detallada sobre las [investigaciones automatizadas.](air-view-investigation-results.md) Sin embargo, algunas organizaciones también usan una solución de informes personalizada o de terceros. Si su organización desea integrar información sobre investigaciones [automatizadas](office-365-air.md) con dicha solución, puede usar la API de actividad de administración de Office 365.

**Se aplica a**
- [Microsoft Defender para Office 365 plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Con [Microsoft Defender para Office 365,](office-365-atp.md)obtiene información detallada sobre las [investigaciones automatizadas.](air-view-investigation-results.md) Sin embargo, algunas organizaciones también usan una solución de informes personalizada o de terceros. Si su organización desea integrar información sobre investigaciones automatizadas con dicha solución, puede usar la API de actividad de administración de Office 365.

|Recurso|Descripción|
|:---|:---|
|[Información general de las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Microsoft 365 y Azure Active Directory.|
|[Introducción a las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|La API de administración de Office 365 usa Azure AD para proporcionar servicios de autenticación para que la aplicación acceda a los datos de Microsoft 365. Siga los pasos de este artículo para configurarlo.|
|[Referencia de las API de Actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Puede usar la API de actividad de administración de Office 365 para recuperar información sobre acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Microsoft 365 y Azure AD. Lea este artículo para obtener más información sobre cómo funciona.|
|[Esquema de la API de Actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Obtenga información general [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) sobre el esquema común y Defender para [Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) y el esquema de investigación y respuesta de amenazas para obtener información sobre tipos específicos de datos disponibles a través de la API de actividad de administración de Office 365.|
|

## <a name="see-also"></a>Recursos adicionales

- [Microsoft Defender para Office 365](office-365-atp.md)
- [Investigación y respuesta automatizadas en Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
