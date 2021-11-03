---
title: Tabla IdentityLogonEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de autenticación registrados por Active Directory en la tabla IdentityLogonEvents del esquema de búsqueda avanzado
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, IdentityLogonEvents, Azure AD, Active Directory, Microsoft Defender para identidad, identidades
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5ce24bfafe690252535579d81b702db025f69217
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2021
ms.locfileid: "60704295"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La tabla del esquema de búsqueda avanzada contiene información sobre las actividades de autenticación realizadas a través de su Active Directory local capturado por Microsoft Defender para las actividades de identidad y autenticación relacionadas con los servicios en línea de Microsoft capturados por `IdentityLogonEvents` Microsoft Cloud App Security. [](advanced-hunting-overview.md) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos ( valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad.

>[!NOTE]
>En esta tabla se Azure Active Directory (Azure AD) las actividades de inicio de sesión de Cloud App Security, específicamente interactivas y las actividades de autenticación mediante ActiveSync y otros protocolos heredados. Los inicios de sesión no interactivos que no están disponibles en esta tabla se pueden ver en el registro Azure AD auditoría. [Obtenga más información sobre cómo Cloud App Security a Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `ActionType` | cadena | Tipo de actividad que desencadenó el evento. Vea la [referencia de esquema en el portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información |
| `Application` | string | Aplicación que realizó la acción grabada |
| `LogonType` | cadena | Tipo de sesión de inicio de sesión, específicamente:<br><br> - **Interactivo:** el usuario interactúa físicamente con la máquina con el teclado y la pantalla locales<br><br> - Inicios de sesión interactivos remotos **(RDP):** el usuario interactúa con el equipo de forma remota mediante Escritorio remoto, Terminal Services, Asistencia remota u otros clientes RDP<br><br> - **Red:** sesión iniciada cuando se tiene acceso al equipo mediante PsExec o cuando se tiene acceso a recursos compartidos en el equipo, como impresoras y carpetas compartidas.<br><br> - **Lote:** sesión iniciada por tareas programadas<br><br> - **Servicio:** sesión iniciada por los servicios cuando se inician |
| `Protocol` | cadena | Protocolo de red usado |
| `FailureReason` | cadena | Información que explica por qué falló la acción grabada |
| `AccountName` | cadena | Nombre de usuario de la cuenta |
| `AccountDomain` | string | Dominio de la cuenta |
| `AccountUpn` | cadena | Nombre principal de usuario (UPN) de la cuenta |
| `AccountSid` | cadena | Identificador de seguridad (SID) de la cuenta |
| `AccountObjectId` | cadena | Identificador único de la cuenta en Azure AD |
| `AccountDisplayName` | cadena | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre o un nombre determinado, un inicio intermedio y un apellido o apellido. |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN) del dispositivo |
| `DeviceType` | cadena | Tipo de dispositivo |
| `OSPlatform` | cadena | Plataforma del sistema operativo que se ejecuta en el equipo. Esto indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 11, Windows 10 y Windows 7. |
| `IPAddress` | cadena | Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas |
| `Port` | cadena | Puerto TCP usado durante la comunicación |
| `DestinationDeviceName` | string | Nombre del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada |
| `DestinationIPAddress` | string | Dirección IP del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada |
| `DestinationPort` | string | Puerto de destino de comunicaciones de red relacionadas |
| `TargetDeviceName` | string | Nombre de dominio completo (FQDN) del dispositivo al que se aplicó la acción grabada |
| `TargetAccountDisplayName` | string | Nombre para mostrar de la cuenta a la que se aplicó la acción grabada |
| `Location` | string | Ciudad, país u otra ubicación geográfica asociada al evento |
| `Isp` | string | Proveedor de servicios de Internet (ISP) asociado con la dirección IP del extremo |
| `ReportId` | largo | Identificador único del evento |
| `AdditionalFields` | cadena | Información adicional sobre la entidad o el evento |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)