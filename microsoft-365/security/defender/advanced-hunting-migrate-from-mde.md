---
title: Migrar consultas de búsqueda avanzada desde Microsoft Defender para endpoint
description: Obtenga información sobre cómo ajustar las consultas de Microsoft Defender para puntos de conexión para que pueda usarlas en Microsoft 365 Defender
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, atp de microsoft defender, mdatp, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, microsoft 365, asignación
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: c0a29f93b9ea926beaeecb840ba108da04a89ebb
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501144"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Migrar consultas de búsqueda avanzada desde Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Mueva los flujos de trabajo de búsqueda avanzados de Microsoft Defender para endpoint para buscar de forma proactiva amenazas mediante un conjunto más amplio de datos. En Microsoft 365 Defender, obtiene acceso a datos de otras soluciones de seguridad de Microsoft 365, como:

- Microsoft Defender para punto de conexión
- Microsoft Defender para Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

>[!NOTE]
>La mayoría de los clientes de Microsoft Defender para [endpoints pueden usar Microsoft 365 Defender sin licencias adicionales.](prerequisites.md#licensing-requirements) Para empezar a realizar la transición de los flujos de trabajo de búsqueda avanzados desde Defender para endpoint, [active Microsoft 365 Defender](m365d-enable.md).

Puede realizar la transición sin afectar a los flujos de trabajo existentes de Defender for Endpoint. Las consultas guardadas permanecen intactas y las reglas de detección personalizadas siguen funcionando y generando alertas. Sin embargo, estarán visibles en Microsoft 365 Defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Tablas de esquema solo en Microsoft 365 Defender
El esquema de búsqueda avanzada de [Microsoft 365 Defender](advanced-hunting-schema-tables.md) proporciona tablas adicionales que contienen datos de varias soluciones de seguridad de Microsoft 365. Las tablas siguientes solo están disponibles en Microsoft 365 Defender:

| Nombre de tabla | Descripción |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Archivos, direcciones IP, direcciones URL, usuarios o dispositivos asociados con alertas |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Alertas de Microsoft Defender para endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security y Microsoft Defender para Identidad, incluidas la información de gravedad y las categorías de amenazas  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Actividades relacionadas con archivos en servicios y aplicaciones en la nube |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Información sobre los archivos adjuntos a los correos electrónicos |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Eventos de correo electrónico de Microsoft 365, incluidos los eventos de entrega y bloqueo de correo electrónico |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Eventos de seguridad que se producen después de la entrega, después de que Microsoft 365 haya entregado los correos electrónicos al buzón de destinatario |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Información sobre las direcciones URL de los correos electrónicos |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Eventos que implican un controlador de dominio local que ejecuta Active Directory (AD). En esta tabla se describe un rango de eventos relacionados con la identidad y eventos del sistema en el controlador de dominio. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Información de cuenta de varios orígenes, incluido Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Eventos de autenticación en Active Directory y servicios en línea de Microsoft |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Consultas para objetos de Active Directory, como usuarios, grupos, dispositivos y dominios |

>[!IMPORTANT]
> Las consultas y detecciones personalizadas que usan tablas de esquema que solo están disponibles en Microsoft 365 Defender solo se pueden ver en Microsoft 365 Defender.

## <a name="map-devicealertevents-table"></a>Tabla Map DeviceAlertEvents
Las `AlertInfo` tablas y `AlertEvidence` reemplazan la tabla en el esquema de Microsoft `DeviceAlertEvents` Defender para endpoint. Además de los datos sobre alertas de dispositivos, estas dos tablas incluyen datos sobre alertas para identidades, aplicaciones y correos electrónicos.

Use la tabla siguiente para comprobar cómo se asignan `DeviceAlertEvents` las columnas a las columnas de las tablas `AlertInfo` `AlertEvidence` y.

>[!TIP]
>Además de las columnas de la tabla siguiente, la tabla incluye muchas otras columnas que proporcionan una imagen más holística de las alertas `AlertEvidence` de varios orígenes. [Ver todas las columnas alertevidence](advanced-hunting-alertevidence-table.md) 

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
| `ReportId` | Esta columna se suele usar en Microsoft Defender para endpoint para buscar registros relacionados en otras tablas. En Microsoft 365 Defender, puede obtener datos relacionados directamente de la `AlertEvidence` tabla. |
| `Table` | Esta columna se suele usar en Microsoft Defender para Endpoint para obtener información adicional sobre eventos en otras tablas. En Microsoft 365 Defender, puede obtener datos relacionados directamente de la `AlertEvidence` tabla. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Ajustar las consultas existentes de Microsoft Defender para puntos de conexión
Las consultas de Microsoft Defender para puntos de conexión funcionarán tal como están a menos que haga referencia a la `DeviceAlertEvents` tabla. Para usar estas consultas en Microsoft 365 Defender, aplique estos cambios:

- Reemplace `DeviceAlertEvents` por `AlertInfo` .
- Une `AlertInfo` las tablas y las para obtener datos `AlertEvidence` `AlertId` equivalentes.

### <a name="original-query"></a>Consulta original
La siguiente consulta usa `DeviceAlertEvents` en Microsoft Defender for Endpoint para obtener las alertas que implican _powershell.exe_:

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Consulta modificada
La siguiente consulta se ha ajustado para su uso en Microsoft 365 Defender. En lugar de comprobar el nombre de archivo directamente desde , se une y `DeviceAlertEvents` comprueba el nombre de archivo en esa `AlertEvidence` tabla.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>Migrar reglas de detección personalizadas

Cuando las reglas de Microsoft Defender para extremo se editan en Microsoft 365 Defender, siguen funcionando como antes si la consulta resultante solo mira las tablas de dispositivos. 

Por ejemplo, las alertas generadas por reglas de detección personalizadas que consultan solo tablas de dispositivos se seguirán entregando a siem y generarán notificaciones por correo electrónico, según cómo las haya configurado en Microsoft Defender para endpoint. Las reglas de supresión existentes en Defender for Endpoint también se seguirán aplicando.

Una vez que edites una regla de Defender para endpoint para que consulta las tablas de identidad y correo electrónico, que solo están disponibles en Microsoft 365 Defender, la regla se mueve automáticamente a Microsoft 365 Defender. 

Alertas generadas por la regla migrada:

- Ya no están visibles en el portal de Defender for Endpoint (Centro de seguridad de Microsoft Defender)
- Deje de entregarse en siem o genere notificaciones por correo electrónico. Para evitar este cambio, configure las notificaciones a través de Microsoft 365 Defender para obtener las alertas. Puede usar la API de [Microsoft 365 Defender](api-incident.md) para recibir notificaciones de alertas de detección de clientes o incidentes relacionados.
- Microsoft Defender no suprimirá las reglas de supresión de puntos de conexión. Para evitar que se generen alertas para determinados usuarios, dispositivos o buzones de correo, modifique las consultas correspondientes para excluir esas entidades explícitamente.

Si edita una regla de esta manera, se le pedirá confirmación antes de aplicar dichos cambios.

Las nuevas alertas generadas por reglas de detección personalizadas en el portal de Microsoft 365 Defender se muestran en una página de alerta que proporciona la siguiente información:

- Título y descripción de la alerta 
- Activos afectados
- Acciones realizadas en respuesta a la alerta
- Resultados de consulta que desencadenaron la alerta 
- Información sobre la regla de detección personalizada 
 
![Imagen de la nueva página de alerta](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a>Escribir consultas sin DeviceAlertEvents

En el esquema de Microsoft 365 Defender, las tablas y se proporcionan para dar cabida al conjunto diverso de información que acompaña a las alertas `AlertInfo` `AlertEvidence` de varios orígenes. 

Para obtener la misma información de alerta que usó para obtener de la tabla en el esquema de Microsoft Defender para endpoint, filtre la tabla y, a continuación, una cada identificador único con la tabla, que proporciona información detallada sobre el evento y la `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` entidad. 

Vea la consulta de ejemplo siguiente:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

Esta consulta genera muchas más columnas que `DeviceAlertEvents` en el esquema de Microsoft Defender para endpoint. Para que los resultados sean manejables, use `project` para obtener solo las columnas que le interesan. En el ejemplo siguiente se proyectan las columnas que podrían interesarle cuando la investigación detecte actividad de PowerShell:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

Si desea filtrar por entidades específicas implicadas en las alertas, puede hacerlo especificando el tipo de entidad y el valor por el que `EntityType` desea filtrar. En el ejemplo siguiente se busca una dirección IP específica:

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a>Consulta también
- [Activar Microsoft 365 Defender](advanced-hunting-query-language.md)
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Búsqueda avanzada en Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)