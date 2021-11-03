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
ms.openlocfilehash: 3954ef585ee3a4f51677f3e5e26b6309d3b75889
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60661464"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender



La tabla del esquema de búsqueda avanzada contiene información acerca de las actividades en varias aplicaciones y servicios en la nube `CloudAppEvents` cubiertos por [](advanced-hunting-overview.md) Microsoft Cloud App Security. Para obtener una lista completa, vaya a [Aplicaciones y servicios cubiertos.](#apps-and-services-covered) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla. 

>[!IMPORTANT]
>Esta tabla incluye información que solía estar disponible en la `AppFileEvents` tabla. A partir del 7 de marzo de 2021, los usuarios que usen actividades relacionadas con archivos en servicios en la nube en y más allá de esta fecha deben usar la `CloudAppEvents` tabla en su lugar. <br><br>Asegúrese de buscar consultas y reglas de detección personalizadas que aún usan la tabla y `AppFileEvents` editarlas para usar la `CloudAppEvents` tabla. Encontrará más instrucciones sobre cómo convertir consultas afectadas en Hunt en las actividades de la aplicación en la nube [Microsoft 365 Defender búsqueda avanzada.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)


Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `ActionType` | cadena | Tipo de actividad que desencadenó el evento |
| `Application` | string | Aplicación que realizó la acción grabada |
| `ApplicationId` | cadena | Identificador único de la aplicación |
| `AccountObjectId` | cadena | Identificador único de la cuenta en Azure Active Directory |
| `AccountDisplayName` | cadena | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre o un nombre determinado, un inicio intermedio y un apellido o apellido. |
| `IsAdminOperation` | cadena | Indica si la actividad la realizó un administrador |
| `DeviceType` | string | Tipo de dispositivo basado en propósitos y funciones, como "Dispositivo de red", "Estación de trabajo", "Servidor", "Móvil", "Consola de juegos" o "Impresora" | 
| `OSPlatform` | cadena | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esta columna indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 11, Windows 10 y Windows 7. |
| `IPAddress` | cadena | Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas |
| `IsAnonymousProxy` | cadena | Indica si la dirección IP pertenece a un proxy anónimo conocido |
| `CountryCode` | cadena | Código de dos letras que indica el país donde se geolocalización de la dirección IP del cliente |
| `City` | cadena | Ciudad donde se geolocalización de la dirección IP del cliente |
| `Isp` | cadena | Proveedor de servicios de Internet (ISP) asociado a la dirección IP |
| `UserAgent` | cadena | Información del agente de usuario desde el explorador web u otra aplicación cliente |
| `ActivityType` | cadena | Tipo de actividad que desencadenó el evento |
| `ActivityObjects` | dinámico | Lista de objetos, como archivos o carpetas, que participaron en la actividad grabada |
| `ObjectName` | cadena | Nombre del objeto al que se aplicó la acción grabada |
| `ObjectType` | string | Tipo de objeto, como un archivo o una carpeta, al que se aplicó la acción grabada |
| `ObjectId` | cadena | Identificador único del objeto al que se aplicó la acción grabada |
| `ReportId` | cadena | Identificador único del evento |
| `RawEventData` | cadena | Información de evento sin procesar de la aplicación o servicio de origen en formato JSON |
| `AdditionalFields` | dinámico | Información adicional sobre la entidad o el evento |
| `AccountType` | cadena | Tipo de cuenta de usuario, que indica su rol general y niveles de acceso, como Regular, System, Admin, DcAdmin, System, Application | 
| `IsExternalUser` | booleano | Indica si un usuario dentro de la red no pertenece al dominio de la organización | 
| `IsImpersonated` | booleano | Indica si la actividad la realizó un usuario en nombre de otro (suplantado) usuario | 
| `IPTags` | dinámico | Información definida por el cliente aplicada a direcciones IP específicas e intervalos de direcciones IP | 
| `IPCategory` | cadena | Información adicional sobre la dirección IP | 
| `UserAgentTags` | dinámico | Más información proporcionada por Microsoft Cloud App Security una etiqueta en el campo agente de usuario. Puede tener cualquiera de los siguientes valores: cliente nativo, explorador obsoleto, sistema operativo obsoleto, robot | 

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
