---
title: Desduplicación en los resultados de búsqueda de eDiscovery
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 12/21/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo eliminar resultados de búsqueda de exhibición de documentos electrónicos duplicados para que solo se exporte una copia de un mensaje de correo electrónico.
ms.openlocfilehash: b8b595e1bf9296262f3ed4feff977daa3aef5c13
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67818509"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>Desduplicación en los resultados de búsqueda de eDiscovery

En este artículo se describe cómo funciona la desduplicación de los resultados de búsqueda de eDiscovery y se explican las limitaciones del algoritmo de desduplicación.
  
Al usar herramientas de eDiscovery para exportar los resultados de una búsqueda de exhibición de documentos electrónicos, tiene la opción de desduplicar los resultados que se exportan. ¿Qué significa esto? Al habilitar la desduplicación (de forma predeterminada, la desduplicación no está habilitada), solo se exporta una copia de un mensaje de correo electrónico aunque se hayan encontrado varias instancias del mismo mensaje en los buzones de correo en los que se ha buscado. La desduplicación le ayuda a ahorrar tiempo al reducir el número de elementos que tiene que revisar y analizar después de exportar los resultados de la búsqueda. Pero es importante comprender cómo funciona la desduplicación y tener en cuenta que hay limitaciones en el algoritmo que pueden hacer que un elemento único se marque como duplicado durante el proceso de exportación.
  
## <a name="how-duplicate-messages-are-identified"></a>Cómo se identifican los mensajes duplicados

Las herramientas de eDiscovery usan una combinación de las siguientes propiedades de correo electrónico para determinar si un mensaje es duplicado:
  
- **InternetMessageId** : esta propiedad especifica el identificador de mensaje de Internet de un mensaje de correo electrónico, que es un identificador único global que hace referencia a una versión específica de un mensaje específico. Este identificador lo genera el programa cliente de correo electrónico del remitente o el sistema de correo electrónico host que envía el mensaje. Si una persona envía un mensaje a más de un destinatario, el identificador de mensaje de Internet será el mismo para cada instancia del mensaje. Las revisiones posteriores del mensaje original recibirán un identificador de mensaje diferente. 

- **ConversationTopic** : esta propiedad especifica el asunto del subproceso de conversación de un mensaje. El valor de la propiedad **ConversationTopic** es la cadena que describe el tema general de la conversación. Una conversación consta de un mensaje inicial y todos los mensajes enviados en respuesta al mensaje inicial. Los mensajes de la misma conversación tienen el mismo valor para la propiedad **ConversationTopic** . El valor de esta propiedad suele ser la línea Subject del mensaje inicial que generó la conversación. 

- **BodyTagInfo** : se trata de una propiedad interna del almacén de Exchange. El valor de esta propiedad se calcula comprobando varios atributos en el cuerpo del mensaje. Esta propiedad se usa para identificar las diferencias en el cuerpo de los mensajes. 

Durante el proceso de exportación de eDiscovery, estas tres propiedades se comparan para cada mensaje que coincida con los criterios de búsqueda. Si estas propiedades son idénticas para dos (o más) mensajes, se determina que esos mensajes son duplicados y el resultado es que solo se exportará una copia del mensaje si se habilita la desduplicación. El mensaje que se exporta se conoce como "elemento de origen". La información sobre los mensajes duplicados se incluye en los informes **deResults.csv** y **Manifest.xml** que se incluyen con los resultados de búsqueda exportados. En el archivo **Results.csv** , un mensaje duplicado se identifica con un valor en la columna **Duplicar en elemento** . El valor de esta columna coincide con el valor de la columna **Identidad del elemento** del mensaje que se exportó. 
  
Los gráficos siguientes muestran cómo se muestran los mensajes duplicados en los informes **deResults.csv** y **Manifest.xml** que se exportan con los resultados de la búsqueda. Estos informes no incluyen las propiedades de correo electrónico descritas anteriormente, que se usan en el algoritmo de desduplicación. En su lugar, los informes incluyen la propiedad **Item Identity** asignada a los elementos por el almacén de Exchange. 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>Results.csv informe (visto en Excel)
  
