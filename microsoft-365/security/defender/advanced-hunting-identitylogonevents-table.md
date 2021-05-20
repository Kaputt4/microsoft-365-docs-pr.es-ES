---
title: IdentityLogonEvents tabla en el esquema de caza avanzado
description: Obtenga información sobre los eventos de autenticación registrados por Active Directory en la tabla IdentityLogonEvents del esquema de caza avanzado
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, IdentityLogonEvents, Azure AD, Active Directory, Microsoft Defender for Identity, identidades
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
ms.openlocfilehash: 3cd0c0f371c73a515704791e829be7266d400580
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572758"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La `IdentityLogonEvents` tabla del esquema de caza [avanzada](advanced-hunting-overview.md) contiene información sobre las actividades de autenticación realizadas a través del Active Directory local capturado por Microsoft Defender para actividades de identidad y autenticación relacionadas con los servicios en línea de Microsoft capturados por Microsoft Cloud App Security. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos ( `ActionType` valores) admitidos por una tabla, use la referencia de esquema integrada disponible en el centro de seguridad.

>[!NOTE]
>En esta tabla se tratan Azure Active Directory (Azure AD) a las que Cloud App Security realiza un seguimiento de las actividades de inicio de sesión (Azure AD), específicamente los inicios de sesión interactivos y las actividades de autenticación mediante ActiveSync y otros protocolos heredados. Los inicios de sesión no interactivos que no están disponibles en esta tabla se pueden ver en el registro de auditoría de Azure AD. [Obtén más información sobre cómo conectar Cloud App Security a Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `ActionType` | cadena | Tipo de actividad que desencadenó el evento. Consulte la [referencia de esquema en](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) el portal para obtener más información |
| `Application` | cadena | Aplicación que realizó la acción grabada |
| `LogonType` | cadena | Tipo de sesión de inicio de sesión, específicamente:<br><br> - **Interactivo** : el usuario interactúa físicamente con la máquina utilizando el teclado y la pantalla locales<br><br> - **Inicios de sesión interactivos remotos (RDP):** el usuario interactúa con la máquina de forma remota mediante Escritorio remoto, Servicios de Terminal Server, asistencia remota u otros clientes RDP<br><br> - **Red:** se accede a la sesión cuando se accede al equipo mediante PsExec o cuando se accede a los recursos compartidos del equipo, como impresoras y carpetas compartidas.<br><br> - **Lote** - Sesión iniciada por tareas programadas<br><br> - **Servicio** - Sesión iniciada por los servicios a medida que comienzan |
| `Protocol` | cadena | Protocolo de red utilizado |
| `FailureReason` | cadena | Información que explica por qué fracasó la acción registrada |
| `AccountName` | cadena | Nombre de usuario de la cuenta |
| `AccountDomain` | cadena | Dominio de la cuenta |
| `AccountUpn` | cadena | Nombre principal de usuario (UPN) de la cuenta |
| `AccountSid` | cadena | Identificador de seguridad (SID) de la cuenta |
| `AccountObjectId` | cadena | Identificador único de la cuenta en Azure AD |
| `AccountDisplayName` | cadena | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre determinado o un nombre, una iniciación intermedia y un apellido o apellido. |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN) del dispositivo |
| `DeviceType` | cadena | Tipo de dispositivo |
| `OSPlatform` | cadena | Plataforma del sistema operativo que se ejecuta en el equipo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. |
| `IPAddress` | cadena | Dirección IP asignada al punto de conexión y utilizada durante las comunicaciones de red relacionadas |
| `Port` | cadena | Puerto TCP utilizado durante la comunicación |
| `DestinationDeviceName` | cadena | Nombre del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada |
| `DestinationIPAddress` | cadena | Dirección IP del dispositivo que ejecuta la aplicación del servidor que procesó la acción grabada |
| `DestinationPort` | cadena | Puerto de destino de las comunicaciones de red relacionadas |
| `TargetDeviceName` | cadena | Nombre de dominio completo (FQDN) del dispositivo al que se aplicó la acción registrada |
| `TargetAccountDisplayName` | cadena | Mostrar el nombre de la cuenta a la que se aplicó la acción registrada |
| `Location` | cadena | Ciudad, país u otra ubicación geográfica asociada con el evento |
| `Isp` | cadena | Proveedor de servicios de Internet (ISP) asociado con la dirección IP del punto final |
| `ReportId` | largo | Identificador único para el evento |
| `AdditionalFields` | cadena | Información adicional sobre la entidad o evento |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)