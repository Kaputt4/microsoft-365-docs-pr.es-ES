---
title: Introducción a Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.custom: intro-overview
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre las funcionalidades y características de Microsoft Syntex.
ms.openlocfilehash: b5c030231395284ece7342f8ed27349bce42f0df
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68664212"
---
# <a name="overview-of-microsoft-syntex"></a>Introducción a Microsoft Syntex

Microsoft Syntex es un servicio de comprensión, procesamiento y cumplimiento de contenido que usa el procesamiento inteligente de documentos, la inteligencia artificial de contenido (IA) y el aprendizaje automático avanzado para buscar, organizar y clasificar documentos de forma automática y cuidadosa en las bibliotecas de SharePoint.

:::row:::
   :::column span="":::      
      Con Syntex, puede automatizar los procesos basados en contenido, capturando la información en los documentos empresariales y transformando esa información en conocimientos prácticos para su organización.

      En lugar de hacer clic y ordenar cientos o miles de archivos, Syntex extrae, analiza y clasifica los datos automáticamente.
   :::column-end:::
   :::column span="":::
      ![Imagen de los equipos que ejecutan Syntex.](../media/content-understanding/syntex-devices-image.png)
   :::column-end:::
:::row-end:::

Puede profundizar en el contenido para comprenderlo realmente y convertir la información en información significativa que su organización puede usar para tomar decisiones empresariales informadas.

## <a name="models"></a>Modelos

:::row:::
   :::column span="":::
      ![Imagen del icono del modelo genérico.](../media/content-understanding/model-generic-image.png) 
   :::column-end:::
   :::column span="3":::
      La comprensión del contenido con Syntex comienza con modelos. Los modelos le permiten identificar y clasificar documentos que se cargan en las bibliotecas de documentos de SharePoint y, a continuación, extraer la información que necesita de cada archivo.

      En Syntex, puede crear [modelos personalizados](model-types-overview.md) o puede usar [modelos precompilados](prebuilt-overview.md). 
   :::column-end:::
:::row-end:::

El tipo de modelo que elija dependerá de los tipos de archivos que use, el formato y la estructura de los archivos, la información que desee extraer y dónde quiera aplicar el modelo.

### <a name="custom-models"></a>Modelos personalizados

Cree modelos personalizados para comprender el diseño de los archivos a partir de documentos de ejemplo. Los modelos aprenden a buscar los datos que necesita extraer de documentos similares. Los modelos personalizados incluyen:

- [Procesamiento de documentos no estructurados](document-understanding-overview.md)
- [Procesamiento de documentos de forma libre](freeform-document-processing-overview.md)
- [Procesamiento estructurado de documentos](form-processing-overview.md)

| Desestructurado<br>procesamiento de documentos  | Forma libre<br>procesamiento de documentos  | Estructurado<br>procesamiento de documentos  |
| ------------- | ------------- | ------------- |
|  ![Icono para el modelo de procesamiento de documentos no estructurados.](../media/content-understanding/custom-classify-and-extract-by-text-pattern.png) | ![Icono del modelo de procesamiento de documentos de forma libre.](../media/content-understanding/custom-extract-by-text-pattern-and-layout.png) |  ![Icono para el modelo de procesamiento estructurado de documentos.](../media/content-understanding/custom-extract-by-layout.png) |
| Use este modelo personalizado para clasificar automáticamente documentos y extraer información de ellos. Use los patrones del texto en documentos de ejemplo para entrenar el modelo. Mejor para archivos de Office y clasificación automática de archivos. <br>[Más información](document-understanding-overview.md) | Use este modelo personalizado para extraer automáticamente información de documentos no estructurados. Use los patrones del texto o el diseño en documentos de ejemplo para entrenar el modelo. Lo mejor para una combinación de las necesidades de texto y diseño. <br>[Más información](freeform-document-processing-overview.md) |  Use este modelo personalizado para identificar automáticamente los valores de campo y tabla de documentos estructurados o semiestructurados, como formularios. Mejor para la mayoría de los idiomas y archivos que incluyen diseños de formulario o tablas. <br>[Más información](form-processing-overview.md) |

### <a name="prebuilt-models"></a>Modelos creados previamente

Si no necesita compilar un modelo personalizado, puede usar un [modelo precompilado](prebuilt-overview.md). Este tipo de modelo se entrena previamente para extraer entidades predefinidas de archivos empresariales comunes. Los modelos precompilados incluyen:

- [Procesamiento de facturas](prebuilt-model-invoice.md)
- [Procesamiento de recibos](prebuilt-model-receipt.md)

| Procesamiento de facturas | Procesamiento de recibos | 
| ------------- | ------------- |
| ![Icono para el modelo de facturas.](../media/content-understanding/trained-invoices-model.png) | ![Icono del modelo de recibos.](../media/content-understanding/trained-receipts-model.png) |
| Use este modelo precompilado para ahorrar tiempo en el procesamiento de facturas. Extraiga automáticamente información clave específica de las facturas. <br>[Más información](prebuilt-model-invoice.md) | Use este modelo precompilado para ahorrar tiempo en el procesamiento de recibos. Extraiga automáticamente información clave específica de los gastos. <br>[Más información](prebuilt-model-receipt.md) | 

