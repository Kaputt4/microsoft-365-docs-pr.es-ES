---
title: Introducción a los tipos de modelo en Microsoft Syntex
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
description: Obtenga información sobre modelos personalizados y modelos precompilados en Microsoft Syntex.
ms.openlocfilehash: 47eea92e8e9e4e5eb4588d04dd1422a43afd16ae
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68664356"
---
# <a name="overview-of-model-types-in-microsoft-syntex"></a>Introducción a los tipos de modelo en Microsoft Syntex

La comprensión del contenido en Microsoft Syntex comienza con los modelos de inteligencia artificial. Los modelos le permiten identificar y clasificar documentos que se cargan en bibliotecas de documentos de SharePoint y, a continuación, extraer la información que necesita de cada archivo.

Cuando se aplica a una biblioteca de documentos de SharePoint, el modelo está asociado a un tipo de contenido y tiene columnas para almacenar la información que se va a extraer. El tipo de contenido que cree se almacena en la galería de tipo de contenido de SharePoint. También puede optar por usar tipos de contenido existentes para usar su esquema.

Syntex usa [modelos personalizados](#custom-models) y [modelos precompilados](#prebuilt-models). 

![Diagrama que muestra los tipos de modelos personalizados y precompilados de Syntex.](../media/content-understanding/syntex-model-types-diagram.png)

Los modelos pueden ser *modelos empresariales*, que se crean en un [centro de contenido](create-a-content-center.md) o *modelos locales*, que se crean en el [sitio de SharePoint local](create-local-model.md).

<!---
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GJXS] 

</br>
--->

## <a name="custom-models"></a>Modelos personalizados

El tipo de modelo personalizado que elija dependerá de los tipos de archivos que use, el formato y la estructura de los archivos y de dónde quiera aplicar el modelo.

Los modelos personalizados incluyen:

- [Procesamiento de documentos no estructurados](#unstructured-document-processing)
- [Procesamiento de documentos de forma libre](#freeform-document-processing)
- [Procesamiento estructurado de documentos](#structured-document-processing)

Para ver las diferencias en paralelo en los modelos personalizados, consulte [Comparación de modelos personalizados](./difference-between-document-understanding-and-form-processing-model.md).

### <a name="unstructured-document-processing"></a>Procesamiento de documentos no estructurados

Use el modelo de procesamiento de documentos no estructurado para clasificar automáticamente documentos y extraer información de ellos. Funciona mejor con documentos sin estructura, como cartas o contratos. Estos documentos deben tener texto que pueda identificarse en función de frases o patrones. El texto identificado designa tanto el tipo de archivo (su clasificación) como lo que le gustaría extraer (sus extractores).

Por ejemplo, un documento no estructurado podría ser una carta de renovación de contrato que pueda escribirse de varias maneras. Sin embargo, la información existe de forma coherente en el cuerpo de cada documento de renovación del contrato, como la cadena de texto "Fecha de inicio del servicio de" seguida de una fecha real.

Este tipo de modelo admite la gama más amplia de tipos de archivo y solo funciona en archivos con el alfabeto latino (caracteres en inglés).

Para obtener más información, vea [Información general sobre el procesamiento de documentos no estructurados](document-understanding-overview.md).

### <a name="freeform-document-processing"></a>Procesamiento de documentos de forma libre

Use el modelo de procesamiento de documentos de forma libre para extraer automáticamente información de documentos no estructurados y de forma libre, como cartas y contratos, donde la información puede aparecer en cualquier parte del documento.

Los modelos de procesamiento de documentos de forma libre usan Microsoft Power Apps [AI Builder](/ai-builder/form-processing-model-overview) para crear y entrenar modelos en Syntex. 

> [!NOTE]
> El modelo de procesamiento de documentos de forma libre todavía no está disponible en algunas regiones. Para obtener más información, consulte [Disponibilidad de características por región](/ai-builder/availability-region).

Porque su organización recibe cartas y documentos en grandes cantidades de diversos orígenes, como correo, fax y correo electrónico. Procesar estos documentos y escribirlos manualmente en una base de datos puede tardar mucho tiempo. Mediante el uso de la inteligencia artificial para extraer el texto y otra información de estos documentos, este modelo automatiza este proceso.

Este tipo de modelo es la mejor opción para documentos en inglés en archivos PDF o de imagen cuando no se requiere la clasificación automática del tipo de documento.

Para obtener más información, vea [Información general sobre el procesamiento de documentos de forma libre](freeform-document-processing-overview.md).

### <a name="structured-document-processing"></a>Procesamiento estructurado de documentos

Use el modelo de procesamiento estructurado de documentos para identificar automáticamente los valores de campo y tabla. Funciona mejor para documentos estructurados o semiestructurados, como formularios y facturas.

Los modelos de procesamiento estructurado de documentos usan el procesamiento de documentos de Microsoft Power Apps [AI Builder](/ai-builder/form-processing-model-overview) (anteriormente conocido como procesamiento de formularios) para crear y entrenar modelos en Syntex. 

Este tipo de modelo admite la gama más amplia de idiomas y se entrena para comprender el diseño del formulario a partir de documentos de ejemplo y, a continuación, aprende a buscar los datos que necesita extraer de ubicaciones similares. Los formularios suelen tener un diseño más estructurado donde las entidades están en la misma ubicación (por ejemplo, un número de seguridad social en un formulario fiscal).

Para obtener más información, vea [Información general sobre el procesamiento estructurado de documentos](form-processing-overview.md).

## <a name="prebuilt-models"></a>Modelos creados previamente

Si no necesita crear un modelo personalizado, puede usar un [modelo precompilado](prebuilt-overview.md) que ya se haya entrenado para documentos estructurados específicos.

Los modelos precompilados incluyen:

- [Procesamiento de facturas](#invoice-processing)
- [Procesamiento de recibos](#receipt-processing)

Los modelos precompilados se entrenan previamente para reconocer los documentos y la información estructurada de los documentos. En lugar de tener que crear un nuevo modelo personalizado desde cero, puede iterar en un modelo previamente entrenado existente para agregar campos específicos que se ajusten a las necesidades de su organización.

### <a name="invoice-processing"></a>Procesamiento de facturas

El modelo de procesamiento de facturas analiza y extrae información clave de las facturas de ventas. La API analiza las facturas en varios formatos y extrae la información clave de la factura, como el nombre del cliente, la dirección de facturación, la fecha de vencimiento y el importe vencido.

Para obtener más información sobre los modelos de procesamiento de facturas precompilados, consulte [Uso de un modelo precompilado para extraer información de facturas](prebuilt-model-invoice.md).

### <a name="receipt-processing"></a>Procesamiento de recibos

El modelo de procesamiento de recibos precompilado analiza y extrae información clave de los recibos de ventas. La API analiza los recibos impresos y manuscritos y extrae información de recibo de clave, como el nombre del comerciante, el número de teléfono del comerciante, la fecha de transacción, los impuestos y el total de la transacción.

Para obtener más información sobre los modelos de procesamiento de recibos precompilados, consulte [Uso de un modelo precompilado para extraer información de recibos](prebuilt-model-receipt.md).

## <a name="see-also"></a>Vea también

[Comparación de modelos personalizados en Microsoft Syntex](./difference-between-document-understanding-and-form-processing-model.md)

[Aprendizaje: mejorar el rendimiento empresarial con AI Builder](/learn/paths/improve-business-performance-ai-builder/?source=learn)
