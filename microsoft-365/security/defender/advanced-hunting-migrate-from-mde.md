---
title: Migración de consultas de búsqueda avanzadas desde Microsoft Defender para punto de conexión
description: Obtenga información sobre cómo ajustar las consultas de Microsoft Defender para punto de conexión para que pueda usarlas en Microsoft 365 Defender
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, Microsoft Defender para punto de conexión, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, asignación
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 9fd00df5e61d37e5133f23e5f06973ceb99c4636
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666182"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Migración de consultas de búsqueda avanzadas desde Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Mueva los flujos de trabajo de búsqueda avanzados de Microsoft Defender para punto de conexión a la búsqueda proactiva de amenazas mediante un conjunto más amplio de datos. En Microsoft 365 Defender, obtiene acceso a los datos de otras soluciones de seguridad de Microsoft 365, entre las que se incluyen:

- Microsoft Defender para punto de conexión
- Microsoft Defender para Office 365
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Identity

>[!NOTE]
>La mayoría de los clientes Microsoft Defender para punto de conexión pueden [usar Microsoft 365 Defender sin licencias adicionales](prerequisites.md#licensing-requirements). Para empezar a realizar la transición de los flujos de trabajo de búsqueda avanzados desde Defender para punto de conexión, [active Microsoft 365 Defender](m365d-enable.md).

Puede realizar la transición sin afectar a los flujos de trabajo existentes de Defender para punto de conexión. Las consultas guardadas permanecen intactas y las reglas de detección personalizadas siguen ejecutándose y generando alertas. Sin embargo, serán visibles en Microsoft 365 Defender.

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Tablas de esquema solo en Microsoft 365 Defender

El [Microsoft 365 Defender esquema de búsqueda avanzada](advanced-hunting-schema-tables.md) proporciona tablas adicionales que contienen datos de varias soluciones de seguridad Microsoft 365. Las tablas siguientes solo están disponibles en Microsoft 365 Defender:

| Nombre de tabla | Descripción |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Archivos, direcciones IP, direcciones URL, usuarios o dispositivos asociados a alertas |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Alertas de Microsoft Defender para punto de conexión, Microsoft Defender para Office 365, Microsoft Defender for Cloud Apps y Microsoft Defender for Identity , incluida la información de gravedad y las categorías de amenazas  |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Información sobre los archivos adjuntos a los correos electrónicos |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Eventos de correo electrónico de Microsoft 365, incluidos los eventos de bloqueo y entrega de correo electrónico |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Eventos de seguridad que se producen después de la entrega, una vez que Microsoft 365 ha entregado ya los correos electrónicos al buzón del destinatario |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Información sobre las direcciones URL de los correos electrónicos |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Eventos que implican un controlador de dominio local que ejecuta Active Directory (AD). En esta tabla se describen una serie de eventos relacionados con la identidad y eventos del sistema en el controlador de dominio. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Información de la cuenta de varios orígenes, incluyendo Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Eventos de autenticación en Active Directory y en servicios en línea de Microsoft |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Consultas sobree objetos de Active Directory, como usuarios, grupos, dispositivos y dominios |

>[!IMPORTANT]
> Las consultas y las detecciones personalizadas que usan tablas de esquema que solo están disponibles en Microsoft 365 Defender solo se pueden ver en Microsoft 365 Defender.

## <a name="map-devicealertevents-table"></a>Tabla Map DeviceAlertEvents

Las `AlertInfo` tablas y `AlertEvidence` reemplazan la `DeviceAlertEvents` tabla en el esquema de Microsoft Defender para punto de conexión. Además de los datos sobre las alertas de dispositivo, estas dos tablas incluyen datos sobre alertas de identidades, aplicaciones y correos electrónicos.

Use la tabla siguiente para comprobar cómo `DeviceAlertEvents` se asignan las columnas a las columnas de las `AlertInfo` tablas y `AlertEvidence` .

> [!TIP]
> Además de las columnas de la tabla siguiente, la `AlertEvidence` tabla incluye muchas otras columnas que proporcionan una imagen más holística de las alertas de varios orígenes. [Ver todas las columnas AlertEvidence](advanced-hunting-alertevidence-table.md)

| Columna DeviceAlertEvents | Dónde encontrar los mismos datos en Microsoft 365 Defender |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` y  `AlertEvidence` tablas |
| `Timestamp` | `AlertInfo` y  `AlertEvidence` tablas |
| `DeviceId` | `AlertEvidence` Mesa |
| `DeviceName` | `AlertEvidence` Mesa |
| `Severity` | `AlertInfo` Mesa |
| `Category` | `AlertInfo` Mesa |
| `Title` | `AlertInfo` Mesa |
| `FileName` | `AlertEvidence` Mesa |
| `SHA1` | `AlertEvidence` Mesa |
| `RemoteUrl` | `AlertEvidence` Mesa |
| `RemoteIP` | `AlertEvidence` Mesa |
| `AttackTechniques` | `AlertInfo` Mesa |
| `ReportId` | Esta columna se usa normalmente en Microsoft Defender para punto de conexión para buscar registros relacionados en otras tablas. En Microsoft 365 Defender, puede obtener datos relacionados directamente desde la `AlertEvidence` tabla. |
| `Table` | Esta columna se usa normalmente en Microsoft Defender para punto de conexión para obtener información adicional sobre eventos en otras tablas. En Microsoft 365 Defender, puede obtener datos relacionados directamente desde la `AlertEvidence` tabla. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Ajuste de las consultas de Microsoft Defender para punto de conexión existentes

Microsoft Defender para punto de conexión consultas funcionarán tal y como están a menos que hagan referencia a la `DeviceAlertEvents` tabla. Para usar estas consultas en Microsoft 365 Defender, aplique estos cambios:

- Reemplazar `DeviceAlertEvents` por `AlertInfo`.
- Una las `AlertInfo` tablas y `AlertEvidence` en `AlertId` para obtener datos equivalentes.

### <a name="original-query"></a>Consulta original

La consulta siguiente usa `DeviceAlertEvents` en Microsoft Defender para punto de conexión para obtener las alertas que implican _powershell.exe_:

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d)
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```

### <a name="modified-query"></a>Consulta modificada

La consulta siguiente se ha ajustado para su uso en Microsoft 365 Defender. En lugar de comprobar el nombre de archivo directamente desde `DeviceAlertEvents`, se une `AlertEvidence` y comprueba el nombre de archivo de esa tabla.

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where AttackTechniques has "PowerShell (T1086)"
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>Migración de reglas de detección personalizadas

Cuando se editan Microsoft Defender para punto de conexión reglas en Microsoft 365 Defender, siguen funcionando como antes si la consulta resultante examina solo las tablas de dispositivos.

Por ejemplo, las alertas generadas por reglas de detección personalizadas que consultan solo las tablas de dispositivos se seguirán entregando a siem y generarán notificaciones por correo electrónico, en función de cómo las haya configurado en Microsoft Defender para punto de conexión. Las reglas de supresión existentes en Defender para punto de conexión también se seguirán aplicando.

Una vez que edite una regla de Defender para punto de conexión para que consulte las tablas de identidad y correo electrónico, que solo están disponibles en Microsoft 365 Defender, la regla se mueve automáticamente a Microsoft 365 Defender.

Alertas generadas por la regla migrada:

- Ya no están visibles en el portal de Defender para punto de conexión (Centro de seguridad de Microsoft Defender)
- Deje de entregarse a su SIEM o genere notificaciones por correo electrónico. Para solucionar este cambio, configure las notificaciones a través de Microsoft 365 Defender para obtener las alertas. Puede usar la [API de Microsoft 365 Defender](api-incident.md) para recibir notificaciones de alertas de detección de clientes o incidentes relacionados.
- No se suprimirá mediante Microsoft Defender para punto de conexión reglas de supresión. Para evitar que se generen alertas para determinados usuarios, dispositivos o buzones de correo, modifique las consultas correspondientes para excluir esas entidades explícitamente.

Si edita una regla de esta manera, se le pedirá confirmación antes de que se apliquen dichos cambios.

Las nuevas alertas generadas por las reglas de detección personalizadas en Microsoft 365 Defender se muestran en una página de alertas que proporciona la siguiente información:

- Título y descripción de la alerta
- Activos afectados
- Acciones realizadas en respuesta a la alerta
- Resultados de la consulta que desencadenaron la alerta
- Información sobre la regla de detección personalizada

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/new-alert-page.png" alt-text="Ejemplo de una página de alertas que muestra nuevas alertas generadas por reglas de detección personalizadas en Microsoft 365 Defender portal" lightbox="../../media/new-alert-page.png":::

## <a name="write-queries-without-devicealertevents"></a>Escritura de consultas sin DeviceAlertEvents

En el esquema de Microsoft 365 Defender, se proporcionan las `AlertInfo` tablas y `AlertEvidence` para dar cabida al diverso conjunto de información que acompaña a las alertas de varios orígenes.

Para obtener la misma información de alerta que usó para obtener de la `DeviceAlertEvents` tabla en el esquema Microsoft Defender para punto de conexión, filtre la `AlertInfo` tabla por `ServiceSource` y, a continuación, una cada identificador único con la `AlertEvidence` tabla, que proporciona información detallada sobre eventos y entidades.

Consulte la consulta de ejemplo siguiente:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

Esta consulta genera muchas más columnas que `DeviceAlertEvents` en el esquema de Microsoft Defender para punto de conexión. Para que los resultados sean fáciles de administrar, use `project` para obtener solo las columnas que le interesan. En el ejemplo siguiente se proyectan columnas que podrían interesarle cuando la investigación detectó la actividad de PowerShell:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine
```

Si desea filtrar por entidades específicas implicadas en las alertas, puede hacerlo especificando el tipo de entidad en `EntityType` y el valor por el que desea filtrar. En el ejemplo siguiente se busca una dirección IP específica:

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId
| where EntityType == "Ip" and RemoteIP == "192.88.99.01"
```

## <a name="see-also"></a>Vea también

- [Activar Microsoft 365 Defender](advanced-hunting-query-language.md)
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Búsqueda avanzada en Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
