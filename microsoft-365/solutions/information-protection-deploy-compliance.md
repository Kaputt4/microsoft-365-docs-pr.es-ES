---
title: Usar la puntuación de cumplimiento y el administrador de cumplimiento para administrar acciones de mejora
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 07/13/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: Obtenga información sobre cómo usar la puntuación de cumplimiento y el administrador de cumplimiento para mejorar el nivel de protección de los datos personales.
ms.openlocfilehash: 5b1d465ad03a6aad5370f76b2cdde0657efd2f79
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521058"
---
# <a name="use-compliance-score-and-compliance-manager-to-manage-improvement-actions"></a>Usar la puntuación de cumplimiento y el administrador de cumplimiento para administrar acciones de mejora

La puntuación de cumplimiento de Microsoft y el administrador de cumplimiento se pueden usar de forma conjunta para administrar mejoras relacionadas con las regulaciones de privacidad de datos, como el Reglamento de protección general de datos de la Unión Europea [(RGPD)](../compliance/gdpr.md), la [protección del consumidor de California Act CCPA)](../compliance/ccpa-faq.md), HIPAA-up (Act de Sanidad de Estados Unidos) y la ley de protección de datos de Brasil (LGPD). 

En este artículo se proporcionan instrucciones sobre el uso de estas herramientas para fines de privacidad de datos.

![Puntuación de cumplimiento y administrador de cumplimiento para administrar las acciones de mejora](../media/information-protection-deploy-compliance/information-protection-deploy-compliance-grid.png)

>[!Note]
>Las acciones del cliente que se proporcionan en el administrador de cumplimiento son recomendaciones. Debe evaluar la eficacia de estas recomendaciones en sus entornos de reglamentación antes de la implementación. Las recomendaciones del administrador de cumplimiento no deben interpretarse como una garantía de cumplimiento.
>

## <a name="planned-updates-for-compliance-score-and-compliance-manager"></a>Actualizaciones planificadas para la puntuación de cumplimiento y el administrador de cumplimiento

La [puntuación de cumplimiento](../compliance/compliance-score.md) (actualmente en versión preliminar) requiere que se agreguen las evaluaciones de destino de un Reglamento (como RGPD) del administrador de [cumplimiento](../compliance/compliance-manager-overview.md). En una versión futura, gran parte de la funcionalidad del administrador de cumplimiento se combinará con una experiencia de puntuación de cumplimiento unificada, lo que reduce la necesidad de tener varias herramientas.

Estas son las herramientas para su suscripción, que requieren que inicie sesión:

