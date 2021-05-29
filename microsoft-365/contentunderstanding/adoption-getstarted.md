---
title: 'Adopción de Microsoft SharePoint Syntex: Introducción'
description: Obtenga información sobre cómo usar e implementar SharePoint Syntex en su organización para ayudarle a resolver sus problemas empresariales.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 62e65f9be25e2c482cca78577048d504ee93097a
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698981"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Adopción de Microsoft SharePoint Syntex: Introducción

Piense en los servicios de contenido inteligente disponibles en SharePoint Syntex como que tienen tres partes:

- **Descripción del contenido:** Cree modelos de IA sin código para clasificar y extraer información del contenido para aplicar automáticamente metadatos para la detección y reutilización de conocimientos. Obtenga más información sobre [la comprensión del contenido](document-understanding-overview.md).
- **Procesamiento de contenido:** Automatice la captura, la ingesta y la categorización del contenido y optimice los procesos centrados en el contenido mediante Power Automate. Obtenga más información sobre [el procesamiento de contenido](form-processing-overview.md).
- **Cumplimiento de contenido:** Controle y administre el contenido para mejorar la seguridad y el gobierno con la integración en Microsoft Information Protection.

Con los nuevos servicios y capacidades de IA, puedes crear aplicaciones de clasificación y comprensión de contenido directamente en el flujo de administración de contenido mediante SharePoint Syntex. Hay dos formas diferentes de comprender el contenido. El tipo de modelo que use se basa en el formato de archivo y el caso de uso:

| Procesamiento de formularios | Comprensión mediante documentos |
|:-------|:-------|
| Creado a partir de la biblioteca de documentos. | Creado en el centro de contenido, parte de SharePoint Syntex. |
| Modelo creado en el generador de IA. | Modelo creado en interfaz nativa. |
| Se usa para formatos de archivo semiestructurados. | Se usa para formatos de archivo no estructurados. |
| Clasificador configurable. | Clasificador entrenable con extractores opcionales. |
| Restringido a una sola biblioteca. | Se puede aplicar a múltiples bibliotecas. |
| Train on PDF, JPG, PNG format, total 50 MB/500 pp. | Entrenado en 5-10 archivos de PDF, Office o correo electrónico, incluyendo ejemplos negativos. |

Para obtener una comparación más completa de las capacidades, vea Diferencia entre la comprensión [de documentos y los modelos de procesamiento de formularios.](difference-between-document-understanding-and-form-processing-model.md)

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identificar escenarios empresariales piloto para optimizar

Para prepararse para usar SharePoint Syntex en su organización, primero debe comprender los escenarios en los que será útil. El "por qué" ayuda a determinar qué modelo se necesita y cómo estructurar la organización en función de dónde se aplicará el modelo. Estos son algunos escenarios en los que la comprensión de documentos puede ayudar a su organización:

- **Procesamiento de contenido:** Procesar contratos, instrucciones de trabajo y otros documentos con formato. Admisión de formularios, entrenar al modelo para comprender y asignar los campos y, a continuación, ejecutar los formularios para recopilar automáticamente los datos. Para obtener más información, vea [Información general sobre el procesamiento de formularios.](form-processing-overview.md)
- **Análisis de facturas:** Extrae los detalles relevantes de tus facturas y asegúrate de que cumplen con la directiva o se están procesando correctamente.

Piense en las formas en que SharePoint Syntex puede ayudar a su organización:

- Automatizar procesos empresariales
- Mejorar la precisión de búsqueda
- Administrar el riesgo de cumplimiento

Cuando piense en qué escenarios empresariales debe tener en cuenta, haga las siguientes preguntas:

- ¿Resuelve un problema real?
- ¿Se usará ampliamente o tendrá un impacto general?
- ¿Se puede obtener?
- ¿Puede medir el éxito?

Priorizar escenarios en función del impacto y la facilidad de implementación. Haga que el área de enfoque inicial tenga un mayor impacto en escenarios que también se puedan implementar fácilmente. Des priorizar escenarios de menor impacto que son difíciles de implementar.

Use los [escenarios de ejemplo y los casos de uso](adoption-scenarios.md) para preguntar ideas sobre cómo puede usar SharePoint Syntex en su organización.

## <a name="identify-roles--responsibilities"></a>Identificar roles & responsabilidades

Determine who in your organization will build and manage the models? Los siguientes roles pueden estar implicados:

