---
title: Administrador de cumplimiento de Microsoft
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
description: El administrador de cumplimiento de Microsoft ayuda a las organizaciones a simplificar y automatizar las evaluaciones de riesgos, y sugiere acciones recomendadas para enfrentarse a los riesgos.
ms.openlocfilehash: b6ffd0156b295f03049d68ba99ad30c0ab8ae43b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204521"
---
# <a name="microsoft-compliance-manager"></a>Administrador de cumplimiento de Microsoft

**En este artículo:** Aprenda qué es el administrador de cumplimiento, cómo ayuda a simplificar el cumplimiento y reducir el riesgo, y sus componentes clave.

## <a name="whats-new-the-ga-release-of-compliance-manager"></a>Novedades: la versión de disponibilidad general del administrador de cumplimiento

Actualmente, el administrador de cumplimiento está disponible (GA) como una solución de administración de cumplimiento de un extremo a otro dentro del [centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center.md). Con esta versión, el administrador de cumplimiento completa la transición desde su ubicación anterior en el portal de confianza de servicios de Microsoft.

Lo que comenzó a medida que la versión preliminar pública de la puntuación de cumplimiento ha evolucionado a una herramienta centralizada con capacidades de administración de cumplimiento mejoradas y mayor facilidad de uso.  La versión de disponibilidad general ofrece una mayor colección de evaluaciones predefinidas para ayudarle a escalar las actividades de cumplimiento.

