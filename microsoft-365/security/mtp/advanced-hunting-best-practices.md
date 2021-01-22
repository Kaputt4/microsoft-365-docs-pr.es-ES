---
title: Procedimientos recomendados de consulta de búsqueda avanzada en Microsoft 365 Defender
description: Obtenga información sobre cómo crear consultas de búsqueda de amenazas rápidas, eficientes y sin errores con la búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, esquema, kusto, evitar tiempo de espera, líneas de comandos, id. de proceso, optimizar, procedimiento recomendado, analizar, unirse, resumir
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
ms.technology: m365d
ms.openlocfilehash: cc6110cdd7dd71f80f6897cfbb0026ccce301cf7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928479"
---
# <a name="advanced-hunting-query-best-practices"></a>Prácticas recomendadas para la consulta de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Aplique estas recomendaciones para obtener resultados más rápidos y evitar tiempos de espera mientras ejecuta consultas complejas. Para obtener más información sobre cómo mejorar el rendimiento de las consultas, vea [procedimientos recomendados de consulta de Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-quotas"></a>Comprender las cuotas de recursos de CPU
Según su tamaño, cada inquilino tiene acceso a una cantidad establecida de recursos de CPU asignados para ejecutar consultas de búsqueda avanzada. Para obtener información detallada acerca de los distintos límites de servicio, [lea acerca de las cuotas de búsqueda avanzada y los parámetros de uso.](advanced-hunting-limits.md)

Los clientes que ejecutan varias consultas con regularidad deben realizar un seguimiento del consumo y aplicar las instrucciones de optimización de este artículo para minimizar las interrupciones resultantes de la superación de cuotas o parámetros de uso.

## <a name="general-optimization-tips"></a>Sugerencias generales de optimización

