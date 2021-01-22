---
title: Tabla AADSignInEventsBeta en el esquema de búsqueda avanzada
description: Obtenga información sobre la información asociada con la tabla de eventos de inicio de sesión de Azure Active Directory del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, archivo, dirección IP, dispositivo, máquina, usuario, cuenta, identidad, AAD
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
ms.openlocfilehash: b574717d0ba5621d85c8e73f36ddc72b062a1494
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931043"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Se aplica a:**

- Microsoft 365 Defender

>[!IMPORTANT]
> La tabla está actualmente en versión beta y se ofrece a corto plazo para permitirle buscar eventos de inicio de sesión de `AADSignInEventsBeta` Azure Active Directory (AAD). Con el tiempo, moveremos toda la información del esquema de inicio de sesión a la `IdentityLogonEvents` tabla.<br><br>
> Los clientes que pueden acceder a Microsoft 365 Defender a través de la solución integrada de Microsoft Defender para endpoint del Centro de seguridad de Azure, pero que no tienen licencias para Microsoft Defender para Office, Microsoft Defender para Identity o Microsoft Cloud App Security, no podrán ver este esquema. 

 

La tabla del esquema de búsqueda avanzada contiene información sobre los inicios de sesión interactivos y no `AADSignInEventsBeta` interactivos de Azure Active Directory. Obtenga más información sobre los inicios de sesión en los informes de actividad de inicio de [sesión de Azure Active Directory : versión preliminar.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Use esta referencia para crear consultas que devuelvan información de la tabla.
Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

 

 

| Nombre de columna                 | Tipo de datos | Descripción          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | datetime      | Fecha y hora en que se generó el registro                                                                                                                                         |
| `Application`                     | cadena        | Aplicación que realizó la acción grabada                                                                                                                                       |
| `ApplicationId`                   | string        | Identificador único de la aplicación                                                                                                                                               |
| `LogonType`                       | string        | Tipo de sesión, específicamente interactiva, interactiva remota (RDP), red, lote y servicio                                                                              |
| `ErrorCode`                       | entero        | Contiene el código de error si se produce un error de inicio de sesión. Para encontrar una descripción de un código de error específico, visite <https://aka.ms/AADsigninsErrorCodes> .                                     |
| `CorrelationId`                   | string        | Identificador único del evento de inicio de sesión                                                                                                                                              |
| `SessionId`                       | string        | Número único asignado a un usuario por el servidor de un sitio web durante la visita o sesión                                                                                     |
| `AccountDisplayName`              | string        | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre o nombre, una inicial intermedia y un apellido o apellido.                             |
| `AccountObjectId`                 | string        | Identificador único de la cuenta en Azure AD                                                                                                                                       |
| `AccountUpn`                      | string        | Nombre principal de usuario (UPN) de la cuenta                                                                                                                                            |
| `IsExternalUser`                  | entero        | Indica si el usuario que ha iniciado sesión es externo. Valores posibles: -1 (no establecido), 0 (no externo), 1 (externo).                                                                   |
| `IsGuestUser`                     | boolean       | Indica si el usuario que ha iniciado sesión es un invitado en el espacio empresarial.                                                                                                                  |
| `AlternateSignInName`             | string        | Nombre principal de usuario local (UPN) del usuario que inicia sesión en Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | datetime        | Fecha y hora en que el usuario que ha iniciado sesión ha cambiado su contraseña por última vez                                                                                                              |
| `ResourceDisplayName`             | string        | Nombre para mostrar del recurso al que se ha accedido                                                                                                                                               |
| `ResourceId`                      | string        | Identificador único del recurso al que se ha accedido                                                                                                                                          |
| `ResourceTenantId`                | string        | Identificador único del inquilino del recurso al que se ha accedido                                                                                                                            |
| `DeviceName`                      | cadena        | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo                                                                                                                                   |
| `AadDeviceId`                     | cadena   |      Identificador único del dispositivo en Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | cadena        | Plataforma del sistema operativo que se ejecuta en el equipo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.  |
| `DeviceTrustType`                 | cadena        | Indica el tipo de confianza del dispositivo que ha iniciado sesión. Solo para escenarios de dispositivos administrados. Los valores posibles son Workplace, AzureAd y ServerAd.                                     |
| `IsManaged`                       | entero       | Indica si el dispositivo que inició el inicio de sesión es un dispositivo administrado (1) o no un dispositivo administrado (0)                                                                         |
| `IsCompliant`                     | entero       | Indica si el dispositivo que inició el inicio de sesión es compatible (1) o no (0)                                                                                       |
| `AuthenticationProcessingDetails` | string        | Detalles sobre el procesador de autenticación                                                                                                                                          |
| `AuthenticationRequirement`       | string        | Tipo de autenticación necesaria para el inicio de sesión. Valores posibles: multiFactorAuthentication (se requiere MFA) y singleFactorAuthentication (no se requiere MFA).                |
| `TokenIssuerType`                 | entero        | Indica si el emisor de tokens es Azure Active Directory (0) o servicios de federación de Active Directory (1)                                                                             |
| `RiskLevelAggregated`                       | entero        | Nivel de riesgo agregado durante el inicio de sesión. Valores posibles: 0 (nivel de riesgo agregado no establecido), 1 (ninguno), 10 (bajo), 50 (medio) o 100 (alto).                               |
| `RiskDetails`                      | entero        | Detalles sobre el estado de riesgo del usuario que ha iniciado sesión                                                                                                                            |
| `RiskState`                       | entero        | Indica el estado de usuario de riesgo. Valores posibles: 0 (ninguno), 1 (confirmado como seguro), 2 (corregido), 3 (descartado), 4 (en riesgo) o 5 (confirmado como comprometido).                                |
| `UserAgent`                       | string        | Información de agente de usuario del explorador web u otra aplicación cliente                                                                                                             |
| `ClientAppUsed`                   | string        | Indica la aplicación cliente usada                                                                                                                                                       |
| `Browser`                         | string        | Detalles sobre la versión del explorador que se usa para iniciar sesión                                                                                                                            |
| `ConditionalAccessPolicies`       | string        | Detalles de las directivas de acceso condicional aplicadas al evento de inicio de sesión                                                                                                             |
| `ConditionalAccessStatus`         | entero        | Estado de las directivas de acceso condicional aplicadas al inicio de sesión. Los valores posibles son 0 (directivas aplicadas), 1 (error al intentar aplicar directivas) o 2 (directivas no aplicadas).      |
| `IPAddress`                       | string        | Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas                                                                                                  |
| `CountryCode`                     | string        | Código de dos letras que indica el país en el que se geolocalización la dirección IP del cliente                                                                                                    |
| `State`                           | string        | Estado donde se produjo el inicio de sesión, si está disponible                                                                                                                                      |
| `City`                            | string        | Ciudad donde se encuentra el usuario de la cuenta                                                                                                                                              |
| `Latitude`                        | string        | Coordenadas de norte a sur de la ubicación de inicio de sesión                                                                                                                              |
| `Longitude`                       | string        | Coordenadas de este a oeste de la ubicación de inicio de sesión                                                                                                                                |
| `NetworkLocationDetails`          | string        | Detalles de la ubicación de red del procesador de autenticación del evento de inicio de sesión                                                                                                       |
| `RequestId`                       | string        |  Identificador único de la solicitud                                                                                                                                                   |
|`ReportId` | string | Identificador único del evento |

 

 

## <a name="related-articles"></a>Artículos relacionados

-   [AADSpnSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadspnsignineventsbeta-table)
-   [Información general sobre la búsqueda avanzada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Aprender el lenguaje de consulta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Entender el esquema](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 
