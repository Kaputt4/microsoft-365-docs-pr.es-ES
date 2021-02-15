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
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: El Administrador de cumplimiento de Microsoft ayuda a las organizaciones a simplificar y automatizar las evaluaciones de riesgos, y sugiere acciones recomendadas para ayudar a abordar los riesgos.
ms.openlocfilehash: 7bff6a2a7a150a08b98fe7a92cd71d266df9fda7
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376551"
---
# <a name="microsoft-compliance-manager"></a>Administrador de cumplimiento de Microsoft

**En este artículo:** Obtenga información sobre qué es el Administrador de cumplimiento, cómo ayuda a simplificar el cumplimiento y reducir los riesgos y sus componentes clave.

## <a name="whats-new-the-ga-release-of-compliance-manager"></a>Novedades: la versión ga del Administrador de cumplimiento

El Administrador de cumplimiento ahora está disponible generalmente (GA) como una solución de administración de cumplimiento integral dentro del Centro de cumplimiento [de Microsoft 365.](microsoft-365-compliance-center.md) Con esta versión, el Administrador de cumplimiento completa la transición desde su ubicación anterior en el Portal de confianza de servicios de Microsoft. El Administrador de cumplimiento también está ahora disponible para los clientes de us Government Community (GCC) Moderate y GCC High.

Lo que empezó como vista previa pública de la puntuación de cumplimiento ha evolucionado hasta convertirse en una herramienta centralizada con capacidades mejoradas de administración de cumplimiento y mayor facilidad de uso.  La versión de ga ofrece una colección más grande de evaluaciones predefinidas para ayudarle a escalar las actividades de cumplimiento.

