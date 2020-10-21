---
title: Procedimientos recomendados de consulta de caza avanzada en protección contra amenazas de Microsoft
description: Obtenga información sobre cómo crear consultas de búsqueda de amenazas rápidas, eficientes y sin errores con la búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, esquema, kusto, evitar tiempo de espera, líneas de comandos, identificador de proceso, optimizar, procedimientos recomendados, analizar, unirse, Resumen
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
ms.openlocfilehash: 29e5eb64445c6c5c45b8e1fd1633c030b5f32b86
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649672"
---
# <a name="advanced-hunting-query-best-practices"></a>Prácticas recomendadas para la consulta de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

Aplique estas recomendaciones para obtener resultados con mayor rapidez y evitar Tiempos de espera mientras se ejecutan consultas complejas. Para obtener más información sobre cómo mejorar el rendimiento de las consultas, vea [procedimientos recomendados de consulta de Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-quotas"></a>Descripción de las cuotas de recursos de CPU
Según su tamaño, cada inquilino tiene acceso a una cantidad fija de recursos de CPU asignados para ejecutar consultas de búsqueda avanzada. Para obtener información detallada acerca de los distintos límites de servicio, [Lea acerca de las cuotas de caza avanzadas y los parámetros de uso](advanced-hunting-limits.md).

Los clientes que ejecutan varias consultas con regularidad deben realizar un seguimiento del consumo y aplicar la guía de optimización de este artículo para minimizar la interrupción derivada de la superación de las cuotas o los parámetros de uso.

## <a name="general-optimization-tips"></a>Sugerencias generales de optimización

- **Cambiar el tamaño de nuevas consultas**: Si sospecha que una consulta devolverá un conjunto de resultados grande, evalúelo primero usando el [operador de recuento](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator). Use [Limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) o su sinónimo `take` para evitar conjuntos de resultados grandes.
- **Aplicar filtros al principio**: Aplique filtros de tiempo y otros filtros para reducir el conjunto de datos, especialmente antes de utilizar las funciones de transformación y análisis, como [substring ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [Replace ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [Trim ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [ToUpper ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)o [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). En el ejemplo siguiente, se usa la función de análisis [extractjson ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) después de que los operadores de filtrado hayan reducido el número de registros.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Tiene pulsaciones de pulsaciones**: para evitar buscar subcadenas dentro de palabras de forma innecesaria, use el `has` operador en lugar de `contains` . [Obtener información sobre los operadores de cadena](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Buscar en columnas específicas**: Busque en una columna específica en lugar de ejecutar las búsquedas de texto completo en todas las columnas. No use `*` para comprobar todas las columnas.
- Distinción entre mayúsculas y minúsculas **para la velocidad**: las búsquedas con distinción de mayúsculas y minúsculas son más específicas y generalmente son más ejecutables. Nombres de [operadores de cadena](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)con distinción entre mayúsculas y minúsculas, como `has_cs` y `contains_cs` , normalmente terminan con `_cs` . También puede usar el operador Equals con distinción entre mayúsculas y minúsculas `==` en lugar de `=~` .
- **Analice, no extraiga**: siempre que sea posible, use el [operador](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) de análisis o una función de análisis como [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). Evite el `matches regex` operador de cadena o la [función Extract ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), ambos utilizan una expresión regular. Reserve el uso de la expresión regular para escenarios más complejos. [Obtenga más información sobre las funciones de análisis](#parse-strings)
- **Filtrar tablas no expresiones**: no filtrar por una columna calculada si puede filtrar por una columna de tabla.
- **No hay términos de tres caracteres**: Evite comparar o filtrar con términos con tres caracteres o menos. Estos términos no se indizan y coinciden con ellos se necesitan más recursos.
- **Proyecto**de forma selectiva: haga que los resultados sean más fáciles de entender al proyectar solo las columnas que necesite. La proyección de columnas específicas antes de la ejecución de [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) o de operaciones similares también ayuda a mejorar el rendimiento.

## <a name="optimize-the-join-operator"></a>Optimizar el `join` operador
El [operador join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) combina filas de dos tablas haciendo coincidir los valores de las columnas especificadas. Aplique estas sugerencias para optimizar las consultas que usan este operador.

- **Tabla más pequeña a la izquierda**: el `join` operador hace coincidir los registros de la tabla del lado izquierdo de la instrucción join con los registros de la derecha. Si la tabla es más pequeña en la parte izquierda, será necesario hacer coincidir menos registros, lo que acelerará la consulta. 

    En la tabla siguiente, se reduce la tabla izquierda `DeviceLogonEvents` para abarcar solo tres dispositivos específicos antes de unirse a ellos con los `IdentityLogonEvents` SID de la cuenta.
 
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

- **Use el sabor de combinación interna (INNER-JOIN**): el [sabor de Unión](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) predeterminado o la [innerunique](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) desduplica las filas de la tabla izquierda por la clave de combinación antes de devolver una fila por cada coincidencia con la tabla derecha. Si la tabla izquierda tiene varias filas con el mismo valor para la `join` clave, esas filas se desduplicarán para dejar una única fila aleatoria para cada valor único.

    Este comportamiento predeterminado puede dejar información importante de la tabla izquierda que puede proporcionar una visión útil. Por ejemplo, la siguiente consulta solo mostrará un mensaje de correo electrónico que contiene datos adjuntos en particular, incluso si los mismos datos adjuntos se enviaron con varios mensajes de correo electrónico:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Para solucionar esta limitación, se aplica el sabor [de combinación interna](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) especificando `kind=inner` para mostrar todas las filas de la tabla izquierda con valores coincidentes en el lado derecho:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Unir registros desde una ventana de tiempo**: Cuando investiga los eventos de seguridad, los analistas buscan eventos relacionados que se producen en el mismo período de tiempo. Aplicar el mismo enfoque al usar `join` también el rendimiento de los beneficios mediante la reducción del número de registros que se van a comprobar.
    
    La consulta siguiente comprueba los eventos de inicio de sesión en un plazo de 30 minutos desde la recepción de un archivo malintencionado:

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where MalwareFilterVerdict == "Malware" 
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **Aplicar filtros de tiempo en ambos lados**: incluso si no está investigando un período de tiempo específico, la aplicación de filtros de tiempo en las tablas izquierda y derecha puede reducir el número de registros que se van a comprobar y mejorar el `join` rendimiento. La siguiente consulta se aplica `Timestamp > ago(1h)` a ambas tablas para que solo se unan a los registros de la hora pasada:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Usar sugerencias de rendimiento**: Use sugerencias con el `join` operador para indicar al back-end que distribuya la carga cuando se ejecuten operaciones que consumen muchos recursos. [Obtenga más información sobre sugerencias de combinación](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Por ejemplo, la **[sugerencia de orden aleatorio](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** ayuda a mejorar el rendimiento de las consultas al unir tablas con una clave con alta cardinalidad (una clave con muchos valores únicos), como `AccountObjectId` en la siguiente consulta:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    La **[sugerencia de difusión](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** ayuda a cuando la tabla izquierda es pequeña (hasta 100.000 registros) y la tabla derecha es muy grande. Por ejemplo, la siguiente consulta es intentar unirse a algunos correos electrónicos que tienen temas específicos con _todos_ los mensajes que contienen vínculos en la `EmailUrlInfo` tabla:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Optimizar el `summarize` operador
El [operador de Resumen](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) agrega el contenido de una tabla. Aplique estas sugerencias para optimizar las consultas que usan este operador.

- **Buscar valores distintos**: en general, use `summarize` para buscar valores distintos que pueden ser repetitivos. Puede ser innecesario usarlo para agregar columnas que no tienen valores repetitivos.

    Aunque un único correo electrónico puede formar parte de varios eventos, el ejemplo siguiente _no_ es un uso eficaz de `summarize` porque un identificador de mensaje de red para un correo electrónico individual siempre incluye una dirección de remitente única.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    El `summarize` operador se puede reemplazar fácilmente con `project` , con lo que se obtienen los mismos resultados al consumir menos recursos:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    El siguiente ejemplo es un uso más eficiente de `summarize` porque puede haber varias instancias distintas de una dirección de remitente que envíe correo electrónico a la misma dirección del destinatario. Estas combinaciones son menos claras y es probable que tengan duplicados.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Orden aleatorio de la consulta**: mientras que la `summarize` mejor opción se usa en columnas con valores repetitivos, las mismas columnas también pueden tener _alta cardinalidad_ o gran número de valores únicos. Al igual que el `join` operador, también puede aplicar la [sugerencia de orden aleatorio](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) con `summarize` para distribuir la carga de procesamiento y, potencialmente, mejorar el rendimiento cuando opere en columnas con alta cardinalidad.

    La siguiente consulta usa `summarize` para contar distintas direcciones de correo electrónico de destinatarios, que se pueden ejecutar en cientos de miles de organizaciones de gran tamaño. Para mejorar el rendimiento, incorpora lo `hint.shufflekey` siguiente:

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
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

La consulta resume tanto en `InitiatingProcessId` como en `InitiatingProcessCreationTime` para que se vea un único proceso, sin mezclar varios procesos con el mismo Id. de proceso.

### <a name="query-command-lines"></a>Líneas de comandos de consulta
Hay varias formas de crear una línea de comandos para llevar a cabo una tarea. Por ejemplo, un atacante puede hacer referencia a un archivo de imagen sin una ruta de acceso, sin extensión de archivo, mediante variables de entorno o con comillas. El atacante también puede cambiar el orden de los parámetros o agregar varias comillas y espacios.

Para crear consultas más duraderas alrededor de líneas de comandos, aplique los siguientes procedimientos:

- Identificar los procesos conocidos (como *net.exe* o *psexec.exe*) haciendo coincidir en los campos de nombre de archivo, en lugar de filtrarse en la línea de comandos.
- Análisis de secciones de la línea de comandos mediante la [función parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- Al consultar argumentos de la línea de comandos, no busque una coincidencia exacta en varios argumentos no relacionados en un orden determinado. En su lugar, use expresiones regulares o use operadores de contenedores separados múltiples.
- Use coincidencias que no distinga mayúsculas de minúsculas. Por ejemplo, use `=~` , `in~` , y `contains` en lugar de `==` , `in` y `contains_cs` .
- Para mitigar las técnicas de ofuscación de línea de comandos, considere la posibilidad de quitar comillas, reemplazar comas por espacios y reemplazar varios espacios consecutivos por un solo espacio. Hay técnicas de ofuscación más complejas que requieren otros enfoques, pero estos ajustes pueden ayudar a abordar los más comunes.

En los ejemplos siguientes se muestran varias formas de crear una consulta que busque el archivo *net.exe* para detener el servicio de firewall "MpsSvc":

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

### <a name="ingest-data-from-external-sources"></a>Datos de introducción de orígenes externos
Para incorporar listas largas o grandes tablas a la consulta, use el [operador externaldata](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) para recopilar datos de un URI especificado. Puede obtener datos de archivos en formato TXT, CSV, JSON u [otros formatos](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats). En el ejemplo siguiente se muestra cómo puede usar la amplia lista de hash de malware SHA-256 que proporciona MalwareBazaar (abuse.ch) para comprobar los datos adjuntos en los correos electrónicos:

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,MalwareFilterVerdict,MalwareDetectionMethod
```

### <a name="parse-strings"></a>Analizar cadenas
Hay varias funciones que se pueden usar para controlar eficazmente las cadenas que se deben analizar o convertir. 

| Cadena | Función | Ejemplo de uso |
|--|--|--|
| Líneas de comandos | [parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | Extraiga el comando y todos los argumentos. | 
| Paths | [parse_path ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | Extraiga las secciones de una ruta de acceso de archivo o carpeta. |
| Números de versión | [parse_version ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Desconstruya un número de versión con un máximo de cuatro secciones y hasta ocho caracteres por sección. Use los datos analizados para comparar la antigüedad de la versión. |
| Direcciones IPv4 | [parse_ipv4 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | Convertir una dirección IPv4 en un entero largo. Para comparar direcciones IPv4 sin convertirlas, use [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| Direcciones IPv6 | [parse_ipv6 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | Convertir una dirección IPv4 o IPv6 en la notación IPv6 canónica. Para comparar direcciones IPv6, use [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Para obtener información sobre todas las funciones de análisis admitidas, [Lea about Kusto String Functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions). 

## <a name="related-topics"></a>Temas relacionados
- [Documentación del lenguaje de consulta de Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [Cuotas y parámetros de uso](advanced-hunting-limits.md)
- [Controlar errores de búsqueda avanzada](advanced-hunting-errors.md)
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
