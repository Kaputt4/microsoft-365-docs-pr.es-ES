---
title: Resultados de búsqueda de eDiscovery estimados y reales
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 8f20ca4f-a908-46ec-99e6-9890d269ecf2
description: Comprenda por qué los resultados de búsqueda estimados y reales pueden variar en las búsquedas que se ejecutan con las herramientas de exhibición de documentos electrónicos en Office 365.
ms.openlocfilehash: db7026672af0e3abfcee524757a63c9747ff06e7
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66638574"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results"></a>Diferencias entre los resultados de búsqueda de eDiscovery estimados y reales

Este artículo se aplica a las búsquedas que puede ejecutar mediante una de las siguientes herramientas de Exhibición de documentos electrónicos de Microsoft 365: 

- Búsqueda de contenido
- eDiscovery (Estándar)

Al ejecutar una búsqueda de exhibición de documentos electrónicos, la herramienta que usa devolverá una estimación del número de elementos (y su tamaño total) que coincidan con los criterios de búsqueda. Por ejemplo, al ejecutar una búsqueda en el portal de cumplimiento Microsoft Purview, los resultados de búsqueda estimados se muestran en la página de control flotante de la búsqueda seleccionada.
  
![Estimación de los resultados mostrados en la página de control flotante de búsqueda.](../media/EstimatedSearchResults1.png)
  
Esta es la misma estimación del tamaño total y el número de elementos que se muestran en la herramienta de exportación de exhibición de documentos electrónicos al exportar los resultados a un equipo local y en el informe Resumen de exportación que se descarga con los resultados de la búsqueda.
  
**Resultados estimados en la herramienta de exportación de exhibición de documentos electrónicos**

