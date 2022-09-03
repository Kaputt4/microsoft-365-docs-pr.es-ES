---
title: Resumen del procesamiento de formularios en Microsoft SharePoint Syntex
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
description: Obtenga información sobre cómo usar la compilación de IA para crear modelos de procesamiento de formularios en Microsoft SharePoint Syntex.
ms.openlocfilehash: 8bcb5874ce62b8125e385fcf9eca8dbd2ca9f0fa
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585254"
---
# <a name="form-processing-overview-in-microsoft-sharepoint-syntex"></a>Resumen del procesamiento de formularios en Microsoft SharePoint Syntex

 ![Generador de IA.](../media/content-understanding/ai-builder.png)</br>

Microsoft SharePoint Syntex usa el procesamiento de formularios del [generador de IA](/ai-builder/overview) de Microsoft PowerApps para crear modelos en las bibliotecas de documentos de SharePoint.

Puede usar el procesamiento de formularios de AI Builder para crear modelos de inteligencia artificial que usen tecnología de aprendizaje automático para identificar y extraer pares clave-valor y datos de tabla de documentos estructurados o semiestructurados, como formularios y facturas.

Las organizaciones suelen recibir facturas en grandes cantidades de diversos orígenes, como correo, fax y correo electrónico. Procesar estos documentos y escribirlos manualmente en una base de datos puede tardar mucho tiempo. Mediante el uso de IA para extraer el texto, los pares clave o de valor y las tablas de los documentos, el procesamiento de formularios automatiza este proceso. 

> [!NOTE]
> Consulte la guía [Adopción de SharePoint Syntex: Guía de introducción](./adoption-getstarted.md) para obtener más información sobre ejemplos de escenarios de procesamiento de formularios.

Por ejemplo, puede crear un modelo de procesamiento de formularios que identifique todos los documentos de pedido de compra que se hayan cargado en la biblioteca de documentos. A partir de cada pedido de compra, puede extraer y mostrar datos específicos que son importantes para usted, como *el número de pedido* de compra, *la fecha* o el *costo total*.

![Vista de la biblioteca de documentos.](../media/content-understanding/doc-lib-done.png)</br>  

Use archivos de ejemplo para entrenar el modelo y definir la información que se extrae del formulario. El diseño del documento viene se aprende al entrenar el modelo. Solo necesita cinco documentos de formulario para empezar. AI Builder analizará los archivos de ejemplo para los pares clave-valor y también puede identificar manualmente los que podrían no haberse detectado.  El generador de IA le permite probar la precisión de su modelo en los archivos de ejemplo.

Después de entrenar y publicar el modelo, el modelo crea un [flujo de Power Automate](/power-automate/getting-started). El flujo se ejecuta cuando se carga un archivo en la biblioteca de documentos de SharePoint y se extraen los datos identificados en el modelo. Los datos extraídos se mostrarán en columnas en la vista de la biblioteca de documentos del modelo.

Un administrador de Office 365 debe [habilitar el procesamiento de formularios](./set-up-content-understanding.md) para la biblioteca de documentos de SharePoint para que los usuarios puedan [crear un modelo de procesamiento de formularios](create-a-form-processing-model.md) en ella. Puede seleccionar los sitios durante la instalación o después de la misma, en la configuración de administración.

## <a name="file-limitations"></a>Limitaciones de archivos

Al usar modelos de procesamiento de formularios, asegúrese de tener en cuenta las [limitaciones específicas para el uso de archivos](/ai-builder/form-processing-model-requirements).

## <a name="supported-languages"></a>Idiomas admitidos

El procesamiento de formularios admite documentos en más de 73 idiomas. Para obtener la lista de idiomas, consulte [Compatibilidad con el lenguaje de procesamiento de formularios](/power-platform-release-plan/2021wave2/ai-builder/form-processing-new-language-support).

## <a name="multi-geo-environments"></a>Entornos de Multi-Geo

Al configurar SharePoint Syntex en un [entorno de Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md), solo puede configurarlo para usar el procesamiento de formularios en la ubicación central. Si quiere utilizar el procesamiento de formularios en una ubicación satélite, póngase en contacto con el Soporte técnico de Microsoft.

## <a name="custom-environments"></a>Entornos personalizados

Si usa un entorno personalizado (en lugar del entorno predeterminado) para el procesamiento de Power Platform, hay requisitos de configuración adicionales. Para obtener más información, consulte [Entornos de Power Platform personalizados](set-up-content-understanding.md#requirements).


## <a name="see-also"></a>Vea también
  
[Documentación de Power Automate](/power-automate/)

[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)

[Información general sobre la comprensión de documentos](document-understanding-overview.md)

[Aprendizaje: mejorar el rendimiento empresarial con el generador de IA](/learn/paths/improve-business-performance-ai-builder/?source=learn)