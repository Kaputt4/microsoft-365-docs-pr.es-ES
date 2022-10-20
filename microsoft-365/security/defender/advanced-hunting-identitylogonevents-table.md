---
title: Tabla IdentityLogonEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de autenticación registrados por Active Directory en la tabla IdentityLogonEvents del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, IdentityLogonEvents, Azure AD, Active Directory, Microsoft Defender for Identity, identidades
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
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.openlocfilehash: 0d315ecfdb5895d3492f1af823dd06ce99025474
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68639695"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La `IdentityLogonEvents` tabla del esquema [de búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las actividades de autenticación realizadas a través de active directory local capturadas por Microsoft Defender for Identity y las actividades de autenticación relacionadas con los servicios en línea de Microsoft capturados por Microsoft Defender for Cloud Apps. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada sobre los tipos de eventos (`ActionType` valores) admitidos por una tabla, use la referencia de esquema integrada disponible en Defender for Cloud.

>[!NOTE]
>En esta tabla se tratan las actividades de inicio de sesión de Azure Active Directory (Azure AD) a las que realiza el seguimiento Defender for Cloud Apps, en concreto los inicios de sesión interactivos y las actividades de autenticación mediante ActiveSync y otros protocolos heredados. Los inicios de sesión no interactivos que no están disponibles en esta tabla se pueden ver en el registro de auditoría de Azure AD. [Más información sobre cómo conectar Defender for Cloud Apps a Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `ActionType` | `string` | Tipo de actividad que desencadenó el evento. Consulte la [referencia de esquema en el portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información. |
| `Application` | `string` | Aplicación que realizó la acción registrada |
| `LogonType` | `string` | Tipo de sesión de inicio de sesión, en concreto:<br><br> - **Interactivo** : el usuario interactúa físicamente con la máquina mediante el teclado y la pantalla locales<br><br> - **Inicios de sesión interactivos remotos (RDP** ): el usuario interactúa con la máquina de forma remota mediante Escritorio remoto, Terminal Services, Asistencia remota u otros clientes RDP.<br><br> - **Red** : sesión iniciada cuando se accede a la máquina mediante PsExec o cuando se accede a recursos compartidos en la máquina, como impresoras y carpetas compartidas.<br><br> - **Batch** : sesión iniciada por tareas programadas<br><br> - **Servicio** : sesión iniciada por los servicios a medida que comienzan |
| `Protocol` | `string` | Protocolo de red usado |
| `FailureReason` | `string` | Información que explica por qué se produjo un error en la acción registrada |
| `AccountName` | `string` | Nombre de usuario de la cuenta |
| `AccountDomain` | `string` | Dominio de la cuenta |
| `AccountUpn` | `string` | Nombre principal de usuario (UPN) de la cuenta |
| `AccountSid` | `string` | Identificador de seguridad (SID) de la cuenta |
| `AccountObjectId` | `string` | Identificador único de la cuenta en Azure AD |
| `AccountDisplayName` | `string` | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre determinado o de nombre, una iniciación intermedia y un apellido o apellido. |
| `DeviceName` | `string` | Nombre de dominio completo (FQDN) del dispositivo |
| `DeviceType` | `string` | Tipo de dispositivo |
| `OSPlatform` | `string` | Plataforma del sistema operativo que se ejecuta en el equipo. Esto indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 11, Windows 10 y Windows 7. |
| `IPAddress` | `string` | Dirección IP asignada al punto de conexión y usada durante las comunicaciones de red relacionadas |
| `Port` | `string` | Puerto TCP usado durante la comunicación |
| `DestinationDeviceName` | `string` | Nombre del dispositivo que ejecuta la aplicación de servidor que procesó la acción registrada |
| `DestinationIPAddress` | `string` | Dirección IP del dispositivo que ejecuta la aplicación de servidor que procesó la acción registrada |
| `DestinationPort` | `string` | Puerto de destino de las comunicaciones de red relacionadas |
| `TargetDeviceName` | `string` | Nombre de dominio completo (FQDN) del dispositivo al que se aplicó la acción registrada |
| `TargetAccountDisplayName` | `string` | Nombre para mostrar de la cuenta a la que se aplicó la acción registrada |
| `Location` | `string` | Ciudad, país u otra ubicación geográfica asociada al evento |
| `Isp` | `string` | Proveedor de servicios de Internet (ISP) asociado a la dirección IP del punto de conexión |
| `ReportId` | `long` | Identificador único del evento |
| `AdditionalFields` | `string` | Información adicional sobre la entidad o el evento |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
