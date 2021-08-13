---
title: Licencias para SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Más información sobre las licencias para SharePoint Syntex
ms.openlocfilehash: 08c3b078feb96f988fdf267246fb68356860677fbb00421b5322e9f6aa1904c2
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53824274"
---
# <a name="licensing-for-sharepoint-syntex"></a>Licencias para SharePoint Syntex

Para usar SharePoint Syntex, su organización debe tener una suscripción a SharePoint Syntex y cada usuario de Syntex debe tener una licencia. Si cancela su suscripción de SharePoint Syntex en una fecha futura (o la versión de prueba expira), los usuarios ya no podrán crear, publicar ni ejecutar modelos de comprensión de documentos o de procesamiento de formularios. Además, los informes de almacén de términos, la importación de taxonomía SKOS y la inserción de tipo de contenido ya no estarán disponibles. No se eliminarán modelos, ni contenido ni metadatos y no se cambiarán los permisos del sitio.
 
## <a name="tasks-requiring-a-license"></a>Tareas que requieren una licencia
 
Las siguientes tareas requieren una licencia de SharePoint Syntex para que el usuario las realice:
 
- Carga de contenido en una biblioteca de documentos que tiene un modelo de comprensión mediante documentos
- Ejecución manual de un modelo de comprensión mediante documentos
- Creación de un modelo de procesamiento de formularios mediante el punto de entrada en una biblioteca de SharePoint
- Carga de contenido en una biblioteca en la que se ha aplicado un modelo de procesamiento de formularios
- Visualización de los metadatos extraídos de los archivos mediante un modelo de comprensión mediante documentos o de procesamiento de formularios
 
A los usuarios sin licencia se les puede conceder acceso a un centro de contenido y pueden crear modelos de comprensión mediante documentos allí, pero no pueden aplicarlos a una biblioteca de documentos.
 
## <a name="cost-of-running-models"></a>El coste de la ejecución de modelos
 
El coste de ejecutar modelos de comprensión mediante documentos se incluye en el coste de una licencia de SharePoint Syntex. Sin embargo, los modelos de procesamiento de formularios usan las capacidades de AI Builder, tanto para el entrenamiento como para el procesamiento en tiempo de ejecución. Esta capacidad debe asignarse al entorno de Power Apps en el que se usará AI Builder.
 
Si tiene 300 o más licencias de SharePoint Syntex en su organización, se le asignará un millón de créditos del Generador de IA. La capacidad se renueva cada mes si mantiene el mínimo de 300 licencias (los créditos no usados en un mes no se traspasan al siguiente). Si tiene menos de 300 licencias, debe comprar créditos de AI Builder para poder utilizar el procesamiento de formularios.
 
Puede estimar la capacidad del Generador de IA que lo hace adecuado para usted con la calculadora del [Generador de IA](https://powerapps.microsoft.com/ai-builder-calculator).

Si planea utilizar un entorno de Power Platform personalizado, debe [asignar créditos a ese entorno](/power-platform/admin/capacity-add-on).

Vaya al [Centro de administración de la Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) para comprobar sus créditos y el uso.
  
## <a name="additional-term-store-features"></a>Características adicionales del almacén de términos
 
Una suscripción a SharePoint Syntex incluye las siguientes características adicionales del almacén de términos:
 
- Importación del conjuntos de términos a partir de SKOS
- Insertar tipos de contenido empresarial en un sitio concentrador, que también los agrega a los sitios asociados y a las listas o bibliotecas recién creadas
- Informes del almacén de términos que proporcionan información sobre los conjuntos de términos publicados y su uso en todo el inquilino


## <a name="see-also"></a>Vea también

[Introducción a las licencias para Microsoft Power Platform](/power-platform/admin/pricing-billing-skus)

[Preguntas más frecuentes sobre licencias de Power Apps y Power Automate](/power-platform/admin/powerapps-flow-licensing-faq)
