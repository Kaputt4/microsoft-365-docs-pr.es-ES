---
title: Puntuación de cumplimiento de Microsoft (versión preliminar)
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: La puntuación de cumplimiento de Microsoft (versión preliminar) ayuda a las organizaciones a simplificar y automatizar las evaluaciones de riesgos, y sugiere acciones recomendadas para enfrentarse a los riesgos.
ms.openlocfilehash: 0cb8bd0b5aa39be2a9a6e706afa21bb7dc53eadb
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016143"
---
# <a name="microsoft-compliance-score-preview"></a>Puntuación de cumplimiento de Microsoft (versión preliminar)

**En este artículo:** Obtenga información sobre qué es la puntuación de cumplimiento, cómo ayuda a simplificar la forma de administrar el cumplimiento y cómo configurarlo para su organización.

Novedades **:** La versión de junio de 2020 incluye nuevas funciones para crear y administrar evaluaciones y para ver los controles dentro de la puntuación de cumplimiento. Visite las [notas](compliance-score-release-notes.md) de la versión de calificación de cumplimiento para ver las novedades de la versión preliminar pública de la puntuación de cumplimiento.

## <a name="what-is-compliance-score"></a>¿Qué es la puntuación de cumplimiento?

La [puntuación de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancescore) es una característica de vista previa del centro de cumplimiento de [Microsoft 365](microsoft-365-compliance-center.md) para ayudarle a comprender la postura de cumplimiento de la organización. Calcula una puntuación basada en riesgos que mide su progreso en la realización de acciones que ayudan a reducir los riesgos en torno a la protección de datos y los estándares normativos.

Puede usar la puntuación de cumplimiento como una herramienta para realizar un seguimiento de todas las evaluaciones de riesgos. Proporciona funcionalidades de flujo de trabajo para ayudarle a completar eficazmente las evaluaciones de riesgos mediante una herramienta común.

Los usuarios del [Administrador de cumplimiento](compliance-manager-overview.md) notarán que la puntuación de cumplimiento es ahora una característica independiente con un diseño más fácil y sencillo para ayudar a las organizaciones a administrar más fácilmente el cumplimiento.

La página de puntuación de cumplimiento principal es su panel personalizado. Muestra su puntuación actual, le ayuda a ver qué necesita atención y le guía a acciones para mejorar su calificación. El panel de calificaciones de cumplimiento tendrá el siguiente aspecto:

![Puntuación de cumplimiento: panel](../media/compliance-score-dashboard.png "Panel de calificaciones de cumplimiento")

### <a name="simplified-compliance-management"></a>Administración de cumplimiento simplificada

La puntuación de cumplimiento ayuda a simplificar la administración del cumplimiento proporcionando:

- **Evaluaciones continuas**: explora automáticamente los entornos Microsoft 365 para detectar y supervisar la eficacia de los controles de protección de datos en el sistema.
- **Acciones recomendadas**: proporciona recomendaciones e instrucciones paso a paso sobre cómo implementar controles para maximizar la puntuación.
-  La **asignación de controles integradas**: le ayuda a mantenerse al día con el entorno de cumplimiento en constante evolución al proporcionarle un marco de control común integrado

> [!IMPORTANT]
> Las recomendaciones de la puntuación de cumplimiento y del Administrador de cumplimiento no deben interpretarse como una garantía de cumplimiento. Depende de usted evaluar y validar la eficacia de los controles de cliente según su entorno de reglamentación. Estos servicios están actualmente en versión preliminar y están sujetos a los términos y condiciones de los [términos de servicios en línea](https://go.microsoft.com/fwlink/?linkid=2108910). Vea también la [Guía de licencias de Microsoft 365 por seguridad y cumplimiento normativo](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="relationship-to-compliance-manager"></a>Relación con el administrador de cumplimiento

Piense en la puntuación de cumplimiento como una experiencia simplificada del administrador de cumplimiento. Aunque existen dos herramientas distintas pero integradas, la puntuación de cumplimiento hace que sea más fácil supervisar el nivel de cumplimiento general y tomar medidas para mejorarla.

La puntuación de cumplimiento comparte el mismo back-end con el administrador de cumplimiento. Todo lo que haga en una herramienta se mostrará en la otra herramienta.

Algunas funciones para la administración de la evaluación y la plantilla permanecen en el administrador de cumplimiento durante la versión preliminar pública. Se recomienda comenzar todas las actividades de administración de cumplimiento en puntuación de cumplimiento. Cuando llegue a funciones administradas por el administrador de cumplimiento, le guiaremos en este documento.

#### <a name="learn-more"></a>Más información

[Comprender la relación entre la puntuación de cumplimiento y el administrador de cumplimiento](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).

## <a name="understanding-your-score"></a>Descripción de la puntuación

Puntuación de cumplimiento premios le hace referencia a completar las acciones realizadas para cumplir con una regla, un estándar o una directiva. Cada acción tiene un impacto diferente en su puntuación en función de los posibles riesgos. Su puntuación puede ayudar a priorizar la acción que se debe centrar para mejorar su postura de cumplimiento general.

La puntuación de cumplimiento proporciona una puntuación inicial basada en la línea base de protección de datos 365 de Microsoft.  Esta línea base es un conjunto de controles que incluye normas y estándares clave para la protección de datos y el gobierno de datos general. Esta base dibuja los elementos principalmente desde NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Normalization), así como de FedRAMP (programa federal de administración de riesgos y autorización) y RGPD (norma general de protección de datos de la Unión Europea).

