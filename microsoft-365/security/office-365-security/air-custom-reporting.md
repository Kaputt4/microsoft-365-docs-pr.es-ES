---
title: Uso de soluciones de informes personalizadas con investigación y respuesta automatizadas
keywords: SIEM, API, AIR, autoIR, ATP, investigación automatizada, integración, informe personalizado
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Obtenga información sobre cómo integrar la investigación y la respuesta automatizadas con una solución de informes personalizada o de terceros.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 08502516ae03dc7c6e7b58aa77939723e7532ef0
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308925"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Usar la API de actividad de administración para soluciones de informes personalizadas o de terceros

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Con [Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), obtendrá [información detallada acerca de las investigaciones automatizadas](air-view-investigation-results.md). Sin embargo, algunas organizaciones también usan una solución de informes personalizada o de terceros. Si su organización desea integrar la información sobre las investigaciones automatizadas con una solución de este tipo, puede usar la API de actividad de administración de Office 365.

Use los siguientes recursos para configurar esto:

****

|Recurso|Descripción|
|---|---|
|[Información general de las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Microsoft 365 y Azure Active Directory.|
|[Introducción a las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|La API de administración 365 de Office usa Azure AD para proporcionar servicios de autenticación para que la aplicación tenga acceso a los datos 365 de Microsoft. Siga los pasos de este artículo para configurarlo.|
|[Referencia de las API de Actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Puede usar la API de actividad de administración de Office 365 para recuperar información sobre acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Microsoft 365 y Azure AD. Lea este artículo para obtener más información sobre cómo funciona.|
|[Esquema de la API de Actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Obtenga información general sobre el [esquema común](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) y el [esquema de investigación y respuesta de ATP y la investigación de amenazas de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para obtener información sobre los tipos de datos específicos disponibles a través de la API de actividad de administración de Office 365.|
|

## <a name="see-also"></a>Recursos adicionales

- [Microsoft defender para Office 365](office-365-atp.md)

- [Investigación y respuesta automatizadas en Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