**Obtenga más información sobre la versión de disponibilidad general:**
- Nuestras [preguntas más frecuentes le](compliance-manager-faq.md) guiarán por la evolución con mayor detalle.
- Obtenga información sobre las mejoras de la característica GA en [esta entrada de blog](https://aka.ms/compliancemanager/GAblog).

Vea el vídeo a continuación para obtener información sobre cómo el administrador de cumplimiento puede ayudarle a simplificar la forma en que su organización administra el cumplimiento:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a>Qué es el administrador de cumplimiento

El [Administrador de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancemanager) es una característica del centro de cumplimiento de [Microsoft 365](microsoft-365-compliance-center.md) que le ayuda a administrar los requisitos de cumplimiento de su organización con mayor facilidad y comodidad. El administrador de cumplimiento puede ayudarle a lo largo de su viaje de cumplimiento, desde el inventario de los riesgos de protección de datos hasta la administración de las complejidades de la implementación de controles, mantenerse actualizado con las regulaciones y certificaciones, e informar a los auditores.

El administrador de cumplimiento ayuda a simplificar el cumplimiento y reducir el riesgo al ofrecer:

- Evaluaciones predefinidas para los estándares y normas regionales y de la industria, o evaluaciones personalizadas para satisfacer sus necesidades de cumplimiento exclusivas (las evaluaciones disponibles dependen del contrato de licencias; [más información](https://go.microsoft.com/fwlink/?linkid=2132371)).

- Capacidades de flujo de trabajo que le ayudarán a completar eficazmente las evaluaciones de riesgos mediante una única herramienta.

- Instrucciones detalladas paso a paso sobre acciones de mejora sugeridas para ayudarle a cumplir con las normas y regulaciones más relevantes para su organización. Para las acciones administradas por Microsoft, verá los detalles de implementación y los resultados de la auditoría.

- Una puntuación de cumplimiento basada en riesgos para ayudarle a comprender su postura de cumplimiento midiendo el progreso en completar acciones de mejora.

El panel del administrador de cumplimiento muestra la puntuación de cumplimiento actual, le ayuda a ver qué necesita atención y le guía a las acciones de mejora clave. A continuación se muestra un ejemplo de la apariencia que tendrá el panel del administrador de cumplimiento:

![Administrador de cumplimiento: panel](../media/compliance-manager-dashboard.png "Panel del administrador de cumplimiento")

## <a name="understanding-your-compliance-score"></a>Descripción de la puntuación de cumplimiento

El premio del administrador de cumplimiento le ofrece puntos para completar acciones de mejora realizadas para cumplir con una regla, un estándar o una directiva, y combina dichos puntos en una puntuación de cumplimiento general. Cada acción tiene un impacto diferente en su puntuación en función de los posibles riesgos. La puntuación de cumplimiento puede ayudar a priorizar en qué acción se debe centrar para mejorar su postura de cumplimiento general.

El administrador de cumplimiento le da una puntuación inicial basada en la línea base de protección de datos 365 de Microsoft. Esta línea base es un conjunto de controles que incluye normas y estándares clave para la protección de datos y el gobierno de datos general.

##### <a name="learn-more"></a>Obtén más información

[Comprenda cómo se calcula la puntuación de cumplimiento](compliance-score-calculation.md).

[Obtenga información sobre cómo trabajar con acciones de mejora](compliance-manager-improvement-actions.md).

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a>Elementos clave: controles, evaluaciones, plantillas, acciones de mejora

El administrador de cumplimiento usa varios elementos de datos para ayudarle a administrar las actividades de cumplimiento. Al usar el administrador de cumplimiento para asignar, probar y supervisar las actividades de cumplimiento, es útil tener un conocimiento básico de los elementos clave: controles, evaluaciones, plantillas y acciones de mejora.

### <a name="controls"></a>Controles

Un control es un requisito de una regla, un estándar o una directiva. Define cómo se evalúa y administra la configuración del sistema, el proceso de organización y las personas responsables de cumplir un requisito específico de una reglamentación, un estándar o una directiva.

El administrador de cumplimiento realiza un seguimiento de los siguientes tipos de controles:

1. **Controles administrados de Microsoft**: controles para los servicios en la nube de Microsoft, que Microsoft es responsable de implementar
2. **Sus controles**: a veces denominados controles administrados por el cliente, son controles implementados y administrados por su organización
3. **Controles compartidos**: son controles que tanto su organización como la responsabilidad de Microsoft comparten la responsabilidad de implementar

##### <a name="learn-more"></a>Obtén más información

[Supervise el progreso de los controles](compliance-manager-assessments.md#monitor-assessment-progress-and-controls).

[Obtenga información sobre cómo el administrador de cumplimiento evalúa de forma continua los controles](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).

### <a name="assessments"></a>Evaluaciones

Una evaluación es la agrupación de los controles de una normativa, estándar o Directiva específica. La realización de las acciones de una evaluación le ayudará a cumplir los requisitos de una norma, normativa o ley. Por ejemplo, puede tener una evaluación que, al completar todas las acciones de la misma, le ayude a poner la configuración de Microsoft 365 en línea con los requisitos ISO 27001.

Las evaluaciones tienen varios componentes:

- **Servicios en el ámbito**: el conjunto específico de servicios de Microsoft que se aplican a la evaluación
- **Controles administrados de Microsoft**: controles para los servicios en la nube de Microsoft, que Microsoft implementa en su nombre
- **Sus controles**: a veces denominados controles administrados por el cliente, son controles implementados y administrados por su organización
- **Controles compartidos**: son controles que tanto su organización como la responsabilidad de Microsoft comparten la responsabilidad de implementar
- **Puntuación**de la evaluación: muestra el progreso en la obtención de los puntos totales posibles de las acciones de la evaluación administradas por la organización y por Microsoft.

Al crear evaluaciones, deberá asignarlas a un grupo. Puede configurar los grupos de la forma más lógica para su organización. Por ejemplo, puede agrupar las evaluaciones por año de auditoría, región, solución, Teams dentro de su organización o de algún otro modo. Una vez creados los grupos, puede [filtrar el panel del administrador de cumplimiento](compliance-manager-setup.md#filtering-your-dashboard-view) para ver la puntuación de uno o varios grupos.

##### <a name="learn-more"></a>Obtén más información

[Cree y administre evaluaciones en el administrador de cumplimiento](compliance-manager-assessments.md).

### <a name="templates"></a>Plantillas

El administrador de cumplimiento proporciona plantillas para ayudarle a crear rápidamente evaluaciones. Puede modificar estas plantillas para crear una evaluación optimizada para sus necesidades. También puede crear una evaluación personalizada creando una plantilla con sus propios controles y acciones. Por ejemplo, puede que desee que una plantilla abarque un control de proceso empresarial interno o un estándar de protección de datos regional que no esté cubierto por una de las 150 plantillas de evaluación predefinidas.

##### <a name="learn-more"></a>Obtén más información

[Ver la lista de plantillas de evaluación que proporciona el administrador de cumplimiento](compliance-manager-templates-list.md).

[Obtenga instrucciones detalladas para crear y modificar plantillas para evaluaciones](compliance-manager-templates.md).

### <a name="improvement-actions"></a>Acciones de mejora

Las acciones de mejora ayudan a centralizar las actividades de cumplimiento. Cada acción de mejora proporciona una orientación recomendada que está destinada a ayudarle a alinearse con las normas y los estándares de protección de datos. Las acciones de mejora se pueden asignar a los usuarios de su organización para realizar tareas de implementación y pruebas. También puede almacenar la documentación, las notas y las actualizaciones de estado de registro dentro de la acción de mejora.

##### <a name="learn-more"></a>Obtén más información

[Use acciones de mejora para administrar el flujo de trabajo de cumplimiento](compliance-manager-improvement-actions.md).

[Obtenga información sobre cómo afectan las acciones a la puntuación de cumplimiento](compliance-score-calculation.md#action-types-and-points).

## <a name="supported-languages"></a>Idiomas admitidos

El administrador de cumplimiento está disponible en los siguientes idiomas:

- Inglés
- Bahasa indonesio
- Malayo Bahasa
- Chino (simplificado)
- Chino (tradicional)
- Checo
- Danés
- Neerlandés
- Finés
- Francés
- Alemán
- Hebreo
- Húngaro
- Italiano
- Japonés
- Coreano
- Noruego
- Polaco
- Portugués (Brasil)
- Ruso
- Español
- Sueco
- Tailandés
- Turco

## <a name="next-steps-set-up-and-customize"></a>Pasos siguientes: configurar y personalizar

Obtenga información sobre cómo iniciar sesión, asignar permisos y roles, configurar opciones y personalizar la vista del panel en Introducción al [Administrador de cumplimiento](compliance-manager-setup.md).

A continuación, empiece a personalizar el administrador de cumplimiento para que le ayude a cumplir los estándares de la industria que más importan a su organización mediante la [configuración de evaluaciones](compliance-manager-assessments.md).