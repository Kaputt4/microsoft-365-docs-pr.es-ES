---
title: Migrar consultas de búsqueda avanzada desde ATP de Microsoft defender
description: Obtenga información sobre cómo ajustar las consultas de ATP de Microsoft defender para que pueda usarlas en la protección contra amenazas de Microsoft
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
ms.openlocfilehash: f56360b28a9fe9de4198d97954a64a429d1d99a5
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429700"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a>Migrar consultas de búsqueda avanzada desde ATP de Microsoft defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Protección contra amenazas de Microsoft

Mueva sus flujos de trabajo de caza avanzados de Microsoft defender ATP para buscar de forma proactiva las amenazas con un conjunto de datos más amplio. En Microsoft Threat Protection, obtiene acceso a datos de otras soluciones de seguridad de Microsoft 365, entre las que se incluyen:

- Protección contra amenazas avanzada de Microsoft Defender
- Protección contra amenazas avanzada de Office 365
- Microsoft Cloud App Security
- Azure Advanced Threat Protection

>[!NOTE]
>La mayoría de los clientes ATP de Microsoft defender pueden [usar la protección contra amenazas de Microsoft sin licencias adicionales](prerequisites.md#licensing-requirements). Para empezar a realizar la transición de los flujos de trabajo de búsqueda avanzada de ATP de Microsoft defender, [Active la protección contra amenazas de Microsoft](mtp-enable.md).

Puede realizar la transición sin afectar a los flujos de trabajo de ATP existentes de Microsoft defender. Las consultas guardadas permanecen intactas y las reglas de detección personalizadas continúan ejecutándose y generando alertas. Sin embargo, estarán visibles en la protección contra amenazas de Microsoft. 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a>Tablas de esquema de la protección contra amenazas de Microsoft
El [esquema de búsqueda avanzada de Microsoft Threat Protection](advanced-hunting-schema-tables.md) proporciona tablas adicionales que contienen datos de diversas soluciones de seguridad de Microsoft 365. Las siguientes tablas solo están disponibles en protección contra amenazas de Microsoft:

| Nombre de tabla | Descripción |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Archivos, direcciones IP, URL, usuarios o dispositivos asociados con alertas |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Alertas de Microsoft defender ATP, Office 365 ATP, Microsoft Cloud App Security y Azure ATP, incluida la información de gravedad y las categorías de amenaza  |
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
Las `AlertInfo` `AlertEvidence` tablas y reemplazan la `DeviceAlertEvents` tabla en el esquema ATP de Microsoft defender. Además de datos sobre alertas de dispositivos, estas dos tablas incluyen datos sobre las alertas de identidades, aplicaciones y mensajes de correo electrónico.

Use la tabla siguiente para comprobar el modo en que `DeviceAlertEvents` las columnas se asignan a las columnas en las `AlertInfo` `AlertEvidence` tablas y.

>[!TIP]
>Además de las columnas de la tabla siguiente, la `AlertEvidence` tabla incluye muchas otras columnas que proporcionan una imagen más holística de las alertas de varios orígenes. [Ver todas las columnas de AlertEvidence](advanced-hunting-alertevidence-table.md) 

| Columna DeviceAlertEvents | Dónde encontrar los mismos datos en la protección contra amenazas de Microsoft |
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
| `ReportId` | Esta columna se suele usar en ATP de Microsoft defender para buscar registros relacionados en otras tablas. En la protección contra amenazas de Microsoft, puede obtener datos relacionados directamente de la `AlertEvidence` tabla. |
| `Table` | Esta columna se suele usar en ATP de Microsoft defender para obtener información adicional sobre eventos en otras tablas. En la protección contra amenazas de Microsoft, puede obtener datos relacionados directamente de la `AlertEvidence` tabla. |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a>Ajustar las consultas existentes de ATP de Microsoft defender
Las consultas ATP de Microsoft defender funcionarán tal cual, a menos que hagan referencia a la `DeviceAlertEvents` tabla. Para usar estas consultas en la protección contra amenazas de Microsoft, aplique estos cambios:

- Reemplazar `DeviceAlertEvents` por `AlertInfo` .
- Una el `AlertInfo` y las `AlertEvidence` tablas en `AlertId` para obtener datos equivalentes.

### <a name="original-query"></a>Consulta original
La siguiente consulta usa `DeviceAlertEvents` ATP de Microsoft defender para obtener las alertas que implican _powershell.exe_:

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Consulta modificada
La siguiente consulta se ha ajustado para su uso en Microsoft Threat Protection. En lugar de comprobar el nombre de archivo directamente desde `DeviceAlertEvents` , se unen `AlertEvidence` y se comprueba el nombre de archivo en esa tabla.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>Temas relacionados
- [Habilitar la Protección contra amenazas de Microsoft](advanced-hunting-query-language.md)
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Búsqueda avanzada en ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)