---
title: Tabla CloudAppEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre eventos de servicios y aplicaciones en la nube en la tabla CloudAppEvents del esquema de búsqueda avanzado
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 128d4f9ce80bff6192771ee1806f708d0d15c00f
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531140"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender



La tabla del esquema de búsqueda avanzada contiene información sobre las actividades en diversas aplicaciones y servicios en la nube que `CloudAppEvents` cubre Microsoft Defender para aplicaciones en la nube. [](advanced-hunting-overview.md) Para obtener una lista completa, vaya a [Aplicaciones y servicios cubiertos.](#apps-and-services-covered) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla. 

>[!IMPORTANT]
>Esta tabla incluye información que solía estar disponible en la `AppFileEvents` tabla. A partir del 7 de marzo de 2021, los usuarios que usen actividades relacionadas con archivos en servicios en la nube en y más allá de esta fecha deben usar la `CloudAppEvents` tabla en su lugar. <br><br>Asegúrese de buscar consultas y reglas de detección personalizadas que aún usan la tabla y `AppFileEvents` editarlas para usar la `CloudAppEvents` tabla. Encontrará más instrucciones sobre cómo convertir consultas afectadas en Hunt en las actividades de la aplicación en la nube [Microsoft 365 Defender búsqueda avanzada.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)


Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Description |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `ActionType` | `string` | Tipo de actividad que desencadenó el evento |
| `Application` | `string` | Aplicación que realizó la acción grabada |
| `ApplicationId` | `string` | Identificador único de la aplicación |
| `AccountObjectId` | `string` | Identificador único de la cuenta en Azure Active Directory |
| `AccountId` | `string` | Identificador de la cuenta tal como se encuentra Microsoft Cloud App Security. Podría ser Azure Active Directory, nombre principal de usuario u otros identificadores. |
| `AccountDisplayName` | `string` | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre o un nombre determinado, un inicio intermedio y un apellido o apellido. |
| `IsAdminOperation` | `string` | Indica si la actividad la realizó un administrador |
| `DeviceType` | `string` | Tipo de dispositivo basado en propósitos y funciones, como "Dispositivo de red", "Estación de trabajo", "Servidor", "Móvil", "Consola de juegos" o "Impresora" | 
| `OSPlatform` | `string` | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esta columna indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 11, Windows 10 y Windows 7. |
| `IPAddress` | `string` | Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas |
| `IsAnonymousProxy` | `string` | Indica si la dirección IP pertenece a un proxy anónimo conocido |
| `CountryCode` | `string` | Código de dos letras que indica el país donde se geolocalización de la dirección IP del cliente |
| `City` | `string` | Ciudad donde se geolocalización de la dirección IP del cliente |
| `Isp` | `string` | Proveedor de servicios de Internet (ISP) asociado a la dirección IP |
| `UserAgent` | `string` | Información del agente de usuario desde el explorador web u otra aplicación cliente |
| `ActivityType` | `string` | Tipo de actividad que desencadenó el evento |
| `ActivityObjects` | `dynamic` | Lista de objetos, como archivos o carpetas, que participaron en la actividad grabada |
| `ObjectName` | `string` | Nombre del objeto al que se aplicó la acción grabada |
| `ObjectType` | `string` | Tipo de objeto, como un archivo o una carpeta, al que se aplicó la acción grabada |
| `ObjectId` | `string` | Identificador único del objeto al que se aplicó la acción grabada |
| `ReportId` | `string` | Identificador único del evento |
| `RawEventData` | `string` | Información de evento sin procesar de la aplicación o servicio de origen en formato JSON |
| `AdditionalFields` | `dynamic` | Información adicional sobre la entidad o el evento |
| `AccountType` | `string` | Tipo de cuenta de usuario, que indica su rol general y niveles de acceso, como Regular, System, Admin, DcAdmin, System, Application | 
| `IsExternalUser` | `boolean` | Indica si un usuario dentro de la red no pertenece al dominio de la organización | 
| `IsImpersonated` | `boolean` | Indica si un usuario realizó la actividad para otro usuario (suplantado) | 
| `IPTags` | `dynamic` | Información definida por el cliente aplicada a direcciones IP específicas e intervalos de direcciones IP | 
| `IPCategory` | `string` | Información adicional sobre la dirección IP | 
| `UserAgentTags` | `dynamic` | Más información proporcionada por Microsoft Defender para aplicaciones en la nube en una etiqueta en el campo agente de usuario. Puede tener cualquiera de los siguientes valores: cliente nativo, explorador obsoleto, sistema operativo obsoleto, robot | 

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