- **Tamaño de las consultas nuevas:** si sospecha que una consulta devolverá un conjunto de resultados grande, evalúe primero con el operador [de recuento.](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator) Use [el límite](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) o su sinónimo para evitar grandes conjuntos de `take` resultados.
- Aplicar filtros de forma anticipada: aplique filtros de tiempo y otros filtros para reducir el conjunto de datos, especialmente antes de usar funciones de transformación y análisis, como [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)o [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). En el ejemplo siguiente, se usa la función de análisis [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) después de que los operadores de filtrado han reducido el número de registros.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Contiene latidos:** para evitar buscar subcadenas en palabras innecesariamente, use el `has` operador en lugar de `contains` . [Más información sobre los operadores de cadena](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Buscar en columnas específicas:** busque en una columna específica en lugar de ejecutar búsquedas de texto completo en todas las columnas. No se usa `*` para comprobar todas las columnas.
- **Distingue mayúsculas de minúsculas para la** velocidad: las búsquedas que distinguen mayúsculas de minúsculas son más específicas y, por lo general, más avanzadas. Los nombres de operadores de [cadena](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)que distinguen mayúsculas de minúsculas, `has_cs` como y , generalmente terminan con `contains_cs` `_cs` . También puede usar el operador que distingue mayúsculas de minúsculas en `==` lugar de `=~` .
- **Analizar, no extraer:** siempre que sea [](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) posible, use el operador de análisis o una función de análisis [como parse_json().](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction) Evite el `matches regex` operador de cadena o la función [extract(),](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)que usan expresiones regulares. Reserve el uso de expresiones regulares para escenarios más complejos. [Más información sobre el análisis de funciones](#parse-strings)
- **Tablas de filtro no expresiones:** no filtre en una columna calculada si puede filtrar por una columna de tabla.
- **Sin términos de tres caracteres:** evite comparar o filtrar usando términos con tres caracteres o menos. Estos términos no se indizan y su coincidencia requerirá más recursos.
- **Proyecto selectivamente:** haga que los resultados sean más fáciles de entender proyectando solo las columnas que necesita. La proyección de columnas específicas antes de ejecutar [la combinación](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) u operaciones similares también ayuda a mejorar el rendimiento.

## <a name="optimize-the-join-operator"></a>Optimizar el `join` operador
El [operador join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) combina filas de dos tablas mediante valores coincidentes en columnas especificadas. Aplique estas sugerencias para optimizar las consultas que usan este operador.

- **Tabla más pequeña a la izquierda:** el operador hace que los registros de la tabla del lado izquierdo de la instrucción join coincidan con `join` los registros de la derecha. Al tener la tabla más pequeña a la izquierda, será necesario hacer coincidir menos registros, lo que acelerará la consulta. 

    En la tabla siguiente, se reduce la tabla izquierda para cubrir solo tres dispositivos específicos antes de `DeviceLogonEvents` unirse por `IdentityLogonEvents` SID de cuenta.
 
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

- **Use** el tipo de combinación [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) interna: el tipo de combinación predeterminado o [la](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) combinación interna desduplica las filas de la tabla izquierda por la tecla de combinación antes de devolver una fila para cada coincidencia a la tabla derecha. Si la tabla izquierda tiene varias filas con el mismo valor para la clave, dichas filas se desduplicarán para dejar una sola fila aleatoria `join` para cada valor único.

    Este comportamiento predeterminado puede dejar fuera información importante de la tabla izquierda que puede proporcionar información útil. Por ejemplo, la consulta siguiente solo mostrará un correo electrónico que contiene datos adjuntos concretos, incluso si el mismo archivo adjunto se envió con varios mensajes de correo electrónico:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Para solucionar esta limitación, aplicamos el tipo de combinación interna especificando que se muestren todas las filas de la tabla izquierda con valores coincidentes a la [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) `kind=inner` derecha:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Unir registros desde una ventana de tiempo:** al investigar eventos de seguridad, los analistas buscan eventos relacionados que se producen alrededor del mismo período de tiempo. Aplicar el mismo enfoque al usar también `join` beneficia el rendimiento al reducir el número de registros que se deben comprobar.
    
    La siguiente consulta comprueba si hay eventos de inicio de sesión en un plazo de 30 minutos desde la recepción de un archivo malintencionado:

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
- **Aplicar** filtros de tiempo en ambos lados: incluso si no está investigando una ventana de tiempo específica, la aplicación de filtros de tiempo en las tablas izquierda y derecha puede reducir el número de registros para comprobar y mejorar el `join` rendimiento. La consulta siguiente se aplica a ambas tablas para que solo `Timestamp > ago(1h)` una registros de la última hora:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Usa sugerencias para el rendimiento:** usa sugerencias con el operador para indicar al back-end que distribuya la carga al ejecutar operaciones `join` que consumen muchos recursos. [Más información sobre las sugerencias de unión](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Por ejemplo, **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** la sugerencia de aleatorio ayuda a mejorar el rendimiento de las consultas al unir tablas con una clave con una cardinalidad alta (una clave con muchos valores únicos), como la de la `AccountObjectId` consulta siguiente:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    La **[sugerencia de](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** difusión ayuda cuando la tabla izquierda es pequeña (hasta 100.000 registros) y la tabla derecha es extremadamente grande. Por ejemplo, la consulta siguiente está intentando unirse  a algunos correos electrónicos que tienen asuntos específicos con todos los mensajes que contienen vínculos en la `EmailUrlInfo` tabla:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Optimizar el `summarize` operador
El [operador de resumen](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) agrega el contenido de una tabla. Aplica estas sugerencias para optimizar las consultas que usan este operador.

- **Buscar valores distintos:** en general, se usan para buscar valores `summarize` distintos que pueden ser repetitivos. No es necesario usarlo para agregar columnas que no tienen valores repetitivos.

    Aunque un solo correo electrónico puede formar parte  de varios eventos, el ejemplo siguiente no es un uso eficaz porque un identificador de mensaje de red para un correo electrónico individual siempre incluye una dirección `summarize` de remitente única.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    El operador se puede reemplazar fácilmente por , lo que produce potencialmente los mismos resultados `summarize` mientras consume menos `project` recursos:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    El siguiente ejemplo es un uso más eficaz porque puede haber varias instancias distintas de una dirección de remitente que envía correo electrónico `summarize` a la misma dirección de destinatario. Estas combinaciones son menos distintas y es probable que tengan duplicados.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Aleatorio de la consulta:** aunque se usa mejor en columnas con valores repetitivos, las mismas columnas también pueden tener una gran cardinalidad o un gran número `summarize` de valores  únicos. Al igual que el operador, también puedes aplicar la sugerencia de reproducción aleatoria para distribuir la carga de procesamiento y mejorar potencialmente el rendimiento cuando se opera en columnas `join` con una [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` cardinalidad alta.

    La consulta siguiente se usa para contar una dirección de correo electrónico de destinatario distinta, que puede ejecutarse `summarize` en los cientos de miles de organizaciones grandes. Para mejorar el rendimiento, `hint.shufflekey` incorpora:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Escenarios de consulta

### <a name="identify-unique-processes-with-process-ids"></a>Identificar procesos únicos con identificadores de proceso
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
Hay varias formas de crear una línea de comandos para llevar a cabo una tarea. Por ejemplo, un atacante podría hacer referencia a un archivo de imagen sin una ruta de acceso, sin una extensión de archivo, usando variables de entorno o entre comillas. El atacante también podría cambiar el orden de los parámetros o agregar varias comillas y espacios.

Para crear consultas más duraderas en torno a las líneas de comandos, aplique los siguientes procedimientos:

- Identifique los procesos conocidos (como *net.exe* o *psexec.exe)* haciendo coincidir en los campos de nombre de archivo, en lugar de filtrarlos en la propia línea de comandos.
- Analizar secciones de línea de comandos mediante [la parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- Al consultar argumentos de la línea de comandos, no busque una coincidencia exacta en varios argumentos no relacionados en un orden determinado. En su lugar, use expresiones regulares o use operadores de contenedores separados múltiples.
- Use coincidencias que no distinga mayúsculas de minúsculas. Por ejemplo, use `=~` , y en lugar de , y `in~` `contains` `==` `in` `contains_cs` .
- Para mitigar las técnicas de ofuscación de la línea de comandos, considere la posibilidad de quitar comillas, reemplazar comas por espacios y reemplazar varios espacios consecutivos por un solo espacio. Existen técnicas de ofuscación más complejas que requieren otros enfoques, pero estos retoques pueden ayudar a abordar los más comunes.

Los ejemplos siguientes muestran varias formas de crear una consulta que busca el archivo *net.exe* para detener el servicio de firewall "MpsSvc":

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

### <a name="ingest-data-from-external-sources"></a>Ingerir datos de orígenes externos
Para incorporar listas largas o tablas grandes en la consulta, use el operador [externaldata](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) para ingerir datos de un URI especificado. Puede obtener datos de archivos en formato TXT, CSV, JSON u [otros formatos.](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats) En el siguiente ejemplo se muestra cómo puede usar la amplia lista de hash sha-256 de malware proporcionado por MalwareBazaar (abuse.ch) para comprobar los datos adjuntos de los correos electrónicos:

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
Hay varias funciones que puedes usar para controlar de forma eficaz las cadenas que necesitan análisis o conversión. 

| Cadena | Función | Ejemplo de uso |
|--|--|--|
| Líneas de comandos | [parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | Extraiga el comando y todos los argumentos. | 
| Paths | [parse_path()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | Extraiga las secciones de una ruta de acceso de archivo o carpeta. |
| Números de versión | [parse_version()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Deconstruye un número de versión con hasta cuatro secciones y hasta ocho caracteres por sección. Use los datos analizados para comparar la antigüedad de la versión. |
| Direcciones IPv4 | [parse_ipv4()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | Convertir una dirección IPv4 en un entero largo. Para comparar direcciones IPv4 sin convertirlas, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| Direcciones IPv6 | [parse_ipv6()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | Convierte una dirección IPv4 o IPv6 en la notación IPv6 canónica. Para comparar direcciones IPv6, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Para obtener información sobre todas las funciones de análisis admitidas, [lea acerca de las funciones de cadena de Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions). 

## <a name="related-topics"></a>Temas relacionados
- [Documentación del lenguaje de consulta de Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [Parámetros de uso y cuotas](advanced-hunting-limits.md)
- [Controlar errores de búsqueda avanzada](advanced-hunting-errors.md)
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
