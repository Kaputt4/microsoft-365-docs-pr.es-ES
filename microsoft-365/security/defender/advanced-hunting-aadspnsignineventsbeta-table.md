---
title: Tabla AADSpnSignInEventsBeta en el esquema de búsqueda avanzada
description: Obtenga información sobre la información asociada con la entidad de Azure Active Directory de servicio y la tabla de eventos de inicio de sesión de identidad administrada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, entidades, evidencia, archivo, dirección IP, dispositivo, máquina, usuario, cuenta, identidad, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6d9c0c215d37458eab1deaf19f5818f07c1a9f3a
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531500"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Se aplica a:**
- Microsoft 365 Defender

> [!IMPORTANT]
> La tabla está actualmente en versión beta y se ofrece a corto plazo para permitirle buscar a través de Azure Active Directory `AADSpnSignInEventsBeta` (AAD) eventos de inicio de sesión. Los clientes necesitan tener una Azure Active Directory Premium P2 para recopilar y ver las actividades de esta tabla. Microsoft finalmente moverá toda la información del esquema de inicio de sesión a la `IdentityLogonEvents` tabla.

La tabla del esquema de búsqueda avanzada contiene información sobre Azure Active Directory principal de servicio y los `AADSpnSignInEventsBeta` inicios de sesión de identidad administrada. Puede obtener más información sobre los diferentes tipos de inicios de sesión en Azure Active Directory de actividad de inicio de sesión [- versión preliminar](/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

<br>

****

|Nombre de columna|Tipo de datos|Description|
|---|---|---|
|`Timestamp`|`datetime`|Fecha y hora en que se generó el registro|
|`Application`|`string`|Aplicación que realizó la acción grabada|
|`ApplicationId`|`string`|Identificador único de la aplicación|
|`IsManagedIdentity`|`boolean`|Indica si el inicio de sesión se inició mediante una identidad administrada|
|`ErrorCode`|`int`|Contiene el código de error si se produce un error de inicio de sesión. Para encontrar una descripción de un código de error específico, visite <https://aka.ms/AADsigninsErrorCodes> .|
|`CorrelationId`|`string`|Identificador único del evento de inicio de sesión|
|`ServicePrincipalName`|`string`|Nombre de la entidad de servicio que inició el inicio de sesión|
|`ServicePrincipalId`|`string`|Identificador único de la entidad de servicio que inició el inicio de sesión|
|`ResourceDisplayName`|`string`|Nombre para mostrar del recurso al que se ha accedido|
|`ResourceId`|`string`|Identificador único del recurso al que se ha accedido|
|`ResourceTenantId`|`string`|Identificador único del inquilino del recurso al que se ha accedido|
|`IPAddress`|`string`|Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas|
|`Country`|`string`|Código de dos letras que indica el país donde se geolocalización de la dirección IP del cliente|
|`State`|`string`|Estado en el que se produjo el inicio de sesión, si está disponible|
|`City`|`string`|Ciudad donde se encuentra el usuario de la cuenta|
|`Latitude`|`string`|Las coordenadas de norte a sur de la ubicación de inicio de sesión|
|`Longitude`|`string`|Las coordenadas de este a oeste de la ubicación de inicio de sesión|
|`RequestId`|`string`|Identificador único de la solicitud|
|`ReportId`|`string`|Identificador único del evento|
||||

## <a name="related-articles"></a>Artículos relacionados

- [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
- [Información general sobre la búsqueda avanzada de amenazas](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Aprender el lenguaje de consulta](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [Entender el esquema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