Para obtener más información sobre los modelos personalizados y precompilados, consulte [Información general sobre los tipos de modelos en Microsoft Syntex](model-types-overview.md).

## <a name="content-assembly"></a>Ensamble de contenidos

:::row:::
   :::column span="":::
      ![Imagen del icono de documento genérico.](../media/content-understanding/document-assembly-image.png) 
   :::column-end:::
   :::column span="3":::
      Con Syntex, puede crear *plantillas modernas* basadas en los documentos empresariales que más use.

      A continuación, puede usar esas plantillas para generar automáticamente nuevos documentos mediante listas de SharePoint o entradas de usuario como origen de datos.
   :::column-end:::
:::row-end:::

 Este proceso le permite generar automáticamente documentos empresariales repetitivos estándar, como contratos, declaraciones de trabajo, contratos de servicio, cartas de consentimiento y correspondencia. Puede realizar todas estas tareas de forma más rápida, coherente y con menos errores en Syntex.

Para obtener más información, consulte [Creación de documentos mediante el ensamblado de contenido en Microsoft Syntex](content-assembly.md).

## <a name="advanced-metadata-search"></a>Búsqueda avanzada de metadatos

:::row:::
   :::column span="3":::
      La característica de búsqueda avanzada de metadatos en Syntex le permite realizar consultas específicas basadas en metadatos en bibliotecas de documentos de SharePoint.

      Puede realizar consultas más rápidas y precisas basadas en valores de columna de metadatos específicos, en lugar de simplemente buscar palabras clave.    
   :::column-end:::
   :::column span="":::
      ![Imagen del icono de búsqueda genérica.](../media/content-understanding/search-generic-image.png)
   :::column-end:::
:::row-end:::

Esta característica es útil cuando tiene una información específica que desea buscar, como cuando se modificó por última vez un documento, una persona específica asociada a un archivo o un tipo de archivo específico.

Para obtener más información, consulte [Búsqueda de metadatos en bibliotecas de documentos en Microsoft Syntex](metadata-search.md).

--->

## <a name="content-compliance"></a>Cumplimiento de contenido

:::row:::
   :::column span="":::
      ![Imagen del icono de cumplimiento genérico.](../media/content-understanding/compliance-image.png) 
   :::column-end:::
   :::column span="3":::
      Comprender el contenido permite un mejor control de cumplimiento y aumenta las opciones de administración y gobernanza de todos los datos. Cuando el contenido se etiqueta y clasifica correctamente, se logra un mejor control sobre los datos y es posible seguir las normativas más fácilmente. Syntex le ayuda a garantizar el cumplimiento mediante el uso de etiquetas de retención y etiquetas de confidencialidad para administrar los documentos.
   :::column-end:::
:::row-end:::

Para obtener más información, vea [Aplicar una etiqueta de retención a un modelo de Microsoft Syntex](apply-a-retention-label-to-a-model.md) y [Aplicar una etiqueta de confidencialidad a un modelo de Microsoft Syntex](apply-a-sensitivity-label-to-a-model.md).

## <a name="premium-taxonomy-services"></a>Servicios de taxonomía Premium

:::row:::
   :::column span="3":::
      Tener una o más licencias de Syntex en su organización permite las siguientes características adicionales de almacén de términos para los administradores:<br><br>
       
      - [Importación del conjunto de términos basado en SKOS](import-term-set-skos.md), que permite importar un conjunto de términos mediante un formato basado en SKOS.      
   :::column-end:::
   :::column span="":::
      ![Imagen del icono de taxonomía genérica.](../media/content-understanding/taxonomy-image.png)
   :::column-end:::
:::row-end:::


- [Insertar tipos de contenido empresarial en un sitio central](push-content-type-to-hub.md), que también los agrega a los sitios asociados y a las listas o bibliotecas recién creadas.

- [Informes de almacén de términos](term-store-analytics.md), que le proporcionan información sobre los conjuntos de términos publicados y su uso en toda la organización.

## <a name="scenarios-and-use-cases"></a>Escenarios y casos de uso

:::row:::
   :::column span="":::
      ![Imagen del icono de escenario genérico.](../media/content-understanding/scenarios-image.png) 
   :::column-end:::
   :::column span="3":::
      Syntex puede ayudar a su organización a automatizar los procesos empresariales, mejorar la precisión de la búsqueda y administrar el riesgo de cumplimiento.

      Con los servicios y funcionalidades de IA de contenido, puede crear la comprensión y clasificación del contenido directamente en el flujo de administración de contenido.
   :::column-end:::
:::row-end:::

Para preguntar ideas sobre cómo puede usar Syntex en su organización, consulte [Escenarios y casos de uso para Microsoft Syntex](adoption-scenarios.md).
<br><br>
> [!div class="nextstepaction"]
> [Más información sobre los modelos en Microsoft Syntex](model-types-overview.md)
