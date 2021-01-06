---
title: Diferencias entre los resultados de búsqueda de eDiscovery estimados y reales
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
description: Comprenda por qué los resultados de búsqueda reales y estimados pueden variar en las búsquedas ejecutadas con herramientas de eDiscovery en Office 365.
ms.openlocfilehash: a5a66e070bf41cf6b3263dbae1e6ac5d136d9465
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760258"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results"></a>Diferencias entre los resultados de búsqueda de eDiscovery estimados y reales

Este tema se aplica a las búsquedas que se pueden ejecutar mediante una de las siguientes herramientas de eDiscovery de Microsoft 365: 

- Búsqueda de contenido
- eDiscovery principal 
   
Cuando se ejecuta una búsqueda de exhibición de documentos electrónicos, la herramienta que se está usando devolverá una estimación del número de elementos (y su tamaño total) que cumplan los criterios de búsqueda. Por ejemplo, cuando se ejecuta una búsqueda en el centro de cumplimiento de Microsoft 365, los resultados de la búsqueda estimados se muestran en la página flotante para la búsqueda seleccionada.
  
![Cálculo de resultados que se muestra en el panel de detalles de la búsqueda seleccionada](../media/74e4ce83-40be-41a9-b60f-5ad447e79fe4.png)
  
Esta es la misma estimación de tamaño total y número de elementos que se muestra en la herramienta de exportación de exhibición de documentos electrónicos cuando se exportan resultados a un equipo local y en el informe de Resumen de exportación que se descarga con los resultados de la búsqueda.
  
**Resultados estimados en la herramienta de exportación de exhibición de documentos electrónicos**