| SharePoint/Administrador de conocimientos | Administrador de Power Platform | Administrador de conocimientos | Propietario del modelo |
|:-------|:-------|:-------|:-------|
| Rol AAD| Rol AAD | Rol AAD | Expertos: |
| Configurar el procesamiento del formulario | Configurar el entorno de servicio de datos común para el procesamiento de formularios | Recopilar casos de uso | Recopilar casos de uso empresarial |
| Administrar centros de contenido y permisos| Comprar y asignar créditos AIB | Establecer procedimientos recomendados y revisar análisis de modelos | Crear y aplicar modelos |

El administrador de conocimientos, el propietario del proceso de negocio y el propietario del modelo de contenido crean modelos de ejemplo y la adopción de campeones en la organización.
Otros que pueden estar implicados: administrador de cumplimiento, administradores de taxonomía.

¿Dónde crearán y aplicarán los modelos? ¿Hay procesos o repositorios existentes que podrían mejorarse?

- Procesamiento de formularios: decida qué sitios recibirán acción de procesamiento de formularios.
- Descripción del documento: puede crear varios centros de contenido para distintas áreas de negocio.

## <a name="strategic-positioning"></a>Posicionamiento estratégico

Trabaje con las partes interesadas para asegurarse de que están alineados en la estrategia para usar SharePoint Syntex. Investigue y proporcione los siguientes recursos para ayudarle con este posicionamiento:

- Resultados empresariales:
  - Posibles resultados fiscales
  - Posibles resultados de agilidad
  - Plantilla de resultados empresariales
- Stakeholders/Exec sponsor buy-in/alignment
  - Barajas de casos profesionales
  - Modelos financieros
  - Preparación de la empresa: cultura

## <a name="identify-stakeholders"></a>Identificación de las partes interesadas

Identifique las partes interesadas del proyecto.

|Rol |Responsabilidades |Departamento |
|:-------|:-------|:--------|
| Patrocinadores ejecutivos   | Comunicar a la empresa valores y visión de alto nivel   |  Liderazgo ejecutivo   |
| Project clientes potenciales | Supervisar todo el proceso de ejecución e implementación del lanzamiento | Administración de proyectos |
| Administradores de información| Crear y administrar los centros de contenido | TI u otro departamento|
| Administradores de contenido y propietarios de modelos| Recopilar casos de uso y crear y aplicar modelos | Cualquier departamento|
| Expertos: | Ayudar a promocionar y administrar el tratamiento de objeción | Cualquier departamento (personal) |
| Administrador de inquilinos | Configurar la configuración de nivel de inquilino | Departamento de TI|
| Administrador de Power Platform| Configurar el entorno de servicios de datos comunes | Departamento de TI|

> [!Note]
> Aunque se recomienda que cada uno de estos roles se cumpla a lo largo de la implementación, es posible que no necesite todos ellos para empezar con la solución identificada.

## <a name="readiness-checklist"></a>Lista de comprobación de preparación

Para prepararse para implementar SharePoint Syntex, debe:

![Preparación para la comprensión del contenido](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Planear el estado final
    - Los modelos de comprensión de documentos son los medios, no el final.
    - Planee aprovechar el valor de los metadatos extraídos con:
      - Búsqueda
      - Filtrado y formato de vista
      - Cumplimiento
      - Automatización
2. Identificación
    - Comprender la arquitectura de la información existente y el uso de características de administración de contenido.
    - ¿Los tipos de contenido existentes son buenos candidatos para los modelos?
    - ¿Qué procesos existentes se mejorarían con los metadatos?
3. Diseño
    - Diseñar el enfoque de la arquitectura de la información, los metadatos administrados y los tipos de contenido
    - Diseñe el proceso de definición, creación, administración.

## <a name="engage-your-organization"></a>Interactuar con su organización

1. Identificar a los poseedores de participación, confirmar escenarios y desarrollar un plan de proyecto.
1. Configure la configuración y aplique licencias.
1. Comenzar a concienciar y entrenar: reclutar a los campeones.
1. Roll out in stages.  
1. Recopilar comentarios e iterar.
1. A medida que aumenta el uso, planee los créditos de AI Builder según sea necesario.

## <a name="see-also"></a>Consulte también

[Escenarios y casos de uso para SharePoint Syntex](adoption-scenarios.md)