---
title: Obtener formación de expertos sobre la búsqueda avanzada
description: Formación gratuita y orientación de expertos en búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, idioma, aprendizaje, escenarios, básico a avanzado, vídeos, paso a paso
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
ms.openlocfilehash: aba0a6ab2c82c038eda8e66890c0c95303dea947
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053840"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Obtener formación de expertos sobre la búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Aumente su conocimiento de la búsqueda avanzada rápidamente con El seguimiento del _adversario,_ una serie de difusión por web para nuevos analistas de seguridad y agentes de amenazas expertos. La serie le guiará a través de los conceptos básicos hasta la creación de sus propias consultas sofisticadas. Empieza con el primer vídeo sobre conceptos básicos o salta a vídeos más avanzados que se adapten a tu nivel de experiencia.


| El título | Description | Reloj | Consultas | 
|--|--|--|--|
| Episodio 1: Conceptos básicos de KQL | En este episodio se tratan los conceptos básicos de la búsqueda avanzada en Microsoft 365 Defender. Obtenga información sobre los datos de búsqueda avanzada disponibles y la sintaxis y los operadores básicos de KQL. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [Archivo CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Episodio 2: Combinaciones | Continúe con el aprendizaje sobre los datos en la búsqueda avanzada y sobre cómo unir tablas. Obtenga información sobre , y las combinaciones, y comprenda los matices de la unión `inner` `outer` predeterminada a `unique` `semi` Kusto. `innerunique` | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [Archivo CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Episodio 3: Resumir, pivotar y visualizar datos | Ahora que ha aprendido a filtrar, manipular y unir datos, es el momento de resumir, cuantificar, pivotar y visualizar. En este episodio se analiza el operador y varios cálculos, a la vez que se introducen tablas `summarize` adicionales en el esquema. También aprenderá a convertir conjuntos de datos en gráficos que pueden ayudarle a extraer información. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [Archivo CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Episodio 4: ¡Vamos a buscar! Aplicación de KQL al seguimiento de incidentes | En este episodio, aprenderás a realizar un seguimiento de alguna actividad de atacante. Usamos nuestra comprensión mejorada de Kusto y la búsqueda avanzada para realizar un seguimiento de un ataque. Obtenga información sobre los trucos reales usados en el campo, incluidos los ABC de ciberseguridad y cómo aplicarlos a la respuesta a incidentes. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [Archivo CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) 


Obtenga más formación de expertos con *L33TSP3AK:* búsqueda avanzada en Microsoft 365 Defender , una serie de difusión por web para analistas que buscan ampliar sus conocimientos técnicos y habilidades prácticas para llevar a cabo investigaciones de seguridad mediante la búsqueda avanzada en Microsoft 365 Defender. 

| El título | Description | Reloj | Consultas | 
|--|--|--|--|
| Episodio 1  | En este episodio, aprenderás diferentes procedimientos recomendados para ejecutar consultas de búsqueda avanzada. Entre los temas tratados se encuentran: cómo optimizar las consultas, usar la búsqueda avanzada para ransomware, controlar JSON como un tipo dinámico y trabajar con operadores de datos externos. | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56:34) | [Archivo CSL](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.csl)


## <a name="how-to-use-the-csl-file"></a>Cómo usar el archivo CSL
Antes de iniciar un episodio, accede al archivo [Kusto CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) correspondiente en GitHub y copia su contenido en el editor de consultas de búsqueda avanzada. Al ver un episodio, puede usar el contenido copiado para seguir al orador y ejecutar consultas. 

El siguiente fragmento de un archivo CSL muestra un conjunto completo de instrucciones marcadas como comentarios con `//` .

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

El mismo archivo CSL incluye consultas antes y después de los comentarios, como se muestra a continuación. Para ejecutar una consulta específica con varias consultas en el [editor,](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)mueva el cursor a esa consulta y seleccione **Ejecutar consulta**.   

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
