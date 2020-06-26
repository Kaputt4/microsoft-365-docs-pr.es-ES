---
title: Tabla DeviceLogonEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre la autenticación o los eventos de inicio de sesión en la tabla DeviceLogonEvents del esquema de búsqueda avanzada.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, logonevents, DeviceLogonEvents, autenticación, Inicio de sesión, iniciar sesión
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
ms.openlocfilehash: 07b2c2301784f378075e3c9803cebc5bcabf9cb0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899272"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

**Se aplica a:**
- Protección contra amenazas de Microsoft



La `DeviceLogonEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre los inicios de sesión de los usuarios y otros eventos de autenticación. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | string | Identificador único para el equipo en servicio |
| `DeviceName` | string | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `ActionType` | cadena |Tipo de actividad que ha desencadenado el evento |
| `AccountDomain` | string | Dominio de la cuenta |
| `AccountName` | string | Nombre de usuario de la cuenta |
| `AccountSid` | string | Identificador de seguridad (SID) de la cuenta |
| `LogonType` | string | Tipo de sesión de inicio de sesión, en concreto:<br><br> - **Interactivo** : el usuario interactúa físicamente con el equipo mediante el teclado y la pantalla locales<br><br> - **Inicios de sesión remotos (RDP)** : el usuario interactúa con el equipo de forma remota con escritorio remoto, Terminal Services, asistencia remota u otros clientes RDP.<br><br> - Sesión de **red** iniciada cuando se tiene acceso al equipo con PsExec o cuando se tiene acceso a recursos compartidos en el equipo, como impresoras y carpetas compartidas<br><br> - Sesión **por lotes** iniciada por tareas programadas<br><br> - Sesión de **servicio** iniciada por los servicios a medida que se inician<br> |
| `LogonId` | string | Identificador de una sesión de inicio de sesión. Este identificador es único en el mismo equipo solo entre reinicios |
| `RemoteDeviceName` | string | Nombre del equipo que llevó a cabo una operación remota en el equipo afectado. Según el evento que se notifica, este nombre puede ser un nombre de dominio completo (FQDN), un nombre NetBIOS o un nombre de host sin información de dominio |
| `RemoteIP` | cadena | Dirección IP a la que se ha conectado |
| `RemoteIPType` | string | Tipo de dirección IP, por ejemplo Public, Private, Reserved, loopback, Teredo, FourToSixMapping y difusión |
| `RemotePort` | int | Puerto TCP del dispositivo remoto al que se estaba conectando |
| `AdditionalFields` | string | Información adicional sobre el evento en el formato de matriz JSON |
| `InitiatingProcessAccountDomain` | string | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | string | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | string | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessIntegrityLevel` | string | Nivel de integridad del proceso que inició el evento. Windows asigna niveles de integridad a los procesos en función de ciertas características, como si se iniciaron desde una descarga de Internet. Estos niveles de integridad influyen en los permisos para recursos |
| `InitiatingProcessTokenElevation` | string | Tipo de token que indica la presencia o ausencia de la elevación de privilegios de control de acceso de usuario (UAC) que se aplica al proceso que inició el evento |
| `InitiatingProcessSHA1` | string | SHA-1 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA256` | string | SHA-256 del proceso (archivo de imagen) que inició el evento. Este campo no suele rellenarse; use la columna SHA1 cuando esté disponible |
| `InitiatingProcessMD5` | string | Hash MD5 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessFileName` | string | Nombre del proceso que inició el evento |
| `InitiatingProcessId` | int | IDENTIFICADOR de proceso (PID) del proceso que inició el evento |
| `InitiatingProcessCommandLine` | string | Línea de comandos que se usa para ejecutar el proceso que inició el evento |
| `InitiatingProcessCreationTime` | datetime | Fecha y hora en que se inició el proceso que inició el evento |
| `InitiatingProcessFolderPath` | string | Carpeta que contiene el proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessParentId` | int | IDENTIFICADOR de proceso (PID) del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentFileName` | string | Nombre del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentCreationTime` | datetime | Fecha y hora en que se inició el primario del proceso responsable del evento |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y timestamp. |
| `AppGuardContainerId` | string | Identificador del contenedor virtualizado que usa la protección de aplicaciones para aislar la actividad del explorador |
| `IsLocalAdmin` | boolean | Indicador booleano de si el usuario es un administrador local en el equipo |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
