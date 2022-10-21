---
title: Introducción al procesamiento de documentos de forma libre en Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Aprenda a usar AI Builder para crear modelos de procesamiento de documentos de forma libre en Microsoft Syntex.
ms.openlocfilehash: 7937fd738cfa011eada44f1f57b46f6e2af2e267
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68664374"
---
# <a name="overview-of-freeform-document-processing-in-microsoft-syntex"></a>Introducción al procesamiento de documentos de forma libre en Microsoft Syntex

Use el modelo de procesamiento de documentos de forma [libre (método de selección de forma libre](create-syntex-model.md#train-a-custom-model)) para extraer automáticamente información de documentos no estructurados y de forma libre, como cartas y contratos.

Microsoft Syntex usa el procesamiento de documentos de Microsoft Power Apps [AI Builder](/ai-builder/form-processing-model-overview) (anteriormente conocido como procesamiento de formularios) para crear modelos de procesamiento de documentos de forma libre en bibliotecas de documentos de SharePoint.
<!---
 ![AI Builder.](../media/content-understanding/ai-builder.png)
--->
Puede usar el procesamiento de documentos de AI Builder para crear modelos de procesamiento de documentos de forma libre que usen tecnología de aprendizaje automático para identificar y extraer pares clave-valor y datos de tabla de documentos no estructurados o de forma libre, como contratos y correspondencia.

A menudo, las organizaciones reciben documentos que no tienen estructura en grandes cantidades de diversos orígenes, como correo, fax y correo electrónico. Procesar estos documentos y escribirlos manualmente en una base de datos puede tardar mucho tiempo. Al usar la inteligencia artificial para extraer el texto, los pares clave-valor y las tablas de los documentos, Syntex automatiza este proceso. 

> [!NOTE]
> Para obtener más ideas sobre cómo usar estos modelos en su organización, consulte [Introducción a la adopción](adoption-getstarted.md) y [escenarios y casos de uso](adoption-scenarios.md).

Por ejemplo, puede crear un modelo de procesamiento estructurado de documentos que identifique todos los documentos cargados en la biblioteca de documentos. A partir de cada documento, puede extraer y mostrar datos específicos que son importantes para usted.

![Captura de pantalla que muestra la vista de la biblioteca de documentos.](../media/content-understanding/doc-lib-done.png) 

Use archivos de ejemplo para entrenar el modelo y definir la información que se extrae del formulario. El diseño del documento viene se aprende al entrenar el modelo. Solo necesita cinco documentos de formulario para empezar. Syntex analizará los archivos de ejemplo para los pares clave-valor y también puede identificar manualmente los que podrían no haberse detectado.  El generador de IA le permite probar la precisión de su modelo en los archivos de ejemplo.

Solo puede crear un modelo de procesamiento estructurado de documentos en bibliotecas de documentos de SharePoint para las que esté habilitado. Si se ha habilitado, puede ver la opción **Clasificar y extraer** en la biblioteca de documentos.

![Captura de pantalla que muestra el modelo de AI Builder.](../media/content-understanding/create-ai-builder-model2.png)

Si lo necesita habilitado en la biblioteca de documentos, póngase en contacto con el administrador de Microsoft 365.

## <a name="requirements"></a>Requisitos

Para obtener información sobre los requisitos que se deben tener en cuenta al elegir este modelo, consulte [Requisitos y limitaciones de los modelos de Microsoft Syntex](requirements-and-limitations.md#freeform-document-processing). 

## <a name="see-also"></a>Vea también

[Comparación de modelos personalizados](difference-between-document-understanding-and-form-processing-model.md)

[Entrenamiento de un modelo de procesamiento de documentos de forma libre](train-freeform-document-processing-model.md)