**Obtenga más información sobre la versión ga:**
- Nuestras [preguntas más frecuentes le](compliance-manager-faq.md) guían a través de la evolución con más detalle.
- Lea las mejoras de características de GA en [esta entrada de blog.](https://aka.ms/compliancemanager/GAblog)

Vea el vídeo siguiente para obtener información sobre cómo el Administrador de cumplimiento puede ayudar a simplificar la forma en que su organización administra el cumplimiento:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a>¿Qué es el Administrador de cumplimiento?

[El Administrador de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancemanager) es una característica del Centro de cumplimiento de Microsoft [365](microsoft-365-compliance-center.md) que le ayuda a administrar los requisitos de cumplimiento de su organización con mayor facilidad y comodidad. El Administrador de cumplimiento puede ayudarle a lo largo de su recorrido de cumplimiento, desde realizar un inventario de los riesgos de protección de datos hasta administrar las complejidades de la implementación de controles, mantenerse al día con las normativas y certificaciones, e informar a los auditores.

El Administrador de cumplimiento ayuda a simplificar el cumplimiento y reducir los riesgos proporcionando:

- Evaluaciones predefinidas para estándares y normativas regionales y del sector comunes, o evaluaciones personalizadas para satisfacer sus necesidades de cumplimiento únicas (las evaluaciones disponibles dependen de su contrato de licencia; [más información](https://go.microsoft.com/fwlink/?linkid=2132371)).

- Capacidades de flujo de trabajo para ayudarle a completar eficazmente las evaluaciones de riesgos a través de una sola herramienta.

- Instrucciones detalladas paso a paso sobre las acciones de mejora sugeridas para ayudarle a cumplir con los estándares y normativas más relevantes para su organización. Para las acciones administradas por Microsoft, verá los detalles de implementación y los resultados de auditoría.

- Una puntuación de cumplimiento basada en riesgos que le ayudará a comprender su posición de cumplimiento midiendo su progreso en la realización de acciones de mejora.

El panel del Administrador de cumplimiento muestra la puntuación de cumplimiento actual, le ayuda a ver lo que necesita atención y le guía a las principales acciones de mejora. A continuación se muestra un ejemplo del aspecto que tendrá el panel del Administrador de cumplimiento:

![Administrador de cumplimiento: panel](../media/compliance-manager-dashboard.png "Panel del Administrador de cumplimiento")

## <a name="understanding-your-compliance-score"></a>Descripción de la puntuación de cumplimiento

El Administrador de cumplimiento le otorga puntos para completar las acciones de mejora tomadas para cumplir con un reglamento, estándar o directiva, y combina esos puntos en una puntuación de cumplimiento general. Cada acción tiene un impacto diferente en la puntuación en función de los posibles riesgos implicados. La puntuación de cumplimiento puede ayudar a dar prioridad a la acción que debe centrarse para mejorar la posición general de cumplimiento.

El Administrador de cumplimiento le proporciona una puntuación inicial basada en la línea base de protección de datos de Microsoft 365. Esta línea base es un conjunto de controles que incluye normas y estándares clave para la protección de datos y el gobierno general de datos.

##### <a name="learn-more"></a>Más información

[Comprenda cómo se calcula la puntuación de cumplimiento.](compliance-score-calculation.md)

[Obtenga información sobre cómo trabajar con acciones de mejora.](compliance-manager-improvement-actions.md)

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a>Elementos clave: controles, evaluaciones, plantillas, acciones de mejora

El Administrador de cumplimiento usa varios elementos de datos para ayudarle a administrar las actividades de cumplimiento. Al usar el Administrador de cumplimiento para asignar, probar y supervisar actividades de cumplimiento, resulta útil tener un conocimiento básico de los elementos clave: controles, evaluaciones, plantillas y acciones de mejora.

### <a name="controls"></a>Controles

Un control es un requisito de una regulación, estándar o directiva. Define cómo evaluar y administrar la configuración del sistema, el proceso organizativo y las personas responsables de cumplir un requisito específico de un reglamento, estándar o directiva.

El Administrador de cumplimiento realiza un seguimiento de los siguientes tipos de controles:

1. **Controles administrados por Microsoft:** controles para los servicios en la nube de Microsoft, que Microsoft es responsable de implementar
2. **Los controles:** a veces denominados controles administrados por el cliente, estos son controles implementados y administrados por la organización
3. **Controles compartidos:** estos son controles que su organización y Microsoft comparten como responsables de la implementación

##### <a name="learn-more"></a>Más información

[Supervisar el progreso de los controles](compliance-manager-assessments.md#monitor-assessment-progress-and-controls).

[Obtenga información sobre cómo el Administrador de cumplimiento evalúa continuamente los controles.](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)

### <a name="assessments"></a>Evaluaciones

Una evaluación es la agrupación de controles de una regulación, estándar o directiva específica. Completar las acciones dentro de una evaluación le ayudará a cumplir los requisitos de una norma, reglamento o ley. Por ejemplo, puede que tenga una evaluación que, cuando complete todas las acciones dentro de ella, ayude a que la configuración de Microsoft 365 se alinee con los requisitos iso 27001.

Las evaluaciones tienen varios componentes:

- **Servicios dentro del ámbito:** el conjunto específico de servicios microsoft aplicables a la evaluación
- **Controles administrados por Microsoft:** controles para los servicios en la nube de Microsoft, que Microsoft implementa en su nombre
- **Los controles:** a veces denominados controles administrados por el cliente, son controles implementados y administrados por la organización
- **Controles compartidos:** estos son controles que su organización y Microsoft comparten como responsables de la implementación
- **Puntuación de** evaluación: muestra su progreso en la obtención de puntos posibles totales de las acciones dentro de la evaluación administradas por su organización y por Microsoft

Al crear evaluaciones, las asignarás a un grupo. Puede configurar grupos de la forma que sea más lógica para su organización. Por ejemplo, puede agrupar evaluaciones por año de auditoría, región, solución, equipos dentro de su organización u otra forma. Una vez creados los grupos, puede filtrar el panel del [Administrador](compliance-manager-setup.md#filtering-your-dashboard-view) de cumplimiento para ver la puntuación por uno o más grupos.

##### <a name="learn-more"></a>Más información

[Crear y administrar evaluaciones en el Administrador de cumplimiento.](compliance-manager-assessments.md)

### <a name="templates"></a>Plantillas

El Administrador de cumplimiento proporciona plantillas para ayudarle a crear evaluaciones rápidamente. Puede modificar estas plantillas para crear una evaluación optimizada para sus necesidades. También puede crear una evaluación personalizada creando una plantilla con sus propios controles y acciones. Por ejemplo, es posible que desee que una plantilla cubra un control interno de procesos empresariales o un estándar de protección de datos regional que no esté cubierto por una de nuestras más de 150 plantillas de evaluación predefinidas.

##### <a name="learn-more"></a>Más información

[Ver la lista de plantillas de evaluación proporcionadas por el Administrador de cumplimiento.](compliance-manager-templates-list.md)

[Obtenga instrucciones detalladas para crear y modificar plantillas para evaluaciones.](compliance-manager-templates.md)

### <a name="improvement-actions"></a>Acciones de mejora

Las acciones de mejora ayudan a centralizar las actividades de cumplimiento. Cada acción de mejora proporciona instrucciones recomendadas diseñadas para ayudarle a alinearse con las normas y normativas de protección de datos. Las acciones de mejora se pueden asignar a los usuarios de la organización para realizar el trabajo de implementación y pruebas. También puede almacenar documentación, notas y registrar actualizaciones de estado dentro de la acción de mejora.

##### <a name="learn-more"></a>Más información

[Use acciones de mejora para administrar el flujo de trabajo de cumplimiento.](compliance-manager-improvement-actions.md)

[Obtenga información sobre cómo las acciones afectan a la puntuación de cumplimiento.](compliance-score-calculation.md#action-types-and-points)

## <a name="supported-languages"></a>Idiomas admitidos

El Administrador de cumplimiento está disponible en los siguientes idiomas:

- Inglés
- Bahasa indonesio
- Malayo malayo
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

Obtenga información sobre cómo iniciar sesión, asignar permisos y roles, configurar opciones y personalizar la vista de panel en Introducción al Administrador [de cumplimiento.](compliance-manager-setup.md)

A continuación, empiece a personalizar el Administrador de cumplimiento para ayudarle a cumplir con los estándares del sector que son más importantes para su organización mediante la configuración [de evaluaciones.](compliance-manager-assessments.md)