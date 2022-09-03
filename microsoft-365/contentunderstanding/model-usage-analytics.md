---
title: Analice cómo se usan los modelos en Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.service: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre cómo encontrar más información sobre el rendimiento de los modelos de procesamiento de formularios y comprensión de documentos.
ms.openlocfilehash: 7c998304472db04d94b430fd1cb98111a1fbdd0a
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67582634"
---
# <a name="analyze-how-your-models-are-used-in-microsoft-sharepoint-syntex"></a>Analice cómo se usan los modelos en Microsoft SharePoint Syntex

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhX]  

</br>


Su centro de contenido de SharePoint Syntex proporciona el análisis de uso de modelos para obtener más información sobre cómo se usan los modelos que se publicaron desde el centro de contenido. En la sección <b>Resultados de los modelos en los últimos 30 días</b> del centro de contenido se incluye un resumen de 30 días de datos de análisis de uso proporcionados en los siguientes gráficos y listas:

- Clasificación por modelo
- Clasificación por biblioteca
- Uso del modelo 

 ![Análisis del modelo.](../media/content-understanding/model-analytics.png) </br>

### <a name="roll-up-of-model-usage-data-in-the-default-content-center"></a>Resumen de datos de uso del modelo en el centro de contenido predeterminado

En SharePoint Syntex, el centro de contenido predeterminado se crea durante la configuración. También se pueden crear más centros de contenido según sea necesario. Por ejemplo, los departamentos podrían crear sus propios centros de contenido para elaborar y administrar sus modelos. 

Con respecto al análisis de uso del modelo, tenga en cuenta lo siguiente:

- El centro de contenido predeterminado mostrará el análisis de uso de modelos para todos los centros de contenido y modelos de su organización, incluidos los creados en otros centros de contenido. Esto proporciona a los administradores de contenido y a otras partes interesadas un portal centralizado para administrar y supervisar los centros de contenido y los modelos en toda la empresa.  
- En otros centros de contenido solo se mostrarán análisis de uso del modelo de los modelos que se hayan creado en ellos. Esto proporciona a los administradores de contenido información sobre los datos de uso solo para los modelos que les preocupan.


## <a name="classification-by-model"></a>Clasificación por modelo

   ![Porcentaje total del modelo.](../media/content-understanding/total-model-percentage.png) </br>

En el gráfico circular **Clasificación por modelo**, se muestran los modelos que han clasificado la mayoría de los archivos. Muestra cada modelo publicado como porcentaje del total de los archivos procesados por todos los modelos publicados en el centro de contenido.

Asimismo, cada modelo presenta una **Tasa de exhaustividad**. Es decir, el porcentaje de los archivos cargados que el modelo analizó correctamente. Una tasa de exhaustividad baja puede significar que existen problemas con el modelo o los archivos que se están analizando.

## <a name="classification-by-library"></a>Clasificación por biblioteca

   ![Archivos procesados.](../media/content-understanding/files-processed-over-time.png) </br>

El gráfico de barras **Clasificación por biblioteca** le ayuda a determinar la eficacia de la comprensión de contenidos en su organización.  Le muestra no solo el número de archivos que se procesó a lo largo del tiempo para cada modelo, sino también las bibliotecas de documentos a las que se aplicó el modelo si selecciona una columna del gráfico.


## <a name="model-usage"></a>Uso del modelo

La lista Uso del modelo mostrará análisis de uso de los modelos creados mediante el centro de contenido.  

> [!NOTE]
> Si se encuentra en el centro de contenido predeterminado y tiene centros de contenido adicionales en la organización, la lista de uso del modelo se agrupará por centro de contenido.

Cada modelo de la lista de uso del modelo mostrará los datos de uso:

- Recuento de elementos clasificados: número de archivos procesados por el modelo.
- Puntuación media de confianza: puntuación media de precisión del modelo al ejecutarlo con archivos.
- URL de lista de objetivo: la biblioteca de documentos de SharePoint a la que se aplica el modelo.



## <a name="see-also"></a>Vea también
[Crear un clasificador](create-a-classifier.md)

[Crear un extractor](create-an-extractor.md)

[Información general sobre la comprensión de los documentos](document-understanding-overview.md)

[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)  