![Resultados estimados en la herramienta de exportación de eDiscovery.](../media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**Resultados estimados en el informe Resumen de exportación**

![Los resultados de búsqueda estimados se incluyen en el informe Exportar resumen.](../media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
Sin embargo, como observará en la captura de pantalla anterior del informe Exportar resumen, el tamaño y el número de resultados de búsqueda reales que se descargan son diferentes del tamaño y el número de resultados de búsqueda estimados.
  
![Diferencia entre los resultados de búsqueda estimados y descargados.](../media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
Estas son algunas de las razones de estas diferencias:
  
- **La forma en que se calculan los resultados**. Una estimación de los resultados de la búsqueda es simplemente eso, una estimación (y no un recuento real) de los elementos que cumplen los criterios de consulta de búsqueda. Para compilar la estimación de elementos de Exchange, la herramienta eDiscovery que usa solicita a la base de datos de Exchange una lista de los identificadores de mensaje que cumplen los criterios de búsqueda. Pero al exportar los resultados de la búsqueda, la búsqueda se vuelve a ejecutar y los mensajes reales se recuperan de la base de datos de Exchange. Por lo tanto, estas diferencias pueden dar lugar a cómo se determina el número estimado de elementos y el número real de elementos.

- **Cambios que se producen entre el momento en que se estiman y exportan los resultados de la búsqueda**. Al exportar los resultados de búsqueda, la búsqueda se reinicia para recopilar los elementos más recientes del índice de búsqueda que cumplen los criterios de búsqueda. Es posible que haya elementos adicionales creados, enviados o recibidos que cumplan los criterios de búsqueda en el tiempo comprendido entre la recopilación de los resultados de búsqueda estimados y el momento en que se exportaron los resultados de la búsqueda. También es posible que los elementos que estaban en el índice de búsqueda cuando se calcularon los resultados de búsqueda ya no estén allí porque se purgaron de la ubicación de contenido antes de exportar los resultados de la búsqueda. Una manera de mitigar este problema es especificar un intervalo de fechas para una búsqueda de exhibición de documentos electrónicos. Otra manera es colocar una suspensión en las ubicaciones de contenido para que los elementos se conserven y no se puedan purgar.

   Estos son otros problemas que pueden dar lugar a diferencias entre los resultados de búsqueda estimados y exportados:

  - Aumento de elementos al usar una consulta de fecha. Esto suele deberse a las dos cosas siguientes:

  - Mantenga el control de versiones en SharePoint. Si se elimina un documento de un sitio que está en suspensión y el control de versiones de documento está habilitado, se conservarán todas las versiones del documento eliminado.

  - Elementos de calendario. Aceptar y rechazar mensajes y las reuniones periódicas seguirán creando automáticamente nuevos elementos en segundo plano con fechas antiguas.

  - Con las retenciones, puede haber casos en los que el mismo elemento se conserve en el buzón principal de un usuario y en su buzón de archivo. Esto puede ocurrir cuando un usuario mueve manualmente un elemento a su archivo.

  - Aunque es poco frecuente, incluso en el caso de que se aplique una suspensión, el mantenimiento de elementos de calendario integrados (que el usuario no puede modificar, pero que se incluyen en muchos resultados de búsqueda) puede quitarse de vez en cuando. Esta eliminación periódica de elementos de calendario dará lugar a menos elementos que se exportan.

- **Elementos sin indexar**. Los elementos que no están indexados para la búsqueda pueden provocar diferencias entre los resultados de búsqueda estimados y reales. Puede incluir elementos sin indexar al exportar los resultados de la búsqueda. Si incluye elementos sin indexar al exportar resultados de búsqueda, es posible que haya más elementos que se exporten. Esto provocará una diferencia entre los resultados de búsqueda estimados y exportados.

    Al usar la herramienta de búsqueda de contenido, tiene la opción de incluir elementos sin indexar al exportar los resultados de la búsqueda. El número de elementos sin indexar devueltos por la búsqueda se muestra en la página de control flotante junto con los demás resultados de búsqueda estimados. Los elementos sin indexar también se incluirían en el tamaño total de los resultados de búsqueda estimados. Al exportar los resultados de la búsqueda, tiene la opción de incluir o no elementos sin indexar. La configuración de estas opciones puede dar lugar a diferencias entre los resultados de búsqueda estimados y reales que se descargan.

- **Exportación de los resultados de una búsqueda de contenido que incluye todas las ubicaciones de contenido**. Si la búsqueda desde la que va a exportar los resultados era una búsqueda de todas las ubicaciones de contenido de su organización, solo se exportarán los elementos sin indexar de las ubicaciones de contenido que contienen elementos que coinciden con los criterios de búsqueda. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. Sin embargo, los elementos sin indexar de todas las ubicaciones de contenido (incluso aquellos que no contienen elementos que coinciden con la consulta de búsqueda) se incluirán en los resultados de búsqueda estimados.

    Como alternativa, si la búsqueda que va a exportar resultados de ubicaciones de contenido específicas incluidas, se exportarán los elementos sin indexar (que no se excluyen por los criterios de búsqueda) de todas las ubicaciones de contenido especificadas en la búsqueda. En este caso, el número estimado de elementos sin indexar y el número de elementos sin indexar que se exportan deben ser los mismos.

    La razón para no exportar elementos sin indexar desde todas las ubicaciones de la organización es que podría aumentar la probabilidad de errores de exportación y aumentar el tiempo necesario para exportar y descargar los resultados de la búsqueda.

- **Elementos sin indexar en SharePoint y OneDrive no incluidos en las estimaciones de búsqueda**. Los elementos no indexados de sitios de SharePoint y cuentas de OneDrive para la Empresa no se incluyen en los resultados de búsqueda estimados. Esto se debe a que el índice de SharePoint no contiene datos para elementos sin indexar. En las estimaciones de búsqueda solo se incluyen elementos no indizados de buzones de correo. Sin embargo, si incluye elementos sin indexar al exportar resultados de búsqueda, se incluyen elementos sin indexar en SharePoint y OneDrive, lo que aumentará el número de elementos que se exportan realmente. Esto provocará diferencias entre los resultados estimados (que no incluyen elementos sin indexar en sitios de SharePoint y OneDrive) y los elementos reales que se descargan. La regla sobre la exportación de elementos no indizados solo desde ubicaciones de contenido que contienen elementos que coinciden con los criterios de búsqueda se sigue aplicando en esta situación.

- **Versiones de documentos en SharePoint y OneDrive**. Al buscar sitios de SharePoint y cuentas de OneDrive, varias versiones de un documento no se incluyen en el recuento de resultados de búsqueda estimados. Pero tiene la opción de incluir todas las versiones del documento al exportar los resultados de la búsqueda. Si incluye versiones de documento al exportar resultados de búsqueda, se aumentará el número real (y el tamaño total) de los elementos exportados.

- **Carpetas de SharePoint**. Si las carpetas de SharePoint coinciden con una consulta de búsqueda, por ejemplo, la búsqueda por fecha, la estimación de búsqueda incluirá un recuento de esas carpetas con el intervalo de fechas de la última modificación (pero no los elementos de esas carpetas). Al exportar los resultados de la búsqueda, los elementos de la carpeta se exportan, pero la carpeta real no se exporta. El resultado es que el número de elementos exportados será mayor que el número de resultados de búsqueda estimados. Si una carpeta está vacía, el número de resultados de búsqueda reales exportados se reducirá en un elemento, ya que la carpeta real no se exporta.

   > [!NOTE]
   > Al ejecutar una búsqueda basada en consultas, puede excluir carpetas de SharePoint agregando la siguiente condición a la consulta: `NOT(ContentType:folder)`.

- **Listas de SharePoint**. Si el nombre de una lista de SharePoint coincide con una consulta de búsqueda, la estimación de búsqueda incluirá un recuento de todos los elementos de la lista. Al exportar los resultados de la búsqueda, la lista (y los elementos de lista) se exporta como un único archivo CSV. Esto reducirá el número real de elementos realmente exportados. Si la lista contiene datos adjuntos, los datos adjuntos se exportarán como documentos independientes, lo que también aumentará el número de elementos exportados.

   > [!NOTE]
   > Al ejecutar una búsqueda basada en consultas, puede excluir listas de SharePoint agregando la siguiente condición a la consulta: `NOT(ContentType:list)`.

- **Formatos de archivo sin formato frente a formatos de archivo exportados**. En el caso de los elementos de Exchange, el tamaño estimado de los resultados de búsqueda se calcula mediante los tamaños de mensajes de Exchange sin formato. Sin embargo, los mensajes de correo electrónico se exportan en un archivo PST o como mensajes individuales (que tienen el formato de archivos EML). Ambas opciones de exportación usan un formato de archivo diferente al de los mensajes de Exchange sin procesar, lo que hace que el tamaño total del archivo exportado sea diferente del tamaño estimado del archivo.

- **Desduplicación de elementos de Exchange durante la exportación**. En el caso de los elementos de Exchange, la desduplicación reduce el número de elementos que se exportan. Tiene la opción de desduplicar los resultados de la búsqueda al exportarlos. En el caso de los mensajes de Exchange, esto significa que solo se exporta una única instancia de un mensaje, aunque ese mensaje se encuentre en varios buzones. Los resultados de búsqueda estimados incluyen todas las instancias de un mensaje. Por lo tanto, si elige la opción de desduplicación al exportar los resultados de búsqueda, el número real de elementos que se exportan podría ser considerablemente menor que el número estimado de elementos.

El informe de resultados de búsqueda (archivo Results.csv) contiene una entrada para cada mensaje duplicado e identifica el buzón de origen donde se encuentra un mensaje duplicado. Esto le ayuda a identificar todos los buzones que contienen un mensaje duplicado.

> [!NOTE]
> Si no selecciona la opción **Include items that are encrypted or have an unrecognized format (Incluir elementos cifrados o con un formato no reconocido** ) al exportar los resultados de búsqueda o simplemente descargar los informes, los informes de errores de índice se descargan pero no tienen ninguna entrada. Esto no significa que no haya errores de indexación. Simplemente significa que los elementos sin indexar no se incluyeron en la exportación.
