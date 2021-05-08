---
title: Obtener formación de expertos sobre la búsqueda avanzada
description: Formación gratuita y orientación de expertos avanzados en la caza
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, idioma, aprendizaje, escenarios, básico a avanzado, vídeos, paso a paso
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
ms.technology: m365d
ms.openlocfilehash: 136e7cba26d55676fdf3b3b7f0f9ef967e7d7991
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245833"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Obtener formación de expertos sobre la búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

Aumente su conocimiento de la búsqueda avanzada rápidamente con _Tracking the adversary_, una serie de difusión por web para nuevos analistas de seguridad y cazacarros de amenazas expertos. La serie le guía a través de los conceptos básicos hasta la creación de sus propias consultas sofisticadas. Empieza con el primer vídeo sobre conceptos básicos o salta a vídeos más avanzados que se adapten a tu nivel de experiencia.

| Title | Descripción | Reloj | Consultas | 
|--|--|--|--|
| Episodio 1: Conceptos básicos de KQL | Este episodio trata los conceptos básicos de la búsqueda avanzada en Microsoft 365 Defender. Obtenga información sobre los datos de búsqueda avanzados disponibles y la sintaxis y los operadores básicos de KQL. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [Archivo de texto](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.txt) |
| Episodio 2: Combinaciones | Siga aprendiendo sobre los datos en la búsqueda avanzada y cómo unir tablas. Obtenga información `inner` sobre , , y `outer` `unique` combinaciones, y comprenda los `semi` matices de la combinación predeterminada de Kusto. `innerunique` | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [Archivo de texto](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.txt) |
| Episodio 3: Resumen, pivotación y visualización de datos | Ahora que ha aprendido a filtrar, manipular y unir datos, es hora de resumir, cuantificar, pivotar y visualizar. En este episodio se analiza el operador y varios cálculos, al tiempo que se presentan tablas `summarize` adicionales en el esquema. También aprenderá a convertir conjuntos de datos en gráficos que pueden ayudarle a extraer información. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [Archivo de texto](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.txt) |
| Episodio 4: Vamos a cazar. Aplicación de KQL al seguimiento de incidentes | En este episodio, aprenderás a realizar un seguimiento de alguna actividad de atacante. Usamos nuestra mejor comprensión de Kusto y la búsqueda avanzada para realizar un seguimiento de un ataque. Obtenga información sobre los trucos reales usados en el campo, incluidos los ABC de ciberseguridad y cómo aplicarlos a la respuesta a incidentes. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [Archivo de texto](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.txt) 


Obtenga más formación de expertos con *L33TSP3AK:* Búsqueda avanzada en Microsoft 365 Defender, una serie de difusión por web para analistas que buscan expandir sus conocimientos técnicos y habilidades prácticas en la realización de investigaciones de seguridad mediante la búsqueda avanzada en Microsoft 365 Defender. 

| Title | Descripción | Reloj | Consultas | 
|--|--|--|--|
| Episodio 1  | En este episodio, aprenderás diferentes procedimientos recomendados para ejecutar consultas avanzadas de búsqueda. Entre los temas tratados se encuentran: cómo optimizar las consultas, usar la búsqueda avanzada para ransomware, controlar JSON como un tipo dinámico y trabajar con operadores de datos externos. | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56:34) | [Archivo de texto](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.txt)


## <a name="how-to-use-the-csl-file"></a>Cómo usar el archivo CSL
Antes de iniciar un episodio, acceda al archivo de texto correspondiente [en GitHub](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/tree/master/Webcasts) y copie su contenido en el editor de consultas de búsqueda avanzada. Al ver un episodio, puede usar el contenido copiado para seguir el altavoz y ejecutar consultas. 

El siguiente fragmento de un archivo de texto que contiene las consultas muestra un conjunto completo de instrucciones marcadas como comentarios con `//` .

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

El mismo archivo de texto incluye consultas antes y después de los comentarios como se muestra a continuación. Para ejecutar una consulta específica con [varias consultas en el editor,](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)mueva el cursor a esa consulta y seleccione Ejecutar **consulta**.   

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
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Conozca el lenguaje de consulta de búsqueda avanzada](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
