---
title: Introducción al procesamiento de formularios
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre el procesamiento de formularios en Microsoft SharePoint Syntex
ms.openlocfilehash: 518bc13017762bbe21420a81726e89c9c327834d
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295181"
---
# <a name="form-processing-overview-preview"></a>Información general sobre el procesamiento de formularios (versión preliminar)

El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).

Project Cortex usa el procesamiento de formularios de Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) para crear modelos dentro de las bibliotecas de documentos de SharePoint.

Puede usar el procesamiento de formularios del generador de AI para crear modelos AI que usen la tecnología de aprendizaje automático para identificar y extraer pares de valores clave y datos de tabla de documentos estructurados o semiestructurados, como formularios y facturas.

Use el procesamiento de formularios del generador de AI para crear modelos AI que utilicen la tecnología de machine learning (ML) para identificar y extraer pares clave-valor y datos de tabla de documentos estructurados o semiestructurados, como formularios y facturas.

Las organizaciones a menudo reciben facturas en grandes cantidades de diversos orígenes, como correo, fax, correo electrónico, etc. El procesamiento de estos documentos y su introducción manual en una base de datos puede llevar una cantidad considerable de tiempo. Mediante el uso de AI para extraer el texto, los pares clave/valor y las tablas de los documentos, el procesamiento de formularios automatiza este proceso. 

Por ejemplo, puede crear un modelo de procesamiento de formularios que identifique todos los documentos de pedido de compra que se cargan en la biblioteca de documentos. Desde cada pedido de compra, puede extraer y Mostrar datos específicos que sean importantes para usted, como *número de pedido*, *fecha*o *coste total*.

También puede usar archivos de ejemplo para entrenar el modelo y definir la información que se va a extraer del formulario. El diseño del documento se conoce mediante el entrenamiento del modelo. Necesitará un mínimo de cinco documentos de formulario para comenzar. La creación de AI analiza los archivos de ejemplo para ver los pares clave-valor y, a continuación, identifica de forma manual los que no se han detectado.  El generador de AI permite probar la precisión del modelo en los archivos de ejemplo.

Después de entrenar y publicar el modelo, úselo para crear un [flujo de automatización energética](https://docs.microsoft.com/power-automate/getting-started) que se ejecuta después de que se cargue un archivo en la biblioteca de documentos de SharePoint. A continuación, se extraen los datos identificados en el modelo. Los datos extraídos se mostrarán en columnas en la vista de la biblioteca de documentos del modelo.

Use archivos de ejemplo para entrenar el modelo y definir la información que se extraerá del formulario. El diseño del documento se conoce mediante el entrenamiento del modelo. Solo necesita cinco documentos de formulario para empezar. El generador de AI analizará los archivos de muestra de los pares clave-valor, y también puede identificar manualmente aquellos que no se hayan detectado.  El generador de AI permite probar la precisión del modelo en los archivos de ejemplo.

Después de entrenar y publicar el modelo, puede usarlo para crear un [flujo de automatización de energía](https://docs.microsoft.com/power-automate/getting-started). El flujo se ejecuta cuando un archivo se carga en la biblioteca de documentos de SharePoint y extrae los datos identificados en el modelo. Los datos extraídos se mostrarán en columnas en la vista de la biblioteca de documentos del modelo.

Un administrador de Office 365 debe [Habilitar el procesamiento de formularios](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) para la biblioteca de documentos de SharePoint para que los usuarios puedan [crear un modelo de procesamiento de formularios](create-a-form-processing-model.md) en él.

## <a name="see-also"></a>Consulte también
  
[Documentación automatizada de la energía](https://docs.microsoft.com/power-automate/)</br>
[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)</br>
[Información general sobre el documento](document-understanding-overview.md)</br>
[Aprendizaje: mejorar el rendimiento empresarial con el generador de AI](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