La evaluación de línea base de protección de datos se usa para calcular el resultado inicial antes de configurar otras evaluaciones. En su primera visita, la puntuación de cumplimiento ya está recopilando las señales de las soluciones de Microsoft 365. Ver? a simple vista sobre el rendimiento de su organización con respecto a los estándares y regulaciones clave de protección de datos y ver las acciones de mejora sugeridas que deben tomarse.

Debido a que cada organización tiene necesidades específicas, la puntuación de cumplimiento depende de que configure y administre sus propias evaluaciones para mitigar mejor los riesgos. Por ejemplo, si su organización pertenece a la industria de servicios financieros, es posible que quiera agregar la evaluación de FFIEC. Si su organización pertenece a la industria de la salud, puede Agregar la evaluación de HIPAA/alta tecnología.

#### <a name="learn-more"></a>Más información

[Comprenda cómo se calcula y se supervisa continuamente la puntuación de cumplimiento](compliance-score-methodology.md).

[Cree y administre evaluaciones en la puntuación de cumplimiento](compliance-score-assessments.md).

## <a name="key-components-controls-assessments-templates-improvement-actions"></a>Componentes clave: controles, evaluaciones, plantillas, acciones de mejora

La puntuación de cumplimiento usa varios componentes para ayudarle a administrar las actividades de cumplimiento. A medida que se usa la puntuación de cumplimiento para asignar, probar y supervisar las actividades de cumplimiento, resulta útil tener un conocimiento básico de los componentes clave: controles, evaluaciones, plantillas y acciones de mejora.

### <a name="controls"></a>Controles

Un control es un requisito de una regla, un estándar o una directiva. Define cómo se evalúa y administra la configuración del sistema, el proceso de organización y las personas responsables de cumplir un requisito específico de una reglamentación, un estándar o una directiva.

La puntuación de cumplimiento hace un seguimiento de dos tipos de controles:

1. **Controles administrados de Microsoft**: controles para los servicios en la nube de Microsoft, que Microsoft es responsable de implementar
2. **Los controles**, en ocasiones denominados controles de cliente, son controles implementados y administrados por la organización.

#### <a name="learn-more"></a>Más información

[Supervise el progreso de los controles](compliance-score-assessments.md#monitor-assessment-progress-and-controls).

### <a name="assessments"></a>Evaluaciones

Una evaluación es la agrupación de los controles de una normativa, estándar o Directiva específica. La realización de las acciones de una evaluación le ayudará a cumplir los requisitos de una norma, normativa o ley. Por ejemplo, puede tener una evaluación que, al completar todas las acciones de la misma, lleva la configuración de Microsoft 365 en línea con los requisitos ISO 27001.

Las evaluaciones tienen varios componentes:

- **Servicios en el ámbito**: el conjunto específico de servicios de Microsoft que se aplican a la evaluación
- **Controles administrados por Microsoft**: controles que implementa y prueba Microsoft
- **Los controles**: controles que administra
- **Puntuación**de la evaluación: porcentaje de los puntos logrados al completar las acciones de mejora dentro de dicha evaluación.

Al crear evaluaciones, deberá asignarlas a un **Grupo**. Puede configurar los grupos de la forma más lógica para su organización. Por ejemplo, puede agrupar las evaluaciones por año, el estándar de cumplimiento, el servicio, los equipos de la organización o algún otro modo. Una vez que haya creado los grupos, puede [filtrar el panel de puntuaciones de cumplimiento](compliance-score-setup.md#filtering-your-dashboard-view) para ver la puntuación de uno o varios grupos.

#### <a name="learn-more"></a>Más información

[Cree y administre evaluaciones en la puntuación de cumplimiento](compliance-score-assessments.md).

### <a name="templates"></a>Plantillas

Puntuación de cumplimiento proporciona plantillas que están listas para crear rápidamente evaluaciones. Puede modificar estas plantillas para crear una evaluación optimizada para sus necesidades. También puede crear una evaluación personalizada mediante el desarrollo de su propia plantilla con sus propios controles y acciones. Por ejemplo, puede que desee que una plantilla abarque un control de proceso empresarial interno o un estándar de protección de datos regional que no esté cubierto por una de nuestras plantillas.

La creación de sus propias plantillas le permite realizar un seguimiento no solo de las evaluaciones de la nube de Microsoft, sino también de otras evaluaciones de riesgos en el ámbito de su organización.

#### <a name="learn-more"></a>Más información

[Permite ver las plantillas disponibles en puntuación de cumplimiento para crear evaluaciones](compliance-score-templates.md).

[Obtenga instrucciones detalladas para crear y modificar el administrador de cumplimiento de plantillas](working-with-compliance-manager.md#templates).

### <a name="improvement-actions"></a>Acciones de mejora

Las acciones de mejora centralizan las actividades de cumplimiento. Cada acción de mejora proporciona una guía de implementación detallada para ayudarle a alinearse con las normas y estándares de protección de datos. Se pueden asignar acciones a los usuarios de su organización para realizar tareas de implementación y pruebas. También puede almacenar la documentación, las notas y las actualizaciones de estado de registro dentro de la acción de mejora.

#### <a name="learn-more"></a>Más información

[Use acciones de mejora para administrar el flujo de trabajo de cumplimiento](compliance-score-improvement-actions.md).

## <a name="next-steps-set-up-and-customize"></a>Pasos siguientes: configurar y personalizar

Obtenga información sobre cómo iniciar sesión, establecer permisos y roles, configurar actualizaciones de calificación segura y personalizar la vista del panel en la configuración de la [puntuación de cumplimiento](compliance-score-setup.md).

A continuación, empiece a personalizar la puntuación de cumplimiento para su organización mediante la [configuración de evaluaciones](compliance-score-assessments.md).