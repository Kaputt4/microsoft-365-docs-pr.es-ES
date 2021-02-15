---
title: Diferencias entre los resultados de búsqueda de exhibición de documentos electrónicos estimados y reales
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 8f20ca4f-a908-46ec-99e6-9890d269ecf2
description: Comprenda por qué los resultados de búsqueda estimados y reales pueden variar en las búsquedas que se ejecutan con herramientas de exhibición de documentos electrónicos en Office 365.
ms.openlocfilehash: a5a66e070bf41cf6b3263dbae1e6ac5d136d9465
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760258"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results"></a>Diferencias entre los resultados de búsqueda de exhibición de documentos electrónicos estimados y reales

Este tema se aplica a las búsquedas que puede ejecutar con una de las siguientes herramientas de exhibición de documentos electrónicos de Microsoft 365: 

- Búsqueda de contenido
- Core eDiscovery 
   
Cuando ejecuta una búsqueda de exhibición de documentos electrónicos, la herramienta que está usando devolverá una estimación del número de elementos (y su tamaño total) que cumplen los criterios de búsqueda. Por ejemplo, cuando se ejecuta una búsqueda en el Centro de cumplimiento de Microsoft 365, los resultados estimados de la búsqueda se muestran en la página desplegable de la búsqueda seleccionada.
  
![Cálculo de resultados que se muestra en el panel de detalles de la búsqueda seleccionada](../media/74e4ce83-40be-41a9-b60f-5ad447e79fe4.png)
  
Esta es la misma estimación del tamaño total y el número de elementos que se muestran en la herramienta de exportación de exhibición de documentos electrónicos al exportar los resultados a un equipo local y en el informe de resumen de exportación que se descarga con los resultados de la búsqueda.
  
**Resultados estimados en la herramienta de exportación de exhibición de documentos electrónicos**