![Resultados estimados en la herramienta de exportación de exhibición de documentos electrónicos](../media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**Resultados estimados en el informe de Resumen de exportación**

![Los resultados de la búsqueda estimada se incluyen en el informe de resumen de exportación](../media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
Sin embargo, como verá en la captura de pantalla anterior del informe de Resumen de exportación, el tamaño y el número de resultados de búsqueda reales que se descargan son diferentes del tamaño y el número de resultados de búsqueda estimados.
  
![Diferencia entre los resultados de la búsqueda estimados y descargados](../media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
Estos son algunos de los motivos de estas diferencias:
  
- **La manera en que se calculan los resultados**. Una estimación de los resultados de la búsqueda es sólo eso, una estimación (y no un recuento real) de los elementos que cumplen los criterios de la consulta de búsqueda. Para compilar la estimación de los elementos de Exchange, se solicita una lista de los identificadores de mensaje que cumplen los criterios de búsqueda en la base de datos de Exchange mediante la herramienta eDiscovery que está usando. Sin embargo, cuando se exportan los resultados de la búsqueda, la búsqueda se vuelve a ejecutar y los mensajes reales se recuperan de la base de datos de Exchange. Por lo tanto, es posible que se produzcan estas diferencias debido a cómo se determina el número estimado de elementos y el número real de elementos.

- **Cambios que se producen entre el momento en que se calculan y se exportan los resultados de búsqueda**. Cuando se exportan los resultados de la búsqueda, la búsqueda se reinicia para recopilar los elementos más recientes del índice de búsqueda que cumplen los criterios de búsqueda. Es posible que se hayan creado, enviado o recibido elementos adicionales que cumplan los criterios de búsqueda en el tiempo entre el momento en que se recopilaron los resultados de búsqueda estimados y el momento en que se exportaron los resultados de la búsqueda. También es posible que los elementos que estaban en el índice de búsqueda cuando se calcularon los resultados de la búsqueda ya no existan porque se han purgado de la ubicación del contenido antes de que se exporten los resultados de la búsqueda. Una forma de mitigar este problema es especificar un intervalo de fechas para una búsqueda de exhibición de documentos electrónicos. Otra forma consiste en poner una retención en las ubicaciones de contenido para que los elementos se conserven y no puedan purgarse. 

   Aunque rara vez, incluso en el caso de que se aplica una retención, el mantenimiento de los elementos del calendario integrados (que el usuario no puede editar, pero que se incluyen en muchos resultados de la búsqueda) puede que se eliminen de vez en cuando. Esta eliminación periódica de los elementos del calendario tendrá como resultado menos elementos que se exportarán.

- **Elementos sin indexar**. Los elementos que no se indizan para la búsqueda pueden causar diferencias entre los resultados de búsqueda reales y estimados. Puede incluir elementos sin indexar al exportar los resultados de la búsqueda. Si incluye elementos sin indexar al exportar los resultados de la búsqueda, es posible que haya más elementos que se exportan. Esto hará que se produzca una diferencia entre los resultados de búsqueda estimados y exportados.

    Al usar la herramienta de búsqueda de contenido, tiene la opción de incluir elementos sin indexar en la estimación de búsqueda. El número de elementos sin indexar devueltos por la búsqueda se muestra en la página de flotante junto con los demás resultados de búsqueda estimados. Los elementos sin indexar también se incluirán en el tamaño total de los resultados de búsqueda estimados. Al exportar los resultados de la búsqueda, tiene la opción de incluir o no los elementos no indexados. La forma en que se configuran estas opciones puede dar lugar a diferencias entre los resultados de búsqueda reales y estimados que se descargan.

- **Exportar los resultados de una búsqueda de contenido que incluya todas las ubicaciones de contenido**. Si la búsqueda desde la que está exportando resultados es una búsqueda de todas las ubicaciones de contenido de la organización, se exportarán solo los elementos sin indexar de las ubicaciones de contenido que contienen elementos que coinciden con los criterios de búsqueda. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. Sin embargo, los elementos no indexados de todas las ubicaciones de contenido (incluso los que no contienen elementos que coinciden con la consulta de búsqueda) se incluirán en los resultados de búsqueda estimados.

    Como alternativa, si la búsqueda que está exportando los resultados de ubicaciones de contenido específicas incluidas, los elementos sin indexar (que no se excluyen por los criterios de búsqueda) de todas las ubicaciones de contenido especificadas en la búsqueda se exportarán. En este caso, el número estimado de elementos sin indexar y el número de elementos sin indexar que se exportan deben ser iguales.

    El motivo por el que no se exportan elementos sin indexar desde cada ubicación de la organización es que puede aumentar la probabilidad de errores de exportación y aumentar el tiempo necesario para exportar y descargar los resultados de la búsqueda.

- **Formatos de archivo sin procesar frente a formatos de archivo exportados**. Para los elementos de Exchange, el tamaño estimado de los resultados de la búsqueda se calcula mediante el tamaño de los mensajes de Exchange sin formato. Sin embargo, los mensajes de correo electrónico se exportan en un archivo PST o como mensajes individuales (que tienen el formato EML files). Ambas opciones de exportación usan un formato de archivo distinto al de los mensajes de Exchange sin procesar, lo que hace que el tamaño total del archivo exportado sea diferente al tamaño de archivo estimado.

- **Versiones de documentos**. Para los documentos de SharePoint, no se incluyen varias versiones de un documento en los resultados de búsqueda estimados. Pero tiene la opción de incluir todas las versiones del documento al exportar los resultados de la búsqueda, lo que aumentará el número real (y el tamaño total) de los documentos exportados. 

- **Desduplicación**. Para los elementos de Exchange, la desduplicación reduce el número de elementos que se exportan. Tiene la opción de desduplicar los resultados de la búsqueda al exportarlos. Para los mensajes de Exchange, esto significa que solo se exporta una instancia de un mensaje, aunque ese mensaje se pueda encontrar en varios buzones. Los resultados de búsqueda estimados incluyen todas las instancias de un mensaje. Por lo tanto, si elige la opción de desduplicación al exportar los resultados de la búsqueda, el número real de elementos que se exportan podría ser considerablemente menor que el número estimado de elementos.

    Otra cosa que debe tener en cuenta si elige la opción de desduplicación es que todos los elementos de Exchange se exportan en un único archivo PST y la estructura de carpetas de los buzones de origen no se conserva. El archivo PST exportado solo contiene los elementos de correo electrónico. Sin embargo, un informe de resultados de búsqueda contiene una entrada para cada mensaje exportado que identifica el buzón de origen donde se encuentra el mensaje. Esto le ayuda a identificar todos los buzones que contienen un mensaje duplicado. Si no habilita la desduplicación, se exportará un archivo PST independiente por cada buzón incluido en la búsqueda. 
 
> [!NOTE]
> Si no selecciona la opción **incluir elementos cifrados o con formato no reconocido** al exportar los resultados de la búsqueda o simplemente descargar los informes, se descargan los informes de errores de índice pero no tienen ninguna entrada. Esto no significa que no haya errores de indización. Solo significa que los elementos sin indexar no se incluyeron en la exportación. 
