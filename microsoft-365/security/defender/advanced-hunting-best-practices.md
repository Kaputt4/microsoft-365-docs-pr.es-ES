---
title: Procedimientos recomendados de consulta de búsqueda avanzada en Microsoft 365 Defender
description: Aprenda a crear consultas de búsqueda de amenazas rápidas, eficaces y sin errores con búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, esquema, kusto, evitar tiempo de espera, líneas de comandos, identificador de proceso, optimizar, procedimiento recomendado, analizar, unir, resumir
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
- tier2
ms.topic: conceptual
ms.openlocfilehash: 31b5747f9d73961a95ef45ea063d25915f9e640c
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68625773"
---
# <a name="advanced-hunting-query-best-practices"></a>Prácticas recomendadas para la consulta de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Aplique estas recomendaciones para obtener resultados más rápido y evitar tiempos de espera al ejecutar consultas complejas. Para obtener más información sobre cómo mejorar el rendimiento de las consultas, vea [procedimientos recomendados de consulta de Kusto](/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-quotas"></a>Descripción de las cuotas de recursos de CPU
En función de su tamaño, cada inquilino tiene acceso a una cantidad establecida de recursos de CPU asignados para ejecutar consultas de búsqueda avanzadas. Para obtener información detallada sobre varios parámetros de uso, [lea sobre las cuotas de búsqueda avanzadas y los parámetros de uso](advanced-hunting-limits.md).

Después de ejecutar la consulta, puede ver el tiempo de ejecución y su uso de recursos (Bajo, Medio, Alto). High indica que la consulta tardó más recursos en ejecutarse y se pudo mejorar para devolver resultados de forma más eficaz.

:::image type="content" source="../../media/resource-usage.png" alt-text="Los detalles de la consulta en la pestaña **Resultados** del portal de Microsoft 365 Defender" lightbox="../../media/resource-usage.png":::

Los clientes que ejecutan varias consultas con regularidad deben realizar un seguimiento del consumo y aplicar las instrucciones de optimización de este artículo para minimizar la interrupción resultante de superar las cuotas o los parámetros de uso.

