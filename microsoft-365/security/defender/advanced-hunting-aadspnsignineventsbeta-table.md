---
title: Tabla AADSpnSignInEventsBeta en el esquema de búsqueda avanzada
description: Obtenga información sobre la información asociada a la entidad de servicio de Azure Active Directory y a la tabla de eventos de inicio de sesión de identidad administrada.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.openlocfilehash: d24a67f6323e0f556e25021470d808b2fc67d918
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68637054"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Se aplica a:**
- Microsoft 365 Defender

> [!IMPORTANT]
> La `AADSpnSignInEventsBeta` tabla está actualmente en versión beta y se ofrece a corto plazo para permitirle buscar a través de eventos de inicio de sesión de Azure Active Directory (AAD). Los clientes deben tener una licencia de Azure Active Directory Premium P2 para recopilar y ver las actividades de esta tabla. Con el tiempo, Microsoft moverá toda la información del esquema de inicio de sesión a la `IdentityLogonEvents` tabla.

La `AADSpnSignInEventsBeta` tabla del esquema de búsqueda avanzada contiene información sobre la entidad de servicio de Azure Active Directory y los inicios de sesión de identidad administrada. Puede obtener más información sobre los distintos tipos de inicios de sesión en [informes de actividad de inicio de sesión de Azure Active Directory: versión preliminar](/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

<br>

****

|Nombre de columna|Tipo de datos|Descripción|
|---|---|---|
|`Timestamp`|`datetime`|Fecha y hora en que se generó el registro|
|`Application`|`string`|Aplicación que realizó la acción registrada|
|`ApplicationId`|`string`|Identificador único de la aplicación|
|`IsManagedIdentity`|`boolean`|Indica si una identidad administrada inició el inicio de sesión.|
|`ErrorCode`|`int`|Contiene el código de error si se produce un error de inicio de sesión. Para encontrar una descripción de un código de error específico, visite <https://aka.ms/AADsigninsErrorCodes>.|
|`CorrelationId`|`string`|Identificador único del evento de inicio de sesión|
|`ServicePrincipalName`|`string`|Nombre de la entidad de servicio que inició el inicio de sesión|
|`ServicePrincipalId`|`string`|Identificador único de la entidad de servicio que inició el inicio de sesión|
|`ResourceDisplayName`|`string`|Nombre para mostrar del recurso al que se accede|
|`ResourceId`|`string`|Identificador único del recurso al que se accede|
|`ResourceTenantId`|`string`|Identificador único del inquilino del recurso al que se accede|
|`IPAddress`|`string`|Dirección IP asignada al punto de conexión y usada durante las comunicaciones de red relacionadas|
|`Country`|`string`|Código de dos letras que indica el país donde la dirección IP del cliente está geolocalizada|
|`State`|`string`|Estado en el que se produjo el inicio de sesión, si está disponible|
|`City`|`string`|Ciudad donde se encuentra el usuario de la cuenta|
|`Latitude`|`string`|Coordenadas de norte a sur de la ubicación de inicio de sesión|
|`Longitude`|`string`|Coordenadas de este a oeste de la ubicación de inicio de sesión|
|`RequestId`|`string`|Identificador único de la solicitud|
|`ReportId`|`string`|Identificador único del evento|
||||

## <a name="related-articles"></a>Artículos relacionados

- [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
- [Información general sobre la búsqueda avanzada de amenazas](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Aprender el lenguaje de consulta](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [Entender el esquema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