- [Puntuación de cumplimiento en el centro de administración de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancescore)
- [Administrador de cumplimiento en el portal de confianza de servicios de Microsoft](https://servicetrust.microsoft.com/ComplianceManager/V3)

## <a name="getting-started-with-compliance-manager"></a>Introducción al administrador de cumplimiento 

El [Administrador de cumplimiento](../compliance/working-with-compliance-manager.md) (actualmente en versión preliminar) es una herramienta gratuita de evaluación de riesgos basada en flujos de trabajo en el portal de confianza de servicios de Microsoft para administrar las actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft. Como parte de su suscripción a Microsoft 365 o Azure Active Directory (Azure AD), el administrador de cumplimiento le ayuda a administrar el cumplimiento de normativas en el modelo de responsabilidad compartida para los servicios en la nube de Microsoft.

Aunque puede ver la puntuación de cumplimiento general y realizar varias funciones en la página de **puntuación de cumplimiento** del centro de cumplimiento, debe usar el administrador de cumplimiento a través del portal de confianza de servicios para configurar primero las evaluaciones para las regulaciones de privacidad de datos. Los datos de estas evaluaciones se mostrarán en la puntuación de cumplimiento para ver y filtrar aún más. 

Mediante el uso de la interfaz del administrador de cumplimiento, puede seleccionar una o varias plantillas de reglamentaciones relacionadas con la privacidad de datos y agruparlas para evaluar y realizar un seguimiento de las acciones de mejora necesarias en todo el conjunto. También puede ver información acerca de los controles a los que se aplica cada regla específica del servicio de destino, separados por los controles administrados por el cliente y por Microsoft.

Las evaluaciones y el estado de la mejora que se seleccionen aquí también aparecen en la puntuación de cumplimiento en el centro de cumplimiento de Microsoft, que enfatiza la importancia de la configuración inicial en el administrador de cumplimiento. Estas relaciones se muestran en esta figura.
 
![Relaciones de la puntuación de cumplimiento en el centro de cumplimiento de Microsoft](../media/information-protection-deploy-compliance/information-protection-deploy-compliance-ui.png)

Estos son los pasos clave para ayudarle a empezar.

### <a name="1-assessment-templates"></a>1. plantillas de evaluación

Desde el administrador de cumplimiento, el primer paso consiste en agregar evaluaciones específicas de las normas de privacidad de datos de interés e incluirlas en un grupo "regulaciones de privacidad de datos" definidas.

Los [grupos](../compliance/working-with-compliance-manager.md#groups) son contenedores que permiten organizar las evaluaciones y compartir información común y tareas de flujo de trabajo entre evaluaciones que tienen los mismos controles administrados por el cliente u otros relacionados. Cuando dos evaluaciones distintas en el mismo grupo comparten el control administrado por el cliente, la finalización de los detalles de implementación, las pruebas y el estado del control se sincronizan automáticamente con el mismo control en cualquier otra evaluación del grupo. Esto unifica los elementos de acción asignados para cada control en el grupo y reduce el trabajo de duplicación. 

También puede optar por usar grupos para organizar. Evaluaciones por año, área, estándar de cumplimiento u otros grupos para ayudar a organizar el trabajo de cumplimiento.


### <a name="2-action-items"></a>2. elementos de acción

Una vez agregadas las evaluaciones, puede ver los elementos de acción específicos de cada grupo o regla individual:

- **Lista de acciones mejoradas.** Navegue a la lista elementos de acción y vea las acciones de mejora asociadas a las regulaciones incluidas en el grupo. Muchas acciones abarcan regulaciones para que un solo elemento de lista pueda representar varias regulaciones. 
 
- **Filtrado de acciones de mejora.** Para muchas normativas de privacidad de datos y grupos de regulaciones, la lista de acciones de mejora puede ser bastante grande, así que considere la posibilidad de filtrar la lista mediante el desplegable de filtros. Por ejemplo, si selecciona "controles técnicos", la lista se reducirá a solo aquellas que tienen una implementación técnica en la organización, ya que muchas de las acciones están relacionadas con las operaciones administrativas en diversos aspectos de la empresa que también se documentan en el administrador de cumplimiento. En este artículo, se centraremos en los controles técnicos, por lo que se recomienda este método de filtrado.
 
- **Información adicional y revisión.** Para cada acción, puede hacer clic en el vínculo para **leer más**, que le indicará más sobre la actividad recomendada, o la **revisión**, que abre un formulario que le permite hacer lo siguiente:
 
   - Asignar la acción a una persona de su organización para que la administre
   - Administrar documentos relacionados con la solución de la acción
   - Especificar el estado del elemento
   - Especificación de fechas de implementación y prueba
   - Registrar información adicional, notas de implementación y notas del plan de pruebas para la acción de asunto
  
- **Elementos no aplicables como fuera de ámbito.** Es posible que algunas acciones de mejora incluidas en la lista elementos de acción no se apliquen a la implementación planeada. Puede especificar que están fuera de ámbito en el administrador de cumplimiento y quitar la acción y su evidencia del cálculo del valor de puntuación de cumplimiento. 

Por ejemplo, si su organización ha decidido usar la clave administrada de Microsoft ", una recomendación para usar la clave de cliente no es aplicable a su implementación de. En este caso, su organización la marcaría como **no en el ámbito** en las **acciones de control** de la plantilla normativa aplicable.
 
### <a name="3-controls-info"></a>3. información de controles

Para obtener una vista específica de la evaluación, vea la [información de controles](../compliance/compliance-manager-overview.md#controls) para cada grupo de evaluación. Esto proporciona una vista específica de la evaluación, que es la diferencia de la lista elementos de acción, que proporciona una vista específica del control técnico.
 
![Relaciones de evaluación para controlar los elementos](../media/information-protection-deploy-compliance/information-protection-deploy-compliance-control.png)

Navegue a la lista de **información de controles** y vea la lista de los servicios de ámbito de la regla en cuestión. 
 
Las agrupaciones de controles específicas de la reglamentación enumeran las acciones que proporciona el área de control para cada área de servicio. Para cada conjunto de acciones, el administrador de cumplimiento proporciona más información sobre la acción y puede sugerir o proporcionar opciones de revisión para ayudar a la organización a elegir un enfoque de control.
 
Tenga en cuenta que esta interfaz proporciona la capacidad de ver los detalles específicos de la acción técnica, junto con el estado de las acciones relacionadas con el control, y el contexto suplementario sobre las regulaciones con las que está relacionada la acción.

### <a name="4-template-download"></a>4. descarga de plantillas

Para los que estén más familiarizados con el análisis normativo basado en hojas de cálculo, otro enfoque es descargar la plantilla para cada evaluación respectiva mediante la descripción de las plantillas. Las plantillas descargadas enumeran la información de control normativo y técnico para cada plantilla y pueden ser más sencillas para que determinados roles puedan navegar o filtrar y generar vistas específicas de la empresa.
 
También puede Agregar una nueva plantilla personalizada para la organización basada en una plantilla existente, mediante **Agregar plantilla**. Para ello, es necesario descargar una plantilla de elección (como HIPAA/alta tecnología)), modificarla para sus fines y volver a cargarla en la herramienta del administrador de cumplimiento, donde ahora se impulsarán evaluaciones y puntuación similares a otras plantillas y evaluaciones como parte del administrador de cumplimiento general y el conjunto de herramientas de puntuación de cumplimiento.
 
>[!Tip]
>Si se trata de un gran número de reglamentos o de acciones de mejora superpuestas, considere la posibilidad de descargar cada plantilla respectiva y combinar los conjuntos de datos, quitar las acciones de mejora o los tipos de control que no se aplican a la organización y volver a cargar. Esto puede ser más fácil que navegar por cada sección de información de control y marcar cada una como fuera del ámbito.
>

## <a name="compliance-score"></a>Puntuación de cumplimiento 

Una vez que las especificaciones de evaluación y revisión se llevan a cabo en el administrador de cumplimiento, ahora puede ir a la herramienta de [puntuación de cumplimiento](../compliance/compliance-score.md) y revisar la puntuación y el segmento, y clasificar los datos con más detalle, incluido el área de control.

La herramienta de puntuación de cumplimiento en el centro de administración de cumplimiento de Microsoft 365 ofrece varios métodos para revisar y filtrar datos de cumplimiento obtenidos del administrador de cumplimiento y varios servicios de Microsoft 365. Esta herramienta se actualiza automáticamente cuando se implementan varias opciones de configuración y comparte señales con la puntuación segura de Microsoft para que se muestren muchas acciones de mejora en ambos resultados. 
 
La puntuación de cumplimiento proporciona:

- Un resultado recopilado, desglosado por Microsoft y por los controles administrados por el cliente
- Un resumen de las acciones de mejora y el estado de finalización
- Una lista de soluciones de Microsoft 365 que afectan su puntuación

### <a name="how-the-compliance-score-gets-calculated"></a>Cómo se calcula la puntuación de cumplimiento

En Resumen, la puntuación se calcula en función de una combinación de implementaciones de controles administrados por el cliente y Microsoft, tal como se explica más detalladamente en el [artículo cálculo](../compliance/compliance-score-methodology.md)de la puntuación de cumplimiento de Microsoft.

A los controles se les asigna un valor de puntuación en función de si son obligatorios o discrecionales, y si son preventivos, detectives o correctivos. Estos representan colectivamente el riesgo de no implementarlo en relación con otros controles.

Como se muestra en el artículo cálculo de la puntuación de cumplimiento de Microsoft, los controles preventivos obtienen una puntuación mayor que el detective y los correctores, y los controles obligatorios obtienen una puntuación mayor que los discrecionales.
 
Tenga en cuenta que la interfaz de usuario del administrador de puntuación de cumplimiento no enumera estos parámetros, ni proporciona la capacidad de filtrarlos por ellos. Sin embargo, si descarga la plantilla asociada desde la herramienta Administrador de cumplimiento, el conjunto de datos resultante enumera estos parámetros para la mayoría de las regulaciones.

Para los controles técnicos, la puntuación de cumplimiento actualizará automáticamente el resultado de la acción de mejora una vez que se activa la característica relacionada. Otras acciones de control no técnicas, como &mdash; las operaciones operativas o relacionadas con la documentación, &mdash; deben registrarse manualmente en la herramienta del administrador de cumplimiento en el portal de confianza de servicios. 

También puede implementar ciertas acciones de mejora para otros fines &mdash; por ejemplo, mediante el uso de etiquetas de retención por motivos que no sean el cumplimiento normativo de la privacidad de los datos, por lo que recibirá &mdash; crédito por usar dicha característica incluso si se usa para otros fines y no como parte de una acción de cumplimiento deliberada.

La puntuación de cumplimiento debe considerarse una medida relativa para realizar el seguimiento de la mejora en una escala amplia. No debe obtener una puntuación perfecta. 

### <a name="additional-guidance"></a>Instrucciones adicionales

Estas son algunas sugerencias importantes para el uso de la puntuación de cumplimiento y el administrador de cumplimiento para lograr el cumplimiento normativo de privacidad de datos:

- Cada normativa de privacidad de los datos tiene una combinación de controles técnicos, especificaciones de documentación y requisitos de funcionamiento, proceso e informes. Todas estas se muestran en las acciones de mejora. 

- Este artículo se centra en un subconjunto de los controles técnicos especificados para la privacidad de los datos en el administrador de cumplimiento y la puntuación de cumplimiento. Consulte la herramienta Administrador de cumplimiento y la [documentación](../compliance/compliance-score.md) para obtener más información sobre los controles administrativos no técnicos.

- Para centrarse en la vista de las acciones de mejora en su área de interés, puede filtrar por tipo de acción en la ficha **soluciones** del administrador de puntuación de cumplimiento.

- La importancia relativa y la prioridad de las acciones de mejora que se identifican en la puntuación de cumplimiento deben considerarse como parte de una revisión de riesgos más amplia, junto con los riesgos de privacidad de datos que ha determinado que su organización debe administrar. 

- Si es una organización global y agrega varias plantillas de normativa de privacidad de datos en el administrador de cumplimiento como evaluaciones, la puntuación de cumplimiento combinará cada una de las acciones que se apliquen en una lista de campos para cada acción de mejora.
 
- Incluso con la agregación de acciones de mejora a través de varios requisitos normativos, si se seleccionan las plantillas de evaluación del Reglamento para RGPD, LGPD, CCPA y HIPAA-alta tecnología, por ejemplo, las acciones de mejora de 400 se enumerarán en puntuación de cumplimiento. Para abordar mejor esta larga lista, use el filtro acción de mejora para reducir el conjunto de resultados a una lista más fácil de administrar.

- El filtro categorías proporciona un medio para filtrar acciones de mejora mediante la Agrupación lógica, que los artículos Track, impiden, Protect, retain e Investigate en esta solución general se alinean con. 

- Es posible que algunos de los controles enumerados en las acciones de mejora se consideren directamente ligados a un artículo reglamentario específico, mientras que otros controles pueden asociarse de forma más indirecta con el espíritu de un Reglamento y son muchas veces cosas que debe tener en cuenta.

