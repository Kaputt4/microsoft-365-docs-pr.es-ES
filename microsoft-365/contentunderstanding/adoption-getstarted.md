---
title: Introducción a la adopción de Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.date: ''
audience: admin
ms.topic: article
ms.service: microsoft-syntex
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
ms.localizationpriority: medium
description: Obtenga información sobre cómo usar e implementar Microsoft Syntex en su organización para ayudar a simplificar los procesos empresariales.
ms.openlocfilehash: e824356fb5c729a6a508abebecffd4b6ea0c6e45
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660585"
---
# <a name="get-started-driving-adoption-of-microsoft-syntex"></a>Introducción a la adopción de Microsoft Syntex

Considere que los servicios de contenido inteligente disponibles en Microsoft Syntex tienen tres partes:

- **Comprensión del contenido:** Cree modelos de inteligencia artificial sin código para clasificar y extraer información del contenido para aplicar automáticamente metadatos para la detección y reutilización de conocimientos. Obtenga más información sobre la [comprensión del contenido](document-understanding-overview.md).
- **Procesamiento de contenido:** Automatice la captura, la ingesta y la categorización del contenido y optimice los procesos centrados en el contenido mediante Power Automate. Obtenga más información sobre el [procesamiento de contenido](form-processing-overview.md).
- **Cumplimiento de contenido:** Controlar y administrar el contenido para mejorar la seguridad y la gobernanza con la integración para Microsoft Purview Information Protection.

Con los nuevos servicios y funcionalidades de inteligencia artificial, puede crear aplicaciones de clasificación y comprensión de contenido directamente en el flujo de administración de contenido mediante Syntex. En el caso de los tipos de modelo personalizados, hay tres maneras diferentes de comprender el contenido. El tipo de modelo personalizado que se usa se basa en el formato de archivo y el caso de uso.

| Procesamiento de documentos no estructurados | Procesamiento estructurado de documentos | Procesamiento de documentos de forma libre |
| ------- | ------- | ------- |
| Creado en el centro de contenido, parte de Syntex. | Creado a partir de la biblioteca de documentos. | Creado a partir de la biblioteca de documentos. |
| Modelo creado en la interfaz nativa. | Modelo creado en el generador de inteligencia artificial. | Modelo creado en el generador de inteligencia artificial. |
| Se usa para formatos de archivo semiestructurados o no estructurados. | Se usa para formatos de archivo estructurados o semiestructurados. | Se usa para formatos de archivo no estructurados o de forma libre. |
| Clasificador entrenable con extractores opcionales. | Clasificador settable. | Clasificador settable. |
| Se puede aplicar a múltiples bibliotecas. | Restringido a una sola biblioteca. | Restringido a una sola biblioteca. |
| Entrenado en 5-10 archivos de PDF, Office o correo electrónico, incluyendo ejemplos negativos. | Entrenar en formato PDF, JPG, PNG, total 50 MB/500 pp. | Entrenar en formato PDF, JPG, PNG, total 50 MB/500 pp. |

Para obtener una comparación más completa de las funcionalidades personalizadas, consulte [Comparación de modelos personalizados en Syntex](difference-between-document-understanding-and-form-processing-model.md).

Si no necesita crear un modelo personalizado, puede usar un [modelo precompilado](prebuilt-overview.md) que ya se haya entrenado para documentos estructurados específicos.

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identificación de escenarios empresariales piloto para optimizar

Para prepararse para usar Syntex en su organización, primero debe comprender los escenarios en los que será útil. El "por qué" ayuda a determinar qué modelo se necesitará y cómo estructurar la organización en función de dónde se aplicará el modelo. Estos son algunos escenarios en los que los modelos personalizados pueden ayudar a su organización:

- **Procesamiento de contenido**: procesar contratos, instrucciones de trabajo y otros documentos similares a formularios. Admisión de los formularios, entrenamiento del modelo para comprender y asignar los campos y, a continuación, ejecute los formularios a través de para recopilar automáticamente los datos.

- **Análisis de facturas**: extraiga los detalles pertinentes de las facturas y asegúrese de que cumplen con la directiva o que se están procesando correctamente.

Piense en las formas en que Syntex puede ayudar a su organización:

- Automatizar procesos de negocio
- Mejora de la precisión de la búsqueda
- Administración del riesgo de cumplimiento

Cuando piense en qué escenarios empresariales debe tener en cuenta, hágase las siguientes preguntas:

- ¿Soluciona un problema real?
- ¿Se usará ampliamente o tendrá un impacto amplio?
- ¿Se puede obtener?
- ¿Puede medir el éxito?

Priorice los escenarios en función del impacto y la facilidad de implementación. Haga que el área de enfoque inicial tenga escenarios de mayor impacto que también se puedan implementar fácilmente. Desescen los escenarios de menor impacto que son difíciles de implementar.

