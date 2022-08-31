---
title: Tabla CloudAppEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de aplicaciones y servicios en la nube en la tabla CloudAppEvents del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, CloudAppEvents, Defender for Cloud Apps
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 8892a672cb9fc77b4cf606f32581c1928decc45f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67470151"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

La `CloudAppEvents` tabla del esquema [de búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las actividades en varias aplicaciones y servicios en la nube cubiertos por Microsoft Defender for Cloud Apps. Para obtener una lista completa, vaya a [Aplicaciones y servicios cubiertos](#apps-and-services-covered). Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

> [!IMPORTANT]
> Esta tabla incluye información que solía estar disponible en la `AppFileEvents` tabla. A partir del 7 de marzo de 2021, los usuarios que busquen actividades relacionadas con archivos en servicios en la nube en y más allá de esta fecha deben usar la `CloudAppEvents` tabla en su lugar. <br><br>Asegúrese de buscar consultas y reglas de detección personalizadas que todavía usen la `AppFileEvents` tabla y editarlas para usar la `CloudAppEvents` tabla. Puede encontrar más instrucciones sobre la conversión de consultas afectadas en [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting (Búsqueda entre actividades de aplicaciones en la nube con Microsoft 365 Defender búsqueda avanzada](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)).

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `ActionType` | `string` | Tipo de actividad que desencadenó el evento |
| `Application` | `string` | Aplicación que realizó la acción registrada |
| `ApplicationId` | `string` | Identificador único de la aplicación |
| `AccountObjectId` | `string` | Identificador único de la cuenta en Azure Active Directory |
| `AccountId` | `string` | Identificador de la cuenta tal como lo encuentra Microsoft Defender for Cloud Apps. Puede ser el identificador de Azure Active Directory, el nombre principal de usuario u otros identificadores. |
| `AccountDisplayName` | `string` | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre determinado o de nombre, una iniciación intermedia y un apellido o apellido. |
| `IsAdminOperation` | `string` | Indica si la actividad la realizó un administrador |
| `DeviceType` | `string` | Tipo de dispositivo basado en el propósito y la funcionalidad, como "Dispositivo de red", "Estación de trabajo", "Servidor", "Móvil", "Consola de juegos" o "Impresora" |
| `OSPlatform` | `string` | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esta columna indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 11, Windows 10 y Windows 7. |
| `IPAddress` | `string` | Dirección IP asignada al punto de conexión y usada durante las comunicaciones de red relacionadas |
| `IsAnonymousProxy` | `string` | Indica si la dirección IP pertenece a un proxy anónimo conocido |
| `CountryCode` | `string` | Código de dos letras que indica el país donde la dirección IP del cliente está geolocalizada |
| `City` | `string` | Ciudad donde la dirección IP del cliente está geolocalizada |
| `Isp` | `string` | Proveedor de servicios de Internet (ISP) asociado a la dirección IP |
| `UserAgent` | `string` | Información del agente de usuario desde el explorador web u otra aplicación cliente |
| `ActivityType` | `string` | Tipo de actividad que desencadenó el evento |
| `ActivityObjects` | `dynamic` | Lista de objetos, como archivos o carpetas, que participaron en la actividad registrada |
| `ObjectName` | `string` | Nombre del objeto al que se aplicó la acción registrada |
| `ObjectType` | `string` | Tipo de objeto, como un archivo o una carpeta, al que se aplicó la acción registrada |
| `ObjectId` | `string` | Identificador único del objeto al que se aplicó la acción registrada |
| `ReportId` | `string` | Identificador único del evento |
| `RawEventData` | `string` | Información de eventos sin formato de la aplicación o servicio de origen en formato JSON |
| `AdditionalFields` | `dynamic` | Información adicional sobre la entidad o el evento |
| `AccountType` | `string` | Tipo de cuenta de usuario, que indica su rol general y sus niveles de acceso, como Regular, System, Administración, DcAdmin, System, Application |
| `IsExternalUser` | `boolean` | Indica si un usuario dentro de la red no pertenece al dominio de la organización |
| `IsImpersonated` | `boolean` | Indica si un usuario realizó la actividad para otro usuario (suplantado) |
| `IPTags` | `dynamic` | Información definida por el cliente aplicada a direcciones IP específicas e intervalos de direcciones IP |
| `IPCategory` | `string` | Información adicional sobre la dirección IP |
| `UserAgentTags` | `dynamic` | Más información proporcionada por Microsoft Defender for Cloud Apps en una etiqueta en el campo agente de usuario. Puede tener cualquiera de los siguientes valores: cliente nativo, explorador obsoleto, sistema operativo obsoleto, robot |

## <a name="apps-and-services-covered"></a>Aplicaciones y servicios cubiertos

- Dropbox
- Dynamics 365
- Exchange Online
- Microsoft Teams
- OneDrive para la Empresa
- Power Automate
- Power BI
- SharePoint Online
- Skype Empresarial
- Office 365
- Yammer

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
