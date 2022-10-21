---
title: Introducción a los modelos precompilados en Microsoft Syntex
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
description: Obtenga información sobre los modelos precompilados en Microsoft Syntex.
ms.openlocfilehash: 0ec44b2f7b0b0360eedceadb71ddf9abdc6e2941
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68659157"
---
# <a name="overview-of-prebuilt-models-in-microsoft-syntex"></a>Introducción a los modelos precompilados en Microsoft Syntex

Además de [los modelos personalizados](model-types-overview.md#custom-models), Microsoft Syntex proporciona *modelos precompilados* para automatizar la extracción de información.

Los modelos precompilados se preconfiguran para reconocer documentos y la información estructurada en los documentos. En lugar de tener que crear un nuevo modelo personalizado desde cero, puede iterar en un modelo previamente entrenado existente para agregar campos específicos que se ajusten a las necesidades de su organización. 

Los modelos precompilados usan el reconocimiento óptico de caracteres (OCR) combinado con modelos de aprendizaje profundo para identificar y extraer campos de datos y texto predefinidos comunes a tipos de documentos específicos. Para empezar, analice uno de los archivos en el modelo precompilado. A continuación, seleccione los campos detectados que tengan sentido para su propósito. Si el modelo no detecta los campos que necesita, puede analizarlo de nuevo mediante un archivo diferente.

Al igual que otros modelos, los modelos precompilados se crean y administran en el [centro de contenido](create-a-content-center.md). Cuando se aplica a una biblioteca de documentos de SharePoint, el modelo está asociado a un tipo de contenido y tiene columnas para almacenar la información que se va a extraer. 

Después de publicar el modelo, utilice el centro de contenido para aplicarlo a cualquier biblioteca de documentos de SharePoint a la que tenga acceso.  

## <a name="available-prebuilt-models"></a>Modelos precompilados disponibles

Actualmente, hay dos modelos precompilados disponibles: [facturas](prebuilt-model-invoice.md) y [recibos](prebuilt-model-receipt.md).

- El *modelo de facturas* analiza y extrae información clave de las facturas de ventas. La API analiza las facturas en varios formatos y [extrae la información clave de la factura](/azure/applied-ai-services/form-recognizer/concept-invoice#field-extraction) , como el nombre del cliente, la dirección de facturación, la fecha de vencimiento y el importe vencido.

- El *modelo de recibos* analiza y extrae información clave de los recibos de ventas. La API analiza los recibos impresos y manuscritos y [extrae información de recibo de clave](/azure/applied-ai-services/form-recognizer/concept-receipt#field-extraction) , como el nombre del comerciante, el número de teléfono del comerciante, la fecha de transacción, los impuestos y el total de la transacción.

Los modelos precompilados adicionales estarán disponibles en futuras versiones.

## <a name="requirements"></a>Requisitos

Para obtener información sobre los requisitos que se deben tener en cuenta al elegir este modelo, consulte [Requisitos y limitaciones de los modelos de Microsoft Syntex](requirements-and-limitations.md). 

## <a name="see-also"></a>Vea también

[Uso de un modelo precompilado para extraer información de facturas](prebuilt-model-invoice.md)

[Uso de un modelo precompilado para extraer información de recibos](prebuilt-model-receipt.md)

 

