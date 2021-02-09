---
title: Tabla IdentityLogonEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de autenticación registrados por Active Directory en la tabla IdentityLogonEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, identidades
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 87ac6194374e8e042cf9d00271b17dd8bb785d64
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145360"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La tabla del esquema de búsqueda avanzada contiene información sobre las actividades de autenticación realizadas a través de Active Directory local capturadas por Microsoft Defender para actividades de identidad y autenticación relacionadas con los servicios en línea de Microsoft capturados por `IdentityLogonEvents` Microsoft Cloud App Security. [](advanced-hunting-overview.md) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos (valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

>[!NOTE]
>En esta tabla se tratan las actividades de inicio de sesión de Azure Active Directory (AD) rastreadas por Cloud App Security, especialmente las actividades de autenticación y inicios de sesión interactivos con ActiveSync y otros protocolos heredados. Los inicios de sesión no interactivos que no están disponibles en esta tabla se pueden ver en el registro de auditoría de Azure AD. [Más información sobre cómo conectar Cloud App Security a Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `ActionType` | cadena | Tipo de actividad que desencadenó el evento. Consulta la [referencia del esquema del portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información |
| `LogonType` | string | Tipo de sesión de inicio de sesión, específicamente:<br><br> - **Interactivo:** el usuario interactúa físicamente con la máquina con el teclado y la pantalla locales<br><br> - Inicios de sesión interactivos remotos **(RDP):** el usuario interactúa con el equipo de forma remota mediante Escritorio remoto, Terminal Services, Asistencia remota u otros clientes RDP<br><br> - **Red:** sesión iniciada cuando se tiene acceso a la máquina mediante PsExec o cuando se tiene acceso a recursos compartidos en la máquina, como impresoras y carpetas compartidas.<br><br> - **Lote:** sesión iniciada por tareas programadas<br><br> - **Servicio:** sesión iniciada por los servicios a medida que se inician |
| `Application` | string | Aplicación que realizó la acción grabada |
| `Protocol` | string | Protocolo de red usado |
| `FailureReason` | string | Información que explica por qué se ha fallado la acción grabada |
| `AccountName` | string | Nombre de usuario de la cuenta |
| `AccountDomain` | string | Dominio de la cuenta |
| `AccountUpn` | string | Nombre principal de usuario (UPN) de la cuenta |
| `AccountSid` | string | Identificador de seguridad (SID) de la cuenta |
| `AccountObjectId` | string | Identificador único de la cuenta en Azure AD |
| `AccountDisplayName` | string | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre o nombre, una iniciación intermedia y un apellido o apellido. |
| `DeviceName` | string | Nombre de dominio completo (FQDN) del dispositivo |
| `DeviceType` | string | Tipo de dispositivo |
| `OSPlatform` | cadena | Plataforma del sistema operativo que se ejecuta en el equipo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. |
| `IPAddress` | cadena | Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas |
| `Port` | string | Puerto TCP usado durante la comunicación |
| `DestinationDeviceName` | string | Nombre del dispositivo que ejecuta la aplicación servidor que procesó la acción grabada |
| `DestinationIPAddress` | string | Dirección IP del dispositivo que ejecuta la aplicación servidor que procesó la acción grabada |
| `DestinationPort` | string | Puerto de destino de comunicaciones de red relacionadas |
| `TargetDeviceName` | string | Nombre de dominio completo (FQDN) del dispositivo al que se aplicó la acción grabada |
| `TargetAccountDisplayName` | string | Nombre para mostrar de la cuenta a la que se aplicó la acción grabada |
| `Location` | string | Ciudad, país u otra ubicación geográfica asociada al evento |
| `Isp` | string | Proveedor de servicios de Internet (ISP) asociado a la dirección IP del extremo |
| `ReportId` | largo | Identificador único del evento |
| `AdditionalFields` | string | Información adicional sobre la entidad o el evento |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
