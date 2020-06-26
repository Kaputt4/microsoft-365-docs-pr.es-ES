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
ms.openlocfilehash: 17e12e9095219b7ad7923f7b5664946fff6ce724
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899380"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**Se aplica a:**
- Protección contra amenazas de Microsoft

La `IdentityLogonEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las actividades de autenticación registradas por Azure Active Directory y otras aplicaciones y servicios en la nube de Microsoft. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `ActionType` | string | Tipo de actividad que ha desencadenado el evento |
| `LogonType` | string | Tipo de sesión de inicio de sesión, en concreto:<br><br> - **Interactivo** : el usuario interactúa físicamente con el equipo mediante el teclado y la pantalla locales<br><br> - **Inicios de sesión remotos (RDP)** : el usuario interactúa con el equipo de forma remota con escritorio remoto, Terminal Services, asistencia remota u otros clientes RDP.<br><br> - Sesión de **red** iniciada cuando se tiene acceso al equipo con PsExec o cuando se tiene acceso a recursos compartidos en el equipo, como impresoras y carpetas compartidas<br><br> - Sesión **por lotes** iniciada por tareas programadas<br><br> - Sesión de **servicio** iniciada por los servicios a medida que se inician |
| `Application` | string | Aplicación que realizó la acción grabada |
| `Protocol` | string | Protocolo usado durante la comunicación |
| `AccountName` | string | Nombre de usuario de la cuenta |
| `AccountDomain` | string | Dominio de la cuenta |
| `AccountUpn` | string | Nombre principal de usuario (UPN) de la cuenta |
| `AccountSid` | string | Identificador de seguridad (SID) de la cuenta |
| `AccountObjectId` | string | Identificador único de la cuenta en Azure AD |
| `AccountDisplayName` | string | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente es una combinación de un nombre determinado o de un nombre, un inicio en el medio y un apellido o un apellido. |
| `DeviceName` | string | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `DeviceType` | string | Tipo de dispositivo |
| `OSPlatform` | cadena | Plataforma del sistema operativo que se ejecuta en el equipo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. |
| `IPAddress` | cadena | Dirección IP asignada al extremo y utilizada durante las comunicaciones de red relacionadas |
| `Location` | string | Ciudad, país u otra ubicación geográfica asociada con el evento |
| `Isp` | string | Proveedor de servicios de Internet (ISP) asociado con la dirección IP del extremo |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