Use los [escenarios de ejemplo y los casos de uso](adoption-scenarios.md) para preguntar ideas sobre cómo puede usar Syntex en su organización.

## <a name="identify-roles-and-responsibilities"></a>Identificar los roles y las responsabilidades

Determine quién en su organización compilará y administrará los modelos. Los siguientes roles pueden estar implicados.

| Administrador de conocimiento/SharePoint | Administrador de Power Platform | Responsable de la información | Propietario del modelo |
|:-------|:-------|:-------|:-------|
| Rol de AAD| Rol de AAD | Rol de AAD | Expertos |
| Configuración del procesamiento estructurado de documentos y modelos de procesamiento de documentos de forma libre | Configuración del entorno de Dataverse | Recopilación de casos de uso | Recopilación de casos de uso empresarial |
| Administración de centros de contenido y permisos| Compra y asignación de créditos de AIB | Establecimiento de procedimientos recomendados y revisión del análisis de modelos | Creación y aplicación de modelos |

El administrador de conocimiento, el propietario de procesos empresariales y el propietario del modelo de contenido crean modelos de ejemplo y abogan por la adopción en la organización. Otros que podrían estar implicados en el administrador de cumplimiento y los administradores de taxonomía.

¿Dónde compilarán y aplicarán los modelos? ¿Hay procesos o repositorios existentes que se puedan mejorar?

- Procesamiento de documentos no estructurados: puede crear varios centros de contenido para diferentes áreas de negocio.
- Procesamiento estructurado de documentos o procesamiento de documentos de forma libre: decida qué sitios obtendrán esta acción.

## <a name="strategic-positioning"></a>Posicionamiento estratégico

Trabaje con las partes interesadas para asegurarse de que están alineadas en la estrategia para usar Syntex. Investigue y proporcione los siguientes recursos para ayudar con este posicionamiento:

- Resultados empresariales:
  - Posibles resultados fiscales
  - Posibles resultados de agilidad
  - Plantilla de resultados empresariales
- Participación/alineación de patrocinadores de stakeholders/Exec
  - Cubiertas de casos empresariales
  - Modelos financieros
  - Preparación de la empresa: referencia cultural

## <a name="identify-stakeholders"></a>Identificación de las partes interesadas

Identifique las partes interesadas del proyecto.

|Rol |Responsabilidades |Departamento |
|:-------|:-------|:--------|
| Patrocinador ejecutivo   | Comunicar a la empresa valores y visión de alto nivel   |  Liderazgo ejecutivo   |
| Cliente potencial del proyecto | Supervisar todo el proceso de ejecución e implementación del lanzamiento | Administración de proyectos |
| Administradores de información| Creación y administración de centros de contenido | TI u otro departamento|
| Administradores de contenido y propietarios de modelos| Recopilación de casos de uso y creación y aplicación de modelos | Cualquier departamento|
| Expertos: | Ayudar a promocionar y administrar el tratamiento de objeción | Cualquier departamento (personal) |
| Administrador de inquilinos | Configurar la configuración de nivel de inquilino | Departamento de TI|
| Administrador de Power Platform| Configuración del entorno de Dataverse | Departamento de TI|

> [!NOTE]
> Aunque se recomienda que cada uno de estos roles se cumpla a lo largo de la implementación, es posible que no los necesite para empezar a trabajar con la solución identificada.

## <a name="readiness-checklist"></a>Lista de comprobación de preparación

Para prepararse para implementar Syntex, debe:

![Preparación para la comprensión del contenido.](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Planear el estado final
    - Los modelos son los medios, no el final.
    - Planee aprovechar el valor de los metadatos extraídos con:
      - Búsqueda
      - Filtrado y formato de vista
      - Cumplimiento
      - Automatización
2. Identificación
    - Descripción de la arquitectura de información existente y el uso de características de administración de contenido.
    - ¿Los tipos de contenido existentes son buenos candidatos para los modelos?
    - ¿Qué procesos existentes mejorarían los metadatos?
3. Diseño
    - Diseñe el enfoque para la arquitectura de la información, los metadatos administrados y los tipos de contenido.
    - Diseñe el proceso para la definición, creación y administración.

## <a name="engage-your-organization"></a>Interacción con la organización

1. Identifique a los titulares de participación, confirme los escenarios y desarrolle un plan de proyecto.
2. Configure los valores y aplique licencias.
3. Comience a concienciar y entrenar: recluta a los campeones.
4. Implementación en fases.  
5. Recopilar comentarios e iterar.
6. A medida que aumenta el uso, planifique los créditos de AI Builder según sea necesario.

## <a name="see-also"></a>Vea también

[Centro de adopción de Microsoft Syntex](https://adoption.microsoft.com/sharepoint-syntex/adoption/)

[Escenarios y casos de uso para Microsoft Syntex](adoption-scenarios.md)

[Introducción a los tipos de modelo en Microsoft Syntex](syntex-overview.md)
