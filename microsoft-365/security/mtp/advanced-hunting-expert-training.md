---
title: Obtener formación experta sobre la búsqueda avanzada
description: Formación gratuita y consejos de expertos en la caza avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, lenguaje, formación, escenarios, básico para avanzadas, vídeos, paso a paso
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
ms.openlocfilehash: c2772d0fc77e563bc80b0f29815349d1bfb3e2ea
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842517"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Obtener formación experta sobre la búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 defender

Mejore rápidamente sus conocimientos sobre la caza avanzada con un _seguimiento del adversario_ , una serie de difusiones por web para nuevos analistas de seguridad y Hunters de amenazas de temporada. La serie le guía a través de los conceptos básicos para crear sus propias consultas sofisticadas. Comience con el primer vídeo sobre conceptos básicos o salte a vídeos más avanzados que se adapten a su nivel de experiencia.


| El título | Description | Reloj | Queries | 
|--|--|--|--|
| Episodio 1: conceptos básicos de KQL | Este episodio cubre los conceptos básicos de la caza avanzada en Microsoft 365 defender. Obtenga información sobre los datos de búsqueda avanzada disponibles y la sintaxis y los operadores de KQL básicos. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [CSL File](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Episodio 2: combinaciones | Seguir aprendiendo sobre los datos de la búsqueda avanzada y cómo combinar tablas. Obtenga información sobre `inner` , `outer` , `unique` y `semi` las combinaciones, y comprenda los matices de la combinación Kusto predeterminada `innerunique` . | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [CSL File](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Episodio 3: resumir, dinamizar y visualizar datos | Ahora que ha aprendido a filtrar, manipular y unir datos, es el momento de resumir, cuantificar, dinamizar y visualizar. Este episodio analiza el `summarize` operador y varios cálculos, a la vez que presenta tablas adicionales en el esquema. También aprenderá a convertir los conjuntos de valores en gráficos que pueden ayudarle a extraer el conocimiento. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [CSL File](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Episodio 4: ¡ vamos a buscar! Aplicación de KQL al seguimiento de incidentes | En este episodio, aprenderá a realizar un seguimiento de la actividad del atacante. Usamos la mejor comprensión de Kusto y la búsqueda avanzada para realizar un seguimiento de un ataque. Obtenga información sobre las sugerencias reales que se usan en el campo, incluidos los ABC de Cybersecurity y cómo aplicarlas a la respuesta ante incidentes. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [CSL File](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)

## <a name="how-to-use-the-csl-file"></a>Cómo usar el archivo CSL
Antes de iniciar un episodio, obtenga acceso al [archivo KUSTO CSL correspondiente en github](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) y copie su contenido en el editor de consultas de búsqueda avanzada. Mientras observa un episodio, puede usar el contenido copiado para seguir el orador y ejecutar consultas. 

El siguiente extracto de un archivo CSL muestra un conjunto completo de instrucciones marcadas como comentarios con `//` .

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

El mismo archivo CSL incluye consultas antes y después de los comentarios, tal como se muestra a continuación. Para ejecutar una consulta específica con [varias consultas en el editor](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor), mueva el cursor a esa consulta y seleccione **Ejecutar consulta**.   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp

AppFileEvents
| take 100
| sort by Timestamp desc
```
     
## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Conozca el lenguaje de consulta de búsqueda avanzada](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