Vea [Optimización de consultas KQL](https://www.youtube.com/watch?v=ceYvRuPp5D8) para ver algunas de las formas más comunes de mejorar las consultas.  

## <a name="general-optimization-tips"></a>Sugerencias generales de optimización

- **Ajustar el tamaño de las nuevas consultas**: si sospecha que una consulta devolverá un conjunto de resultados grande, evaluela primero con el [operador count](/azure/data-explorer/kusto/query/countoperator). Use [limit](/azure/data-explorer/kusto/query/limitoperator) o su sinónimo `take` para evitar conjuntos de resultados grandes.
- **Aplicar filtros al principio**: aplique filtros de tiempo y otros filtros para reducir el conjunto de datos, especialmente antes de usar funciones de transformación y análisis, como [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction)o [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction). En el ejemplo siguiente, la función de análisis [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) se usa después de que los operadores de filtrado hayan reducido el número de registros.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount"
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Contiene latidos**: para evitar buscar subcadenas en palabras innecesariamente, use el `has` operador en lugar de `contains`. [Más información sobre los operadores de cadena](/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Buscar en columnas específicas**: busque en una columna específica en lugar de ejecutar búsquedas de texto completo en todas las columnas. No use `*` para comprobar todas las columnas.
- **Distingue mayúsculas de minúsculas para la velocidad**: las búsquedas que distinguen mayúsculas de minúsculas son más específicas y, por lo general, tienen un mayor rendimiento. Los nombres de [operadores de cadena](/azure/data-explorer/kusto/query/datatypes-string-operators) que distinguen mayúsculas de minúsculas, como `has_cs` y `contains_cs`, suelen terminar con `_cs`. También puede usar el operador `==` equals que distingue mayúsculas de minúsculas en lugar de `=~`.
- **Analizar, no extraer**: siempre que sea posible, use el [operador de análisis](/azure/data-explorer/kusto/query/parseoperator) o una función de análisis como [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction). Evite el `matches regex` operador de cadena o la [función extract(),](/azure/data-explorer/kusto/query/extractfunction) que usan la expresión regular. Reserve el uso de la expresión regular para escenarios más complejos. [Obtenga más información sobre el análisis de funciones](#parse-strings)
- **Filtrar tablas no expresiones**: no filtre por una columna calculada si puede filtrar por una columna de tabla.
- **Sin términos de tres caracteres**: evite comparar o filtrar mediante términos con tres caracteres o menos. Estos términos no se indexan y la coincidencia con ellos requerirá más recursos.
- **Proyecto de forma selectiva**: haga que los resultados sean más fáciles de entender proyectando solo las columnas que necesita. La proyección de columnas específicas antes de ejecutar operaciones de [combinación](/azure/data-explorer/kusto/query/joinoperator) o similares también ayuda a mejorar el rendimiento.



## <a name="optimize-the-join-operator"></a>Optimización del `join` operador
El [operador join](/azure/data-explorer/kusto/query/joinoperator) combina filas de dos tablas mediante la coincidencia de valores en columnas especificadas. Aplique estas sugerencias para optimizar las consultas que usan este operador.

- **Tabla más pequeña a la izquierda**: el `join` operador coincide con los registros de la tabla del lado izquierdo de la instrucción join con los registros de la derecha. Al tener la tabla más pequeña a la izquierda, será necesario buscar menos registros, lo que acelerará la consulta.

    En la tabla siguiente, se reduce la tabla `DeviceLogonEvents` izquierda para cubrir solo tres dispositivos específicos antes de combinarla con `IdentityLogonEvents` los SID de cuenta.

    ```kusto
    DeviceLogonEvents
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- **Usar el sabor de combinación interna**: el [sabor de combinación](/azure/data-explorer/kusto/query/joinoperator#join-flavors) predeterminado o [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) desduplica las filas de la tabla izquierda por la clave de combinación antes de devolver una fila para cada coincidencia a la tabla derecha. Si la tabla izquierda tiene varias filas con el mismo valor para la `join` clave, esas filas se desduplicarán para dejar una sola fila aleatoria para cada valor único.

    Este comportamiento predeterminado puede dejar fuera información importante de la tabla izquierda que puede proporcionar información útil. Por ejemplo, la consulta siguiente solo mostrará un correo electrónico que contenga datos adjuntos determinados, incluso si esos mismos datos adjuntos se enviaron mediante varios mensajes de correo electrónico:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

    Para abordar esta limitación, aplicamos el tipo [de combinación interna](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) especificando `kind=inner` para mostrar todas las filas de la tabla izquierda con valores coincidentes a la derecha:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```
- **Combinar registros desde un período de tiempo**: al investigar eventos de seguridad, los analistas buscan eventos relacionados que se produzcan alrededor del mismo período de tiempo. La aplicación del mismo enfoque cuando se usa `join` también beneficia al rendimiento al reducir el número de registros que se van a comprobar.

    La consulta siguiente comprueba si hay eventos de inicio de sesión en un plazo de 30 minutos después de recibir un archivo malintencionado:

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where ThreatTypes has "Malware"
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **Aplicar filtros de tiempo en ambos lados**: incluso si no está investigando un período de tiempo específico, la aplicación de filtros de tiempo en las tablas izquierda y derecha puede reducir el número de registros para comprobar y mejorar `join` el rendimiento. La consulta siguiente se aplica `Timestamp > ago(1h)` a ambas tablas para que se una solo a los registros de la última hora:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

- **Usar sugerencias para el rendimiento**: use sugerencias con el `join` operador para indicar al back-end que distribuya la carga al ejecutar operaciones que consumen muchos recursos. [Más información sobre las sugerencias de combinación](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Por ejemplo, la **[sugerencia de orden aleatorio](/azure/data-explorer/kusto/query/shufflequery)** ayuda a mejorar el rendimiento de las consultas al combinar tablas mediante una clave con una cardinalidad alta (una clave con muchos valores únicos), como en la `AccountObjectId` consulta siguiente:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId
    ```

    La **[sugerencia de difusión](/azure/data-explorer/kusto/query/broadcastjoin)** ayuda cuando la tabla izquierda es pequeña (hasta 100 000 registros) y la tabla derecha es extremadamente grande. Por ejemplo, la consulta siguiente está intentando unirse a algunos correos electrónicos que tienen asuntos específicos con _todos los_ mensajes que contienen vínculos en la `EmailUrlInfo` tabla:

    ```kusto
    EmailEvents
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId
    ```

## <a name="optimize-the-summarize-operator"></a>Optimización del `summarize` operador
El [operador summarize](/azure/data-explorer/kusto/query/summarizeoperator) agrega el contenido de una tabla. Aplique estas sugerencias para optimizar las consultas que usan este operador.

- **Buscar valores distintos**: en general, use `summarize` para buscar valores distintos que puedan ser repetitivos. Puede ser innecesario usarlo para agregar columnas que no tienen valores repetitivos.

    Aunque un único correo electrónico puede formar parte de varios eventos, el ejemplo siguiente _no_ es un uso eficaz de porque un identificador de mensaje de `summarize` red para un correo electrónico individual siempre viene con una dirección de remitente única.

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress
    ```
    El `summarize` operador se puede reemplazar fácilmente por `project`, lo que produce potencialmente los mismos resultados y consume menos recursos:

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress
    ```
    El ejemplo siguiente es un uso más eficaz de `summarize` porque puede haber varias instancias distintas de una dirección de remitente que envía correo electrónico a la misma dirección de destinatario. Estas combinaciones son menos distintas y es probable que tengan duplicados.

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress
    ```

- **Orden aleatorio de la consulta**: aunque `summarize` se usa mejor en columnas con valores repetitivos, las mismas columnas también pueden tener _una cardinalidad alta_ o un gran número de valores únicos. Al igual que el `join` operador , también puede aplicar la [sugerencia de orden aleatorio](/azure/data-explorer/kusto/query/shufflequery) con `summarize` para distribuir la carga de procesamiento y potencialmente mejorar el rendimiento cuando se trabaja en columnas con alta cardinalidad.

    La consulta siguiente usa `summarize` para contar una dirección de correo electrónico de destinatario distinta, que se puede ejecutar en los cientos de miles de organizaciones grandes. Para mejorar el rendimiento, incorpora `hint.shufflekey`:

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```



## <a name="query-scenarios"></a>Escenarios de consulta

### <a name="identify-unique-processes-with-process-ids"></a>Identificación de procesos únicos con identificadores de proceso

Los Id. de proceso (PID) se reciclan en Windows y se reutilizan para los nuevos procesos. Por sí solos, no pueden servir como identificadores únicos para procesos específicos.

Para obtener un identificador único para un proceso en un equipo específico, utilice el Id. de proceso conjuntamente con la hora de creación del proceso. Cuando se une a los datos en torno a los procesos, debe incluir columnas para el identificador de la máquina (tanto `DeviceId` como `DeviceName`), el identificador de proceso (`ProcessId` o `InitiatingProcessId`) y la hora de creación del proceso (`ProcessCreationTime` o `InitiatingProcessCreationTime`).

En la siguiente consulta de ejemplo se buscan procesos que obtienen acceso a más de 10 direcciones IP por el puerto 445 (SMB), lo que podría buscar recursos compartidos de archivos.

Consulta de ejemplo:

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

La consulta resume tanto en `InitiatingProcessId` como en `InitiatingProcessCreationTime` para que se vea un único proceso, sin mezclar varios procesos con el mismo Id. de proceso.

### <a name="query-command-lines"></a>Líneas de comandos de consulta
Hay varias formas de crear una línea de comandos para llevar a cabo una tarea. Por ejemplo, un atacante podría hacer referencia a un archivo de imagen sin una ruta de acceso, sin una extensión de archivo, usando variables de entorno o entre comillas. El atacante también podría cambiar el orden de los parámetros o agregar varias comillas y espacios.

Para crear consultas más duraderas en torno a las líneas de comandos, aplique las siguientes prácticas:

- Identifique los procesos conocidos (como *net.exe* o *psexec.exe*) mediante la coincidencia en los campos de nombre de archivo, en lugar de filtrar en la propia línea de comandos.
- Análisis de secciones de línea de comandos mediante la [función parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line)
- Al consultar argumentos de la línea de comandos, no busque una coincidencia exacta en varios argumentos no relacionados en un orden determinado. En su lugar, use expresiones regulares o use operadores de contenedores separados múltiples.
- Use coincidencias que no distinga mayúsculas de minúsculas. Por ejemplo, use `=~`, `in~`y `contains` en lugar de `==`, `in`y `contains_cs`.
- Para mitigar las técnicas de ofuscación de línea de comandos, considere la posibilidad de quitar comillas, reemplazar comas por espacios y reemplazar varios espacios consecutivos por un solo espacio. Hay técnicas de ofuscación más complejas que requieren otros enfoques, pero estos ajustes pueden ayudar a abordar los más comunes.

En los ejemplos siguientes se muestran varias maneras de construir una consulta que busca el archivo *net.exe* para detener el servicio de firewall "MpsSvc":

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc"

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc"
```

### <a name="ingest-data-from-external-sources"></a>Ingesta de datos de orígenes externos
Para incorporar listas largas o tablas grandes en la consulta, use el [operador externaldata](/azure/data-explorer/kusto/query/externaldata-operator) para ingerir datos de un URI especificado. Puede obtener datos de archivos en TXT, CSV, JSON u [otros formatos](/azure/data-explorer/ingestion-supported-formats). En el ejemplo siguiente se muestra cómo puede usar la amplia lista de hashes SHA-256 de malware proporcionados por MalwareBazaar (abuse.ch) para comprobar los datos adjuntos en los correos electrónicos:

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string)
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo
| where Timestamp > ago(1d)
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,ThreatTypes,DetectionMethods
```

### <a name="parse-strings"></a>Análisis de cadenas
Hay varias funciones que puede usar para controlar de forma eficaz las cadenas que necesitan análisis o conversión.

| Cadena | Función | Ejemplo de uso |
|--|--|--|
| Líneas de comandos | [parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line) | Extraiga el comando y todos los argumentos. |
| Paths | [parse_path()](/azure/data-explorer/kusto/query/parsepathfunction) | Extraiga las secciones de una ruta de acceso de archivo o carpeta. |
| Números de versión | [parse_version()](/azure/data-explorer/kusto/query/parse-versionfunction) | Deconstruye un número de versión con hasta cuatro secciones y hasta ocho caracteres por sección. Use los datos analizados para comparar la antigüedad de la versión. |
| Direcciones IPv4 | [parse_ipv4()](/azure/data-explorer/kusto/query/parse-ipv4function) | Convierta una dirección IPv4 en un entero largo. Para comparar direcciones IPv4 sin convertirlos, use [ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| Direcciones IPv6 | [parse_ipv6()](/azure/data-explorer/kusto/query/parse-ipv6function)  | Convierta una dirección IPv4 o IPv6 en la notación IPv6 canónica. Para comparar direcciones IPv6, use [ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Para obtener información sobre todas las funciones de análisis admitidas, [lea acerca de las funciones de cadena de Kusto](/azure/data-explorer/kusto/query/scalarfunctions#string-functions).

>[!NOTE]
>Es posible que algunas tablas de este artículo no estén disponibles en Microsoft Defender para punto de conexión. [Active Microsoft 365 Defender](m365d-enable.md) para buscar amenazas mediante más orígenes de datos. Para mover los flujos de trabajo de búsqueda avanzados de Microsoft Defender para punto de conexión a Microsoft 365 Defender, siga los pasos descritos en [Migración de consultas de búsqueda avanzadas desde Microsoft Defender para punto de conexión](advanced-hunting-migrate-from-mde.md) .

## <a name="related-topics"></a>Temas relacionados
- [Documentación del lenguaje de consulta de Kusto](/azure/data-explorer/kusto/query/)
- [Parámetros de uso y cuotas](advanced-hunting-limits.md)
- [Controlar errores de búsqueda avanzados](advanced-hunting-errors.md)
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)