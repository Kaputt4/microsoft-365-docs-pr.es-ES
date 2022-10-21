---
title: Licencias para Microsoft Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.service: microsoft-syntex
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
ms.localizationpriority: high
description: Obtenga información sobre las licencias para Microsoft Syntex.
ms.openlocfilehash: 4b35810f1f8ed3e260f9d6cd83ccd9a36f15f32c
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68663354"
---
# <a name="licensing-for-microsoft-syntex"></a>Licencias para Microsoft Syntex

Para usar Microsoft Syntex, debe tener una licencia para cada usuario de Syntex. Si quita todas las licencias de Syntex del inquilino en una fecha futura (o la prueba expira), los usuarios ya no podrán crear, publicar ni ejecutar modelos personalizados. Además, los informes de almacén de términos, la importación de taxonomía SKOS y la inserción de tipo de contenido ya no estarán disponibles. No se eliminarán modelos, contenido ni metadatos y no se cambiarán los permisos del sitio.
 
> [!NOTE] 
> Syntex es una licencia de complemento y requiere que los usuarios también tengan una licencia para Microsoft 365.
 
## <a name="tasks-requiring-a-license"></a>Tareas que requieren una licencia
 
Las siguientes tareas requieren una [licencia de Syntex](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex) para el usuario que las realiza:
 
- Aplicar un modelo de procesamiento de documentos no estructurado a una biblioteca. (A los usuarios sin licencia se les puede conceder acceso a un centro de contenido y pueden crear modelos allí, pero no se pueden aplicar a una biblioteca de documentos).
- Crear un modelo de procesamiento estructurado de documentos o un modelo de procesamiento de documentos de forma libre a través del punto de entrada de una biblioteca
- Carga de contenido en una biblioteca donde se ha aplicado un modelo personalizado
- Ejecución de un modelo de procesamiento de documentos no estructurado a petición
- Creación de una plantilla moderna con ensamblado de contenido
- Generación de un documento a partir de una plantilla moderna
- Uso de la búsqueda avanzada de metadatos
- Uso de servicios de taxonomía premium. (Los servicios de taxonomía premium comprenden la importación de conjuntos de términos basados en SKOS, la inserción de tipos de contenido empresarial en sitios asociados al centro y los informes de almacén de términos).

A los usuarios sin licencia se les puede conceder acceso a un centro de contenido y pueden crear modelos allí, pero no pueden aplicarlos a una biblioteca de documentos.
 
## <a name="cost-of-training-and-running-models"></a>Costo de entrenamiento y ejecución de modelos
 
El costo de entrenamiento y ejecución de modelos de procesamiento de documentos no estructurados se incluye en el costo de una licencia de Syntex. Sin embargo, los modelos estructurados de procesamiento de documentos y procesamiento de documentos de forma libre usan la capacidad de AI Builder, tanto para el entrenamiento como para el procesamiento en tiempo de ejecución. Esta capacidad debe asignarse al entorno de Power Apps en el que se usará AI Builder.

Por cada licencia de Syntex, se le asignan 3.500 créditos de AI Builder por licencia, por mes agrupados en el nivel de inquilino, con una asignación máxima de 1 millón de créditos al mes. Esta asignación se renueva cada mes para cada licencia de Syntex activa. (Los créditos no usados no se acumulan de mes a mes). 

Puede estimar la capacidad del Generador de IA que lo hace adecuado para usted con la calculadora del [Generador de IA](https://powerapps.microsoft.com/ai-builder-calculator).

Si planea utilizar un entorno de Power Platform personalizado, debe [asignar créditos a ese entorno](/power-platform/admin/capacity-add-on).

Vaya al [Centro de administración de la Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) para comprobar sus créditos y el uso.
  
## <a name="additional-term-store-features"></a>Características adicionales del almacén de términos

Tener una o varias licencias de Syntex en su organización permite las siguientes características adicionales de almacén de términos para administradores de SharePoint:
 
- Importación del conjuntos de términos a partir de SKOS
- Insertar tipos de contenido empresarial en un sitio concentrador, que también los agrega a los sitios asociados y a las listas o bibliotecas recién creadas
- Informes del almacén de términos que proporcionan información sobre los conjuntos de términos publicados y su uso en todo el inquilino

## <a name="see-also"></a>Vea también

[Introducción a las licencias para Microsoft Power Platform](/power-platform/admin/pricing-billing-skus)

[Preguntas más frecuentes sobre licencias de Power Apps y Power Automate](/power-platform/admin/powerapps-flow-licensing-faq)
