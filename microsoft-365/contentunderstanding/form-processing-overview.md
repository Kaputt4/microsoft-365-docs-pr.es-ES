---
title: Información general sobre el procesamiento de formularios (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre el procesamiento de formularios en Project Cortex.
ms.openlocfilehash: de8e0ed546380059cc1b7b209eeec71f1eb779f9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950029"
---
# <a name="form-processing-overview-preview"></a>Información general sobre el procesamiento de formularios (versión preliminar)
> [!Note]
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).

Project Cortex usa el procesamiento de formularios de Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) para crear modelos dentro de las bibliotecas de documentos de SharePoint.
Puede usar el procesamiento de formularios del generador de AI para crear modelos AI que usen la tecnología de aprendizaje automático para identificar y extraer pares de valores clave y datos de tabla de documentos estructurados o semiestructurados, como formularios y facturas.

Las empresas a menudo reciben facturas en grandes cantidades y en una gran variedad de orígenes, como correo, fax, correo electrónico o en persona. El procesamiento de estos documentos y su introducción manual en la base de datos puede tardar una cantidad considerable de tiempo. Mediante el uso de AI para extraer el texto, los pares clave/valor y las tablas de los documentos, el procesamiento de formularios automatizará este proceso. 

Por ejemplo, puede crear un modelo de procesamiento de formularios que identifique todos los documentos de pedido de compra que se cargan en la biblioteca de documentos. Y de cada pedido de compra puede extraer y Mostrar datos específicos que sean importantes para usted, como *número de pedido*, *fecha*o *coste total*.

Los archivos de ejemplo se usan para entrenar el modelo y definir la información que se va a extraer del formulario. El diseño del documento se conoce mediante el entrenamiento del modelo. Solo necesita cinco documentos de formulario para empezar. El generador de AI analizará los archivos de ejemplo para los pares clave-valor, y también puede identificar manualmente aquellos que no se hayan detectado.  El generador de AI permite probar la precisión del modelo en los archivos de ejemplo.

Después de entrenar y publicar el modelo, puede usarlo para crear un [flujo de automatización de energía](https://docs.microsoft.com/power-automate/getting-started). El flujo se ejecuta cuando un archivo se carga en la biblioteca de documentos de SharePoint y extrae los datos identificados en el modelo. Los datos extraídos se mostrarán en columnas en la vista de la biblioteca de documentos del modelo.

Un administrador de Office 365 debe [Habilitar el procesamiento de formularios](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) para la biblioteca de documentos de SharePoint para que los usuarios puedan [crear un modelo de procesamiento de formularios](create-a-form-processing-model.md) en él.



## <a name="see-also"></a>Vea también
  
[Documentación automatizada de la energía](https://docs.microsoft.com/power-automate/)</br>
[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)</br>
[Información general sobre el documento](document-understanding-overview.md)</br>
[Aprendizaje: mejorar el rendimiento empresarial con el generador de AI](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




