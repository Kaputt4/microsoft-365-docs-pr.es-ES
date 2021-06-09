---
title: Tabla AADSignInEventsBeta en el esquema de búsqueda avanzada
description: Obtenga información sobre la información asociada Azure Active Directory de eventos de inicio de sesión del esquema de búsqueda avanzado
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, archivo, dirección IP, dispositivo, máquina, usuario, cuenta, identidad, AAD
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 704752951c453a3fe872b814e7364ef1699226bf
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582985"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Se aplica a:**

- Microsoft 365 Defender

>[!IMPORTANT]
> La tabla está actualmente en versión beta y se ofrece a corto plazo para permitirle buscar a través de eventos de inicio de sesión Azure Active Directory `AADSignInEventsBeta` (AAD). Con el tiempo, moveremos toda la información del esquema de inicio de sesión a la `IdentityLogonEvents` tabla.

 

La tabla del esquema de búsqueda avanzada contiene información sobre Azure Active Directory inicios de sesión interactivos y no `AADSignInEventsBeta` interactivos. Obtenga más información sobre los inicios de sesión en Azure Active Directory de actividad de inicio [de sesión - versión preliminar](/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Use esta referencia para crear consultas que devuelvan información de la tabla.
Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

 

 

| Nombre de columna                 | Tipo de datos | Descripción          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | datetime      | Fecha y hora en que se generó el registro                                                                                                                                         |
| `Application`                     | cadena        | Aplicación que realizó la acción grabada                                                                                                                                       |
| `ApplicationId`                   | cadena        | Identificador único de la aplicación                                                                                                                                               |
| `LogonType`                       | cadena        | Tipo de sesión de inicio de sesión, específicamente interactiva, interactiva remota (RDP), red, lote y servicio                                                                              |
| `ErrorCode`                       | Entero        | Contiene el código de error si se produce un error de inicio de sesión. Para encontrar una descripción de un código de error específico, visite <https://aka.ms/AADsigninsErrorCodes> .                                     |
| `CorrelationId`                   | cadena        | Identificador único del evento de inicio de sesión                                                                                                                                              |
| `SessionId`                       | cadena        | Número único asignado a un usuario por el servidor de un sitio web durante la visita o la sesión                                                                                     |
| `AccountDisplayName`              | cadena        | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre o un nombre determinado, una inicial central y un apellido o apellido.                             |
| `AccountObjectId`                 | cadena        | Identificador único de la cuenta en Azure AD                                                                                                                                       |
| `AccountUpn`                      | cadena        | Nombre principal de usuario (UPN) de la cuenta                                                                                                                                            |
| `IsExternalUser`                  | Entero        | Indica si el usuario que ha iniciado sesión es externo. Valores posibles: -1 (no establecido), 0 (no externo), 1 (externo).                                                                   |
| `IsGuestUser`                     | boolean       | Indica si el usuario que ha iniciado sesión es un invitado en el inquilino                                                                                                                  |
| `AlternateSignInName`             | cadena        | Nombre principal de usuario local (UPN) del usuario que inicia sesión en Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | datetime        | Fecha y hora en que el usuario que ha iniciado sesión ha cambiado por última vez su contraseña                                                                                                              |
| `ResourceDisplayName`             | cadena        | Nombre para mostrar del recurso al que se ha accedido                                                                                                                                               |
| `ResourceId`                      | cadena        | Identificador único del recurso al que se ha accedido                                                                                                                                          |
| `ResourceTenantId`                | cadena        | Identificador único del inquilino del recurso al que se ha accedido                                                                                                                            |
| `DeviceName`                      | cadena        | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo                                                                                                                                   |
| `AadDeviceId`                     | cadena   |      Identificador único del dispositivo en Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | cadena        | Plataforma del sistema operativo que se ejecuta en el equipo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.  |
| `DeviceTrustType`                 | cadena        | Indica el tipo de confianza del dispositivo que ha iniciado sesión. Solo para escenarios de dispositivos administrados. Los valores posibles son Workplace, AzureAd y ServerAd.                                     |
| `IsManaged`                       | Entero       | Indica si el dispositivo que inició el inicio de sesión es un dispositivo administrado (1) o no un dispositivo administrado (0)                                                                         |
| `IsCompliant`                     | Entero       | Indica si el dispositivo que inició el inicio de sesión es compatible (1) o no es compatible (0)                                                                                       |
| `AuthenticationProcessingDetails` | cadena        | Detalles sobre el procesador de autenticación                                                                                                                                          |
| `AuthenticationRequirement`       | cadena        | Tipo de autenticación necesaria para el inicio de sesión. Valores posibles: multiFactorAuthentication (se requería MFA) y singleFactorAuthentication (no se requería MFA).                |
| `TokenIssuerType`                 | Entero        | Indica si el emisor de tokens Azure Active Directory (0) o servicios de federación de Active Directory (1)                                                                             |
| `RiskLevelAggregated`                       | Entero        | Nivel de riesgo agregado durante el inicio de sesión. Valores posibles: 0 (nivel de riesgo agregado no establecido), 1 (ninguno), 10 (bajo), 50 (medio) o 100 (alto).                               |
| `RiskDetails`                      | Entero        | Detalles sobre el estado de riesgo del usuario que ha iniciado sesión                                                                                                                            |
| `RiskState`                       | Entero        | Indica el estado de usuario arriesgado. Valores posibles: 0 (ninguno), 1 (confirmado seguro), 2 (corregido), 3 (descartado), 4 (en riesgo) o 5 (confirmado en peligro).                                |
| `UserAgent`                       | cadena        | Información del agente de usuario desde el explorador web u otra aplicación cliente                                                                                                             |
| `ClientAppUsed`                   | cadena        | Indica la aplicación cliente usada                                                                                                                                                       |
| `Browser`                         | cadena        | Detalles sobre la versión del explorador que se usa para iniciar sesión                                                                                                                            |
| `ConditionalAccessPolicies`       | cadena        | Detalles de las directivas de acceso condicional aplicadas al evento de inicio de sesión                                                                                                             |
| `ConditionalAccessStatus`         | Entero        | Estado de las directivas de acceso condicional aplicadas al inicio de sesión. Los valores posibles son 0 (directivas aplicadas), 1 (error al intentar aplicar directivas) o 2 (directivas no aplicadas).      |
| `IPAddress`                       | cadena        | Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas                                                                                                  |
| `Country`                     | cadena        | Código de dos letras que indica el país donde se geolocalización de la dirección IP del cliente                                                                                                    |
| `State`                           | cadena        | Estado en el que se produjo el inicio de sesión, si está disponible                                                                                                                                      |
| `City`                            | cadena        | Ciudad donde se encuentra el usuario de la cuenta                                                                                                                                              |
| `Latitude`                        | cadena        | Las coordenadas de norte a sur de la ubicación de inicio de sesión                                                                                                                              |
| `Longitude`                       | cadena        | Las coordenadas de este a oeste de la ubicación de inicio de sesión                                                                                                                                |
| `NetworkLocationDetails`          | cadena        | Detalles de ubicación de red del procesador de autenticación del evento de inicio de sesión                                                                                                       |
| `RequestId`                       | cadena        |  Identificador único de la solicitud                                                                                                                                                   |
|`ReportId` | cadena | Identificador único del evento |

 

 

## <a name="related-articles"></a>Artículos relacionados

-   [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
-   [Información general sobre la búsqueda avanzada de amenazas](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Aprender el lenguaje de consulta](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Entender el esquema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 