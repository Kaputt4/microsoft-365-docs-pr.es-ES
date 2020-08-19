---
title: Tabla IdentityLogonEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de autenticación registrados por Active Directory en la tabla IdentityLogonEvents del esquema de búsqueda avanzada.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, IdentityLogonEvents, Azure AD, Active Directory, ATP de Azure, identidades
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 86212bdecb58b2e79a94d0129a0a531ef22bd6e4
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797845"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**Se aplica a:**
- Protección contra amenazas de Microsoft

La `IdentityLogonEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las actividades de autenticación realizadas a través de Active Directory local capturado por ATP de Azure y actividades de autenticación relacionadas con Microsoft Online Services capturado por Microsoft Cloud App Security. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos ( `ActionType` valores) admitidos por una tabla, use la [referencia de esquema integrada](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponible en el centro de seguridad.

>[!NOTE]
>En esta tabla se tratan las actividades de inicio de sesión de Azure Active Directory (AD) con seguimiento por Cloud App Security, los inicios de sesión interactivos y las actividades de autenticación mediante ActiveSync y otros protocolos heredados. Los inicios de sesión no interactivos que no están disponibles en esta tabla se pueden ver en el registro de auditoría de Azure AD. [Obtenga más información sobre cómo conectar Cloud App Security a Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `ActionType` | cadena | Tipo de actividad que ha desencadenado el evento. Consulte la [Referencia del esquema del portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más detalles |
| `LogonType` | string | Tipo de sesión de inicio de sesión, en concreto:<br><br> - **Interactivo** : el usuario interactúa físicamente con el equipo mediante el teclado y la pantalla locales<br><br> - **Inicios de sesión remotos (RDP)** : el usuario interactúa con el equipo de forma remota con escritorio remoto, Terminal Services, asistencia remota u otros clientes RDP.<br><br> - Sesión de **red** iniciada cuando se tiene acceso al equipo con PsExec o cuando se tiene acceso a recursos compartidos en el equipo, como impresoras y carpetas compartidas<br><br> - Sesión **por lotes** iniciada por tareas programadas<br><br> - Sesión de **servicio** iniciada por los servicios a medida que se inician |
| `Application` | string | Aplicación que realizó la acción grabada |
| `Protocol` | string | Protocolo de red usado |
| `FailureReason` | string | Información que explica por qué falló la acción grabada |
| `AccountName` | string | Nombre de usuario de la cuenta |
| `AccountDomain` | string | Dominio de la cuenta |
| `AccountUpn` | string | Nombre principal de usuario (UPN) de la cuenta |
| `AccountSid` | string | Identificador de seguridad (SID) de la cuenta |
| `AccountObjectId` | string | Identificador único de la cuenta en Azure AD |
| `AccountDisplayName` | string | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente es una combinación de un nombre determinado o de un nombre, un inicio en el medio y un apellido o un apellido. |
| `DeviceName` | string | Nombre de dominio completo (FQDN) del dispositivo |
| `DeviceType` | string | Tipo de dispositivo |
| `OSPlatform` | cadena | Plataforma del sistema operativo que se ejecuta en el equipo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. |
| `IPAddress` | cadena | Dirección IP asignada al extremo y utilizada durante las comunicaciones de red relacionadas |
| `DestinationDeviceName` | string | Nombre del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada |
| `DestinationIPAddress` | string | Dirección IP del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada |
| `TargetDeviceName` | string | Nombre de dominio completo (FQDN) del dispositivo al que se aplicó la acción grabada |
| `TargetAccountDisplayName` | string | Nombre para mostrar de la cuenta a la que se aplicó la acción registrada |
| `Location` | string | Ciudad, país u otra ubicación geográfica asociada con el evento |
| `Isp` | string | Proveedor de servicios de Internet (ISP) asociado con la dirección IP del extremo |
| `ReportId` | largo | Identificador único del evento |
| `AdditionalFields` | string | Información adicional acerca de la entidad o el evento |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)