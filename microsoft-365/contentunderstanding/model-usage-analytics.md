---
title: Análisis de uso del modelo de comprensión mediante documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Obtenga información sobre cómo aplicar una etiqueta de retención en un modelo de comprensión mediante documentos
ms.openlocfilehash: 92115d8b1985fa84cd72671442aca18f255355de
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080443"
---
# <a name="document-understanding-model-usage-analytics"></a>Análisis de uso del modelo de comprensión mediante documentos

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhX]  

</br>


El centro de contenido de Microsoft SharePoint Syntex proporciona análisis de uso de modelos para obtener más información sobre cómo se usan los modelos que se publicaron desde el centro de contenido. En la sección <b>Resultados de los modelos en los últimos 30 días</b> del centro de contenido se incluye un resumen de 30 días de datos de análisis de uso proporcionados en los siguientes gráficos y listas:

- Clasificación por modelo
- Clasificación por biblioteca
- Uso del modelo 

 ![Análisis del modelo](../media/content-understanding/model-analytics.png) </br>

### <a name="roll-up-of-model-usage-data-in-the-default-content-center"></a>Resumen de datos de uso del modelo en el centro de contenido predeterminado

En SharePoint Syntex, el centro de contenido predeterminado se crea durante la configuración. También se pueden crear centros de contenido adicionales según sea necesario. Por ejemplo, los departamentos podrían crear sus propios centros de contenido para elaborar y administrar sus modelos. 

En lo que respecta a los análisis de uso del modelo, tenga en cuenta que:

- El centro de contenido predeterminado mostrará análisis de uso del modelo de todos los centros de contenido y los modelos de su organización, incluidos los creados en centros de contenido adicionales. Esto proporciona a los administradores de contenido y a otras partes interesadas un portal centralizado para administrar y supervisar los centros de contenido y los modelos en toda la empresa.  
- En otros centros de contenido solo se mostrarán análisis de uso del modelo de los modelos que se hayan creado en ellos. Esto proporciona a los administradores de contenido conclusiones sobre datos de uso únicamente de los modelos que les interesen.


## <a name="classification-by-model"></a>Clasificación por modelo

   ![Porcentaje de modelo total](../media/content-understanding/total-model-percentage.png) </br>

En el gráfico circular **Clasificación por modelo**, se muestran los modelos que han clasificado la mayoría de los archivos. Muestra cada modelo publicado como porcentaje del total de los archivos procesados por todos los modelos publicados en el centro de contenido.

Asimismo, cada modelo presenta una **Tasa de exhaustividad**. Es decir, el porcentaje de los archivos cargados que el modelo analizó correctamente. Una tasa de exhaustividad baja puede significar que existen problemas con el modelo o los archivos que se están analizando.

## <a name="classification-by-library"></a>Clasificación por biblioteca

   ![Archivos procesados](../media/content-understanding/files-processed-over-time.png) </br>

El gráfico de barras **Clasificación por biblioteca** le ayuda a determinar la eficacia de la comprensión de contenidos en su organización.  Le muestra no solo el número de archivos que se procesó a lo largo del tiempo para cada modelo, sino también las bibliotecas de documentos a las que se aplicó el modelo si selecciona una columna del gráfico.


## <a name="model-usage"></a>Uso del modelo

La lista Uso del modelo mostrará análisis de uso de los modelos creados mediante el centro de contenido.  

> [!NOTE]
> Si se encuentra en el centro de contenido predeterminado y tiene centros de contenido adicionales en la organización, la lista de uso del modelo se agrupará por centro de contenido.

Cada modelo de la lista de uso del modelo mostrará los datos de uso:

- Recuento de elementos clasificados: número de archivos procesados por el modelo.
- Puntuación media de confianza: puntuación media de precisión del modelo al ejecutarlo con archivos.
- URL de lista de objetivo: la biblioteca de documentos de SharePoint a la que se aplica el modelo.



## <a name="see-also"></a>Consulte también
[Crear un clasificador](create-a-classifier.md)

[Crear un extractor](create-an-extractor.md)

[Información general sobre la comprensión de los documentos](document-understanding-overview.md)

[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)  