![Ver información sobre elementos duplicados en el informe de Results.csv.](../media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Manifest.xml informe (visto en Excel)
  
![Ver información sobre elementos duplicados en el informe de Manifest.xml.](../media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
Además, se incluyen otras propiedades de mensajes duplicados en los informes de exportación. Esto incluye el buzón en el que se encuentra el mensaje duplicado, si el mensaje se envió a un grupo de distribución y si el mensaje fue Cc'd o CCO a otro usuario.
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>Limitaciones del algoritmo de desduplicación

Hay algunas limitaciones conocidas del algoritmo de desduplicación que pueden hacer que los elementos únicos se marquen como duplicados. Es importante comprender estas limitaciones para que pueda decidir si desea usar o no la característica opcional de desduplicación.
  
Hay una situación en la que la característica de desduplicación podría identificar erróneamente un mensaje como duplicado y no exportarlo (pero aún así citarlo como duplicado en los informes de exportación). Se trata de mensajes que un usuario edita pero no envía. Por ejemplo, supongamos que un usuario selecciona un mensaje en Outlook, copia el contenido del mensaje y, a continuación, lo pega en un mensaje nuevo. A continuación, el usuario cambia una de las copias quitando o agregando datos adjuntos, o cambiando la línea del asunto o el propio cuerpo. Si estos dos mensajes coinciden con la consulta de una búsqueda de exhibición de documentos electrónicos, solo se exportará uno de los mensajes si la desduplicación está habilitada cuando se exportan los resultados de la búsqueda. Por lo tanto, aunque se cambió el mensaje original o el mensaje copiado, no se envió ninguno de los mensajes revisados y, por lo tanto, no se actualizaron los valores de **las propiedades InternetMessageId**, **ConversationTopic** y **BodyTagInfo** . Pero como se explicó anteriormente, ambos mensajes se mostrarán en los informes de exportación. 
  
Los mensajes únicos también se pueden marcar como duplicados cuando está habilitada la característica de protección de página Copiar en escritura, como en el caso de que un buzón esté en suspensión por juicio o In-Place suspensión. La característica Copiar en escritura copia el mensaje original (y lo guarda en la carpeta Versiones de la carpeta Elementos recuperables del usuario) antes de guardar la revisión en el elemento original. En este caso, la copia revisada y el mensaje original (en la carpeta Elementos recuperables) podrían considerarse mensajes duplicados y, por tanto, solo se exportaría uno de ellos.
  
> [!IMPORTANT]
> Si las limitaciones del algoritmo de desduplicación pueden afectar a la calidad de los resultados de búsqueda, no debe habilitar la desduplicación al exportar elementos. Si es poco probable que las situaciones descritas en esta sección sean un factor en los resultados de la búsqueda y quiera reducir el número de elementos con más probabilidad de que sean duplicados, considere la posibilidad de habilitar la desduplicación. 
  
## <a name="more-information"></a>Más información

- La información de este artículo es aplicable al exportar resultados de búsqueda mediante una de las siguientes herramientas de exhibición de documentos electrónicos:

  - Búsqueda de contenido en el centro de cumplimiento en Office 365

  - Exhibición de documentos electrónicos local en Exchange Online

  - Centro de exhibición de documentos electrónicos en SharePoint Online

- Para obtener más información sobre la exportación de resultados de búsqueda, consulte:

  - [Exportar búsqueda de contenido](export-search-results.md)

  - [Exportar un informe de búsqueda de contenido](export-a-content-search-report.md)

  - [Exportar In-Place resultados de búsqueda de exhibición de documentos electrónicos a un archivo PST](/exchange/security-and-compliance/in-place-ediscovery/export-search-results)

  - [Exportar contenido y crear informes en el Centro de eDiscovery](/SharePoint/governance/export-content-and-create-reports-in-the-ediscovery-center)
