---
title: Migrar consultas de búsqueda avanzada de Microsoft Defender para endpoint
description: Obtenga información sobre cómo ajustar Microsoft Defender para las consultas de puntos de conexión para que pueda usarlas en Microsoft 365 Defender
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, atp de microsoft defender, mdatp, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, microsoft 365, asignación
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 4e008488bdd733c9a7ce5b418fb838e0fe880d9d
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080750"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Migrar consultas de búsqueda avanzada de Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Mueva los flujos de trabajo de búsqueda avanzada de Microsoft Defender for Endpoint para buscar de forma proactiva amenazas mediante un conjunto más amplio de datos. En Microsoft 365 Defender, obtiene acceso a los datos de otras soluciones de seguridad de Microsoft 365, como:

- Microsoft Defender para punto de conexión
- Microsoft Defender para Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

>[!NOTE]
>La mayoría de los clientes de Microsoft Defender para puntos de conexión [pueden usar Microsoft 365 Defender sin licencias adicionales.](prerequisites.md#licensing-requirements) Para empezar a realizar la transición de los flujos de trabajo de búsqueda avanzada desde Defender para endpoint, [active Microsoft 365 Defender.](mtp-enable.md)

Puede realizar la transición sin afectar a los flujos de trabajo existentes de Defender for Endpoint. Las consultas guardadas permanecen intactas y las reglas de detección personalizadas siguen funcionando y generando alertas. Sin embargo, estarán visibles en Microsoft 365 Defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Tablas de esquema solo en Microsoft 365 Defender
El esquema de búsqueda avanzada [de Microsoft 365 Defender](advanced-hunting-schema-tables.md) proporciona tablas adicionales que contienen datos de varias soluciones de seguridad de Microsoft 365. Las tablas siguientes solo están disponibles en Microsoft 365 Defender:

| Nombre de tabla | Descripción |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Archivos, direcciones IP, direcciones URL, usuarios o dispositivos asociados con alertas |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Alertas de Microsoft Defender para Endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security y Microsoft Defender para Identity, incluidas la información de gravedad y las categorías de amenazas  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Actividades relacionadas con archivos en servicios y aplicaciones en la nube |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Información sobre los archivos adjuntos a los correos electrónicos |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Eventos de correo electrónico de Microsoft 365, incluidos los eventos de entrega y bloqueo de correo electrónico |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Eventos de seguridad que se producen después de la entrega, después de que Microsoft 365 haya entregado los correos electrónicos al buzón del destinatario |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Información sobre las direcciones URL de los correos electrónicos |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Eventos que implican a un controlador de dominio local que ejecuta Active Directory (AD). En esta tabla se trata una serie de eventos relacionados con la identidad y eventos del sistema en el controlador de dominio. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Información de cuenta de varios orígenes, incluido Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Eventos de autenticación en Active Directory y servicios en línea de Microsoft |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Consultas de objetos de Active Directory, como usuarios, grupos, dispositivos y dominios |

## <a name="map-devicealertevents-table"></a>Asignar tabla DeviceAlertEvents
Las `AlertInfo` tablas y `AlertEvidence` reemplazan la tabla en el esquema de `DeviceAlertEvents` Microsoft Defender para puntos de conexión. Además de los datos sobre las alertas de dispositivo, estas dos tablas incluyen datos sobre alertas de identidades, aplicaciones y correos electrónicos.

Use la tabla siguiente para comprobar cómo se asignan `DeviceAlertEvents` las columnas a las columnas de las tablas `AlertInfo` `AlertEvidence` y.

>[!TIP]
>Además de las columnas de la tabla siguiente, la tabla incluye muchas otras columnas que proporcionan una imagen más holística de las alertas `AlertEvidence` de varios orígenes. [Ver todas las columnas AlertEvidence](advanced-hunting-alertevidence-table.md) 

| Columna DeviceAlertEvents | Dónde encontrar los mismos datos en Microsoft 365 Defender |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` y  `AlertEvidence` tablas |
| `Timestamp` | `AlertInfo` y  `AlertEvidence` tablas |
| `DeviceId` | `AlertEvidence` tabla |
| `DeviceName` | `AlertEvidence` tabla |
| `Severity` | `AlertInfo` tabla |
| `Category` | `AlertInfo` tabla |
| `Title` | `AlertInfo` tabla |
| `FileName` | `AlertEvidence` tabla |
| `SHA1` | `AlertEvidence` tabla |
| `RemoteUrl` | `AlertEvidence` tabla |
| `RemoteIP` | `AlertEvidence` tabla |
| `AttackTechniques` | `AlertInfo` tabla |
| `ReportId` | Esta columna se usa normalmente en Microsoft Defender para Endpoint para buscar registros relacionados en otras tablas. En Microsoft 365 Defender, puede obtener datos relacionados directamente desde la `AlertEvidence` tabla. |
| `Table` | Esta columna se usa normalmente en Microsoft Defender para Endpoint para obtener información adicional sobre eventos en otras tablas. En Microsoft 365 Defender, puede obtener datos relacionados directamente desde la `AlertEvidence` tabla. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Ajustar Las consultas existentes de Microsoft Defender para puntos de conexión
Las consultas de Microsoft Defender para puntos de conexión funcionarán tal y como están a menos que hacen referencia a la `DeviceAlertEvents` tabla. Para usar estas consultas en Microsoft 365 Defender, aplique estos cambios:

- Reemplazar `DeviceAlertEvents` por `AlertInfo` .
- Una las `AlertInfo` tablas y las tablas para obtener datos `AlertEvidence` `AlertId` equivalentes.

### <a name="original-query"></a>Consulta original
La siguiente consulta usa `DeviceAlertEvents` Microsoft Defender para Endpoint para obtener las alertas que implican _powershell.exe:_

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Consulta modificada
Se ha ajustado la consulta siguiente para su uso en Microsoft 365 Defender. En lugar de comprobar el nombre de archivo directamente desde , se une y `DeviceAlertEvents` comprueba el nombre de archivo en esa `AlertEvidence` tabla.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>Migrar reglas de detección personalizadas

Cuando se editan las reglas de Microsoft Defender para puntos de conexión en Microsoft 365 Defender, siguen funcionando como antes si la consulta resultante solo examina las tablas del dispositivo. Por ejemplo, las alertas generadas por reglas de detección personalizadas que consultan solo tablas de dispositivo se seguirán entregando a siem y generarán notificaciones por correo electrónico, en función de cómo las hayas configurado en Microsoft Defender para Endpoint. También se seguirán aplicando las reglas de supresión existentes en Defender para Endpoint.

Una vez que edite una regla de Defender para extremo para que consulta las tablas de identidad y correo electrónico, que solo están disponibles en Microsoft 365 Defender, la regla se mueve automáticamente a Microsoft 365 Defender. 

Alertas generadas por la regla migrada:

- Ya no están visibles en el portal de Defender for Endpoint (Centro de seguridad de Microsoft Defender)
- Deja de entregarse a siem o genera notificaciones por correo electrónico. Para evitar este cambio, configure las notificaciones a través de Microsoft 365 Defender para obtener las alertas. Puede usar la API de [Microsoft 365 Defender](api-incident.md) para recibir notificaciones de alertas de detección de clientes o incidentes relacionados.
- Microsoft Defender no suprimirá las reglas de supresión de puntos de conexión. Para evitar que se generen alertas para determinados usuarios, dispositivos o buzones, modifique las consultas correspondientes para excluir esas entidades explícitamente.

Si edita una regla de esta forma, se le pedirá confirmación antes de aplicar dichos cambios.

Las nuevas alertas generadas por reglas de detección personalizadas en el portal de Microsoft 365 Defender se muestran en una página de alerta que proporciona la siguiente información:

- Título y descripción de la alerta 
- Activos afectados
- Acciones tomadas en respuesta a la alerta
- Resultados de la consulta que desencadenaron la alerta 
- Información sobre la regla de detección personalizada 
 
![Imagen de la nueva página de alerta](../../media/newalertpage.png)

## <a name="write-queries-without-devicealertevents"></a>Escribir consultas sin DeviceAlertEvents

En el esquema de Microsoft 365 Defender, las tablas y las tablas se proporcionan para dar cabida al variado conjunto de información que acompaña a las alertas `AlertInfo` `AlertEvidence` de varios orígenes. 

Para obtener la misma información de alerta que usó para obtener de la tabla en el esquema de Microsoft Defender para puntos de conexión, filtre la tabla y, a continuación, una cada identificador único con la tabla, que proporciona información detallada sobre eventos y `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` entidades. 

Consulta de ejemplo a continuación:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

Esta consulta genera muchas más columnas que `DeviceAlertEvents` en el esquema de Microsoft Defender para puntos de conexión. Para que los resultados sean fáciles de administrar, úselos para obtener solo las columnas `project` que le interesan. En el ejemplo siguiente se muestran las columnas que pueden interesarle cuando la investigación detectó actividad de PowerShell:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

Si desea filtrar por entidades específicas implicadas en las alertas, puede hacerlo especificando el tipo de entidad y el valor por el que `EntityType` desea filtrar. En el siguiente ejemplo se busca una dirección IP específica:

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a>Consulte también
- [Activar Microsoft 365 Defender](advanced-hunting-query-language.md)
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Búsqueda avanzada en Microsoft Defender para puntos de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)