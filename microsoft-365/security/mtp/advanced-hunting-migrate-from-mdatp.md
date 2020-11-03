---
title: Migrar consultas de búsqueda avanzada de Microsoft defender para el punto de conexión
description: Aprenda a ajustar las consultas de Microsoft defender para el punto de conexión para que pueda usarlas en Microsoft 365 defender
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, ATP de Microsoft defender, mdatp, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, Microsoft 365, asignación
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b69dff94cc5d3ba3331fd6d13b1d7de1402ac47
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846861"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Migrar consultas de búsqueda avanzada de Microsoft defender para el punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 defender

Mueva los flujos de trabajo de caza avanzados de Microsoft defender para el punto de conexión para buscar de forma proactiva las amenazas con un conjunto de datos más amplio. En Microsoft 365 defender, obtiene acceso a datos de otras soluciones de seguridad de Microsoft 365, entre las que se incluyen:

- Microsoft Defender para punto de conexión
- Microsoft defender para Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

>[!NOTE]
>La mayoría de los clientes de Microsoft defender para extremo pueden [usar microsoft 365 defender sin licencias adicionales](prerequisites.md#licensing-requirements). Para empezar a migrar los flujos de trabajo de caza avanzados de defender para el punto de conexión, [Active Microsoft 365 defender](mtp-enable.md).

Puede realizar la transición sin afectar a los flujos de trabajo de defender existentes para el punto de conexión. Las consultas guardadas permanecen intactas y las reglas de detección personalizadas continúan ejecutándose y generando alertas. Sin embargo, estarán visibles en Microsoft 365 defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Tablas de esquema en Microsoft 365 defender solamente
El [esquema de búsqueda avanzada de microsoft 365 defender](advanced-hunting-schema-tables.md) proporciona tablas adicionales que contienen datos de diversas soluciones de seguridad de Microsoft 365. Las siguientes tablas solo están disponibles en Microsoft 365 defender:

| Nombre de tabla | Descripción |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Archivos, direcciones IP, URL, usuarios o dispositivos asociados con alertas |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Alertas de Microsoft defender para el punto de conexión, Microsoft defender para Office 365, Microsoft Cloud App Security y Microsoft defender para identidad, incluida la información de gravedad y las categorías de amenaza  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Actividades relacionadas con archivos en aplicaciones y servicios en la nube |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Información sobre los archivos adjuntos a los correos electrónicos |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Eventos de correo electrónico de Microsoft 365, incluidos eventos de bloqueo y entrega de correo electrónico |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Eventos de seguridad que se producen después de la entrega, después de que Microsoft 365 haya entregado los correos electrónicos al buzón del destinatario |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Información sobre las direcciones URL en correos electrónicos |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Eventos que implican un controlador de dominio local que ejecuta Active Directory (AD). Esta tabla cubre una amplia variedad de eventos relacionados con la identidad y eventos del sistema en el controlador de dominio. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Información de cuenta de varios orígenes, incluido Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Eventos de autenticación en Active Directory y Microsoft Online Services |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Consultas de objetos de Active Directory, como usuarios, grupos, dispositivos y dominios |

## <a name="map-devicealertevents-table"></a>Tabla DeviceAlertEvents de mapa
Las `AlertInfo` `AlertEvidence` tablas y reemplazan la `DeviceAlertEvents` tabla en el esquema de Microsoft defender para extremo. Además de datos sobre alertas de dispositivos, estas dos tablas incluyen datos sobre las alertas de identidades, aplicaciones y mensajes de correo electrónico.

Use la tabla siguiente para comprobar el modo en que `DeviceAlertEvents` las columnas se asignan a las columnas en las `AlertInfo` `AlertEvidence` tablas y.

>[!TIP]
>Además de las columnas de la tabla siguiente, la `AlertEvidence` tabla incluye muchas otras columnas que proporcionan una imagen más holística de las alertas de varios orígenes. [Ver todas las columnas de AlertEvidence](advanced-hunting-alertevidence-table.md) 

| Columna DeviceAlertEvents | Dónde encontrar los mismos datos en Microsoft 365 defender |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo``AlertEvidence`tablas y |
| `Timestamp` | `AlertInfo``AlertEvidence`tablas y |
| `DeviceId` | `AlertEvidence` Table |
| `DeviceName` | `AlertEvidence` Table |
| `Severity` | `AlertInfo` Table |
| `Category` | `AlertInfo` Table |
| `Title` | `AlertInfo` Table |
| `FileName` | `AlertEvidence` Table |
| `SHA1` | `AlertEvidence` Table |
| `RemoteUrl` | `AlertEvidence` Table |
| `RemoteIP` | `AlertEvidence` Table |
| `AttackTechniques` | `AlertInfo` Table |
| `ReportId` | Esta columna se suele usar en Microsoft defender para Endpoint para buscar registros relacionados en otras tablas. En Microsoft 365 defender, puede obtener datos relacionados directamente de la `AlertEvidence` tabla. |
| `Table` | Esta columna se suele usar en Microsoft defender para el punto de conexión para obtener información adicional sobre eventos en otras tablas. En Microsoft 365 defender, puede obtener datos relacionados directamente de la `AlertEvidence` tabla. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Ajustar las consultas existentes de Microsoft defender para Endpoint
Las consultas de Microsoft defender for Endpoint funcionarán tal cual, a menos que hagan referencia a la `DeviceAlertEvents` tabla. Para usar estas consultas en Microsoft 365 defender, aplique estos cambios:

- Reemplazar `DeviceAlertEvents` por `AlertInfo` .
- Una el `AlertInfo` y las `AlertEvidence` tablas en `AlertId` para obtener datos equivalentes.

### <a name="original-query"></a>Consulta original
La siguiente consulta usa `DeviceAlertEvents` en Microsoft defender para el punto de conexión para obtener las alertas que implican _powershell.exe_ :

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Consulta modificada
La siguiente consulta se ha ajustado para su uso en Microsoft 365 defender. En lugar de comprobar el nombre de archivo directamente desde `DeviceAlertEvents` , se unen `AlertEvidence` y se comprueba el nombre de archivo en esa tabla.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>Temas relacionados
- [Activar Microsoft 365 defender](advanced-hunting-query-language.md)
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Búsqueda avanzada en Microsoft defender para el punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)