---
title: Introducción al ensamblado de contenido en Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: anrasto, shrganguly
ms.topic: article
ms.service: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre cómo crear documentos y otro contenido mediante una plantilla moderna en Microsoft Syntex.
ms.openlocfilehash: 62016db6ee47a94c0b7c22ac8173b89c8150cc5f
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2022
ms.locfileid: "68564128"
---
# <a name="overview-of-content-assembly-in-microsoft-syntex"></a>Introducción al ensamblado de contenido en Microsoft Syntex

Puede usar las funcionalidades de ensamblado de contenido de Microsoft Syntex para ayudarle a generar automáticamente documentos empresariales repetitivos estándar, como contratos, declaraciones de trabajo, contratos de servicio, cartas de consentimiento, lanzamientos de ventas y correspondencia. Puede realizar todas estas acciones de forma más rápida, coherente y con menos errores creando plantillas modernas y usando esas plantillas para generar documentos.

![Diagrama del flujo de creación de documentos a partir de una plantilla moderna.](../media/content-understanding/content-assembly-diagram.png)

Cargue un documento existente para crear una plantilla moderna y, a continuación, use esa plantilla para generar automáticamente contenido nuevo mediante listas de SharePoint o entradas manuales como origen de datos.

> [!NOTE]
> Debe ser un usuario con licencia de Syntex para acceder a las funcionalidades de ensamblado de contenido y usarlas. También debe tener permisos para administrar listas de SharePoint.


## <a name="requirements-and-limitations"></a>Requisitos y limitaciones

### <a name="supported-file-types"></a>Tipos de archivo compatibles

Actualmente solo se admiten documentos de Microsoft Word (.docxextensión /.doc) para crear una plantilla.

### <a name="file-limitations"></a>Limitaciones de archivos

- El documento de Word que desea usar como plantilla moderna no debe incluir comentarios ni tener habilitado El seguimiento de cambios.

- Dado que los controles de contenido se usan en Word para crear campos para la plantilla moderna, asegúrese de que los marcadores de posición de texto de las imágenes no estén encapsulados en texto. Si el documento ya contiene controles de contenido, quítelos antes de usarlos para crear una plantilla moderna.

### <a name="current-release-limitations"></a>Limitaciones actuales de la versión

- La plantilla y el documento están asociados a una biblioteca de documentos. Para usar la plantilla en otra biblioteca de documentos, deberá volver a crearla en esa biblioteca de documentos.

- El documento cargado que se usa para crear la plantilla moderna se guardará como una copia independiente y se colocará en el directorio /forms de la biblioteca de documentos. El archivo original del disco no se verá afectado.

- Puede crear campos para texto y también campos para texto dentro de las celdas de una tabla. Sin embargo, actualmente no se admiten imágenes, arte inteligente, tablas completas y listas con viñetas.

- Una vez que se crea un documento a partir de una plantilla, no está asociado a la plantilla.

## <a name="differences-between-modern-templates-and-other-document-templates"></a>Diferencias entre plantillas modernas y otras plantillas de documento

|Característica  |Plantillas modernas  |Otras plantillas  |
|---------|---------|---------|
|Licencias      |Licencia de Syntex necesaria para acceder a esta oferta.  |Se ofrece como parte de la licencia de Microsoft E3 o E5.  |
|Cuándo usar cada uno            | Debe usar para generar documentos transaccionales estándar, como contratos de servicio e instrucciones de trabajo, cuando solo cambien partes específicas del documento. Los documentos generados a partir de plantillas modernas garantizan la coherencia y menos posibilidades de errores manuales y errores tipográficos que se producen cuando los usuarios cambian las secciones del documento en flujo libre.  |Debe usar este método cuando desee establecer un documento como ejemplo para que otros usuarios hagan referencia. Puede considerar el uso de plantillas regulares para documentos no transaccionales, como lanzamientos de ventas o resúmenes ejecutivos.  |
|Estandarización de la generación de contenido |Puede agregar campos y asociarlos a varios orígenes de datos solo para secciones específicas del contenido con el fin de facilitar a los usuarios la generación de documentos una vez publicada la plantilla.  |Una vez cargado, el archivo se mantiene tal y como está en la plantilla. Cualquier usuario que use la plantilla tiene que cambiar el contenido en consecuencia.   |
|Orígenes de datos admitidos     |Puede asociar campos con listas de SharePoint y almacén de términos al crear plantillas.   |No aplicable   |
|Tipos de documento admitidos    |Actualmente solo se admiten documentos de Microsoft Word (.docxextensión /.doc) para crear una plantilla.  |Puede usar cualquier archivo para cargarlo como plantilla.   |
|Administración de plantillas    |Una vez creada la plantilla, puede editar o administrar los campos de plantilla, cambiar el nombre de la plantilla y volver a publicarla para su uso.  |No aplicable   |
|Borrador de versión de plantillas |Puede crear versiones de borrador de plantillas antes de publicarlas finalmente para que la usen otros usuarios.   |No hay ninguna capacidad para crear borradores de plantillas regulares.  |
|Flujos de trabajo   |Puede automatizar la generación de documentos a partir de plantillas [mediante la configuración de flujos de trabajo de Power Automate](automate-document-generation.md).  |Los flujos de trabajo no se pueden configurar con plantillas regulares.  |

> [!div class="nextstepaction"]
> [Introducción > Creación de una plantilla moderna](content-assembly-modern-template.md)



 