![Resultados estimados en la herramienta de exportación de exhibición de documentos electrónicos](../media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**Resultados estimados en el informe de resumen de exportación**

![Los resultados de la búsqueda estimada se incluyen en el informe de resumen de exportación](../media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
Sin embargo, como verá en la captura de pantalla anterior del informe de resumen de exportación, el tamaño y el número de resultados de búsqueda reales que se descargan son diferentes del tamaño y el número de resultados de búsqueda estimados.
  
![Diferencia entre los resultados de la búsqueda estimados y descargados](../media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
Estas son algunas de las razones de estas diferencias:
  
- **La forma en que se calculan los resultados.** Una estimación de los resultados de la búsqueda es simplemente eso, una estimación (y no un recuento real) de los elementos que cumplen los criterios de consulta de búsqueda. Para compilar la estimación de los elementos de Exchange, la herramienta de exhibición de documentos electrónicos que está usando solicita a la base de datos de Exchange una lista de los IDs de mensajes que cumplen los criterios de búsqueda. Pero al exportar los resultados de la búsqueda, la búsqueda se vuelve a ejecutar y los mensajes reales se recuperan de la base de datos de Exchange. Por lo tanto, estas diferencias pueden deber a cómo se determina el número estimado de elementos y el número real de elementos.

- **Cambios que se produce entre el momento en que se estiman y exportan los resultados de la búsqueda.** Al exportar los resultados de la búsqueda, la búsqueda se reinicia para recopilar los elementos más recientes del índice de búsqueda que cumplen los criterios de búsqueda. Es posible que haya elementos adicionales creados, enviados o recibidos que cumplan los criterios de búsqueda en el tiempo entre el momento en que se recopilaron los resultados de búsqueda estimados y el momento en que se exportaron los resultados de la búsqueda. También es posible que los elementos que estaban en el índice de búsqueda cuando se calcularon los resultados de la búsqueda ya no estén allí porque se purgaron de la ubicación de contenido antes de exportar los resultados de la búsqueda. Una forma de mitigar este problema es especificar un intervalo de fechas para una búsqueda de exhibición de documentos electrónicos. Otra forma es colocar una retención en las ubicaciones de contenido para que los elementos se conserven y no se puedan purgar. 

   Aunque rara vez, incluso cuando se aplica una retención, el mantenimiento de elementos de calendario integrados (que el usuario no puede editar, pero se incluyen en muchos resultados de búsqueda) puede quitarse de vez en cuando. Esta eliminación periódica de elementos de calendario dará como resultado menos elementos que se exportan.

- **Elementos no indexados**. Los elementos que no están indexados para la búsqueda pueden causar diferencias entre los resultados de búsqueda estimados y reales. Puede incluir elementos no indexados al exportar los resultados de la búsqueda. Si incluye elementos no indexados al exportar resultados de búsqueda, es posible que haya más elementos exportados. Esto provocará una diferencia entre los resultados de búsqueda estimados y exportados.

    Al usar la herramienta de búsqueda de contenido, tiene la opción de incluir elementos no indexados en la estimación de búsqueda. El número de elementos no indexados devueltos por la búsqueda se muestra en la página desplegable junto con los demás resultados de búsqueda estimados. Los elementos no indexados también se incluirían en el tamaño total de los resultados de búsqueda estimados. Al exportar los resultados de la búsqueda, tiene la opción de incluir o no incluir elementos no indexados. La forma en que configure estas opciones puede dar lugar a diferencias entre los resultados de búsqueda estimados y los reales que se descargan.

- **Exportar los resultados de una búsqueda de contenido que incluya todas las ubicaciones de contenido.** Si la búsqueda de la que exporta los resultados fue una búsqueda de todas las ubicaciones de contenido de la organización, solo se exportarán los elementos no indexados de las ubicaciones de contenido que contengan elementos que coincidan con los criterios de búsqueda. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. Sin embargo, los elementos no indexados de todas las ubicaciones de contenido (incluso aquellos que no contienen elementos que coinciden con la consulta de búsqueda) se incluirán en los resultados de búsqueda estimados.

    Como alternativa, si la búsqueda desde la que exporta los resultados incluye ubicaciones de contenido específicas, se exportarán los elementos no indexados (que no se excluyen por los criterios de búsqueda) de todas las ubicaciones de contenido especificadas en la búsqueda. En este caso, el número estimado de elementos no indexados y el número de elementos no indexados que se exportan deben ser los mismos.

    El motivo para no exportar elementos no indexados desde cada ubicación de la organización es porque puede aumentar la probabilidad de errores de exportación y aumentar el tiempo necesario para exportar y descargar los resultados de la búsqueda.

- **Formatos de archivo sin procesar frente a formatos de archivo exportados.** Para los elementos de Exchange, el tamaño estimado de los resultados de la búsqueda se calcula con los tamaños de los mensajes de Exchange sin procesar. Sin embargo, los mensajes de correo electrónico se exportan en un archivo PST o como mensajes individuales (que tienen formato de archivos EML). Ambas opciones de exportación usan un formato de archivo diferente al de los mensajes de Exchange sin procesar, lo que hace que el tamaño total del archivo exportado sea diferente del tamaño de archivo estimado.

- **Versiones del documento**. Para los documentos de SharePoint, no se incluyen varias versiones de un documento en los resultados de búsqueda estimados. Pero tiene la opción de incluir todas las versiones del documento al exportar los resultados de la búsqueda, lo que aumentará el número real (y el tamaño total) de los documentos exportados. 

- **Desduplicación.** Para los elementos de Exchange, la desduplicación reduce el número de elementos que se exportan. Tiene la opción de desduplicar los resultados de búsqueda al exportarlos. Para los mensajes de Exchange, esto significa que solo se exporta una instancia de un mensaje, aunque ese mensaje se pueda encontrar en varios buzones. Los resultados de búsqueda estimados incluyen todas las instancias de un mensaje. Por lo tanto, si elige la opción de desduplicación al exportar resultados de búsqueda, el número real de elementos que se exportan puede ser considerablemente menor que el número estimado de elementos.

    Otra cosa que debe tener en cuenta si elige la opción de desduplicación es que todos los elementos de Exchange se exportan en un único archivo PST y no se conserva la estructura de carpetas de los buzones de origen. El archivo PST exportado solo contiene los elementos de correo electrónico. Sin embargo, un informe de resultados de búsqueda contiene una entrada para cada mensaje exportado que identifica el buzón de origen donde se encuentra el mensaje. Esto le ayuda a identificar todos los buzones que contienen un mensaje duplicado. Si no habilita la desduplicación, se exportará un archivo PST independiente por cada buzón incluido en la búsqueda. 
 
> [!NOTE]
> Si no selecciona la  opción Incluir elementos cifrados o que tienen un formato no reconocido al exportar los resultados de la búsqueda o simplemente descargar los informes, se descargan los informes de errores de índice, pero no tienen ninguna entrada. Esto no significa que no haya errores de indización. Simplemente significa que los elementos no indexados no se incluyeron en la exportación. 
