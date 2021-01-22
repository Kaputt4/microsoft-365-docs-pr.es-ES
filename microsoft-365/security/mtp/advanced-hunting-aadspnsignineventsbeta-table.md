---
title: Tabla AADSpnSignInEventsBeta en el esquema de búsqueda avanzada
description: Obtenga información sobre la información asociada con la entidad de servicio de Azure Active Directory y la tabla de eventos de inicio de sesión de identidad administrada del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, entidades, evidencia, archivo, dirección IP, dispositivo, máquina, usuario, cuenta, identidad, AAD
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 172c400df3adea70a2e2d2e37547fa39e0d3b9cf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928623"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Se aplica a:**

- Microsoft 365 Defender

>[!IMPORTANT]
> La tabla se encuentra actualmente en versión beta y se ofrece a corto plazo para permitirle buscar a través de eventos de inicio de sesión de identidad administrada y entidad de servicio de `AADSpnSignInEventsBeta` Azure Active Directory (AAD). Con el tiempo, moveremos toda la información del esquema de inicio de sesión a la `IdentityLogonEvents` tabla.<br><br>
> Los clientes que pueden acceder a Microsoft 365 Defender a través de la solución integrada de Microsoft Defender para Endpoint del Centro de seguridad de Azure, pero que no tienen licencias para Microsoft Defender para Office, Microsoft Defender para Identity o Microsoft Cloud App Security, no podrán ver este esquema. 



La tabla del esquema de búsqueda avanzada contiene información sobre la entidad de servicio de Azure Active Directory y los inicios de sesión de `AADSpnSignInEventsBeta` identidad administrada. Puede obtener más información sobre los diferentes tipos de inicios de sesión en los informes de actividad de inicio de sesión [de Azure Active Directory : versión preliminar.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Nombre de columna     | Tipo de datos | Descripción   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | Fecha y hora en que se generó el registro                                                                                                     |
| `Application`          | cadena        | Aplicación que realizó la acción grabada                                                                                                   |
| `ApplicationId`        | string        | Identificador único de la aplicación                                                                                                           |
| `IsManagedIdentity`    | boolean       | Indica si el inicio de sesión se inició mediante una identidad administrada                                                                               |
| `ErrorCode`            | entero        | Contiene el código de error si se produce un error de inicio de sesión. Para encontrar una descripción de un código de error específico, visite <https://aka.ms/AADsigninsErrorCodes> . |
| `CorrelationId`        | string        | Identificador único del evento de inicio de sesión                                                                                                          |
| `ServicePrincipalName` | string        | Nombre de la entidad de servicio que inició el inicio de sesión                                                                                        |
| `ServicePrincipalId`   | string        | Identificador único de la entidad de servicio que inició el inicio de sesión                                                                           |
| `ResourceDisplayName`  | string        | Nombre para mostrar del recurso al que se ha accedido                                                                                                           |
| `ResourceId`           | string        | Identificador único del recurso al que se ha accedido                                                                                                      |
| `ResourceTenantId`     | string        | Identificador único del inquilino del recurso al que se ha accedido                                                                                        |
| `IPAddress`            | string        | Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas                                                              |
| `CountryCode`          | string        | Código de dos letras que indica el país en el que se geolocalización la dirección IP del cliente                                                                |
| `State`                | string        | Estado donde se produjo el inicio de sesión, si está disponible                                                                                                  |
| `City`                 | string        | Ciudad donde se encuentra el usuario de la cuenta                                                                                                          |
| `Latitude`             | string        | Coordenadas de norte a sur de la ubicación de inicio de sesión                                                                                          |
| `Longitude`            | string        | Coordenadas de este a oeste de la ubicación de inicio de sesión                                                                                            |
| `RequestId`            | string        | Identificador único de la solicitud                                                                                                                |
|`ReportId` | string | Identificador único del evento | 

 

## <a name="related-articles"></a>Artículos relacionados

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [Información general sobre la búsqueda avanzada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Aprender el lenguaje de consulta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Entender el esquema](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

