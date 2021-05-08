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
description: Microsoft Compliance Manager ayuda a las organizaciones a simplificar y automatizar las evaluaciones de riesgos y sugiere acciones recomendadas para ayudar a solucionar los riesgos.
ms.openlocfilehash: 7eb8e0fdea26ca24453ca7071ab1282c686d5848
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244400"
---
# <a name="microsoft-compliance-manager"></a>Administrador de cumplimiento de Microsoft

**En este artículo:** Obtenga información sobre lo que es el Administrador de cumplimiento, cómo ayuda a simplificar el cumplimiento y reducir los riesgos, y sus componentes clave.

## <a name="whats-new-the-ga-release-of-compliance-manager"></a>Novedades: la versión de GA del Administrador de cumplimiento

El Administrador de cumplimiento ya está disponible generalmente (GA) como una solución de administración de cumplimiento integral dentro del centro de Microsoft 365 [cumplimiento.](microsoft-365-compliance-center.md) Con esta versión, el Administrador de cumplimiento completa la transición desde su ubicación anterior en el Portal de confianza de servicio de Microsoft. El Administrador de cumplimiento también está disponible para los Community (GCC) moderados, GCC altos y del Departamento de Defensa (DoD).

Lo que comenzó como la vista previa pública de la puntuación de cumplimiento ha evolucionado hasta convertirse en una herramienta centralizada con capacidades de administración de cumplimiento mejoradas y mayor facilidad de uso.  La versión de ga ofrece una colección más grande de evaluaciones predefinidas para ayudarle a escalar sus actividades de cumplimiento.

**Obtenga más información sobre la versión de GA:**
- Nuestras [preguntas más frecuentes le](compliance-manager-faq.md) guían a través de la evolución con más detalle.
- Lea acerca de las mejoras de características de GA en [esta entrada de blog](https://aka.ms/compliancemanager/GAblog).

Vea el vídeo siguiente para obtener información sobre cómo el Administrador de cumplimiento puede ayudar a simplificar la forma en que su organización administra el cumplimiento:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a>Qué es el Administrador de cumplimiento

[Microsoft Compliance Manager es](https://compliance.microsoft.com/compliancemanager) una característica del centro de cumplimiento [Microsoft 365](microsoft-365-compliance-center.md) que le ayuda a administrar los requisitos de cumplimiento de su organización con mayor facilidad y comodidad. El Administrador de cumplimiento puede ayudarle a lo largo de su recorrido de cumplimiento, desde realizar un inventario de los riesgos de protección de datos hasta administrar las complejidades de la implementación de controles, mantenerse al día con las normativas y certificaciones, y los informes a los auditores.

El Administrador de cumplimiento ayuda a simplificar el cumplimiento y reducir los riesgos proporcionando:

- Evaluaciones predefinidas para estándares y normativas regionales y del sector comunes, o evaluaciones personalizadas para satisfacer sus necesidades de cumplimiento únicas (las evaluaciones disponibles dependen de su contrato de licencia; [más información](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)).

- Capacidades de flujo de trabajo para ayudarle a completar eficazmente sus evaluaciones de riesgos a través de una sola herramienta.

- Instrucciones detalladas paso a paso sobre las acciones de mejora sugeridas para ayudarle a cumplir con los estándares y normativas más relevantes para su organización. Para las acciones administradas por Microsoft, verá los detalles de implementación y los resultados de auditoría.

- Una puntuación de cumplimiento basada en riesgos que le ayudará a comprender su posición de cumplimiento midiendo su progreso en la realización de acciones de mejora.

El panel del Administrador de cumplimiento muestra la puntuación de cumplimiento actual, le ayuda a ver qué necesita atención y le guía a las acciones de mejora clave. A continuación se muestra un ejemplo de cómo será el panel del Administrador de cumplimiento:

![Administrador de cumplimiento: panel](../media/compliance-manager-dashboard.png "Panel del Administrador de cumplimiento")

## <a name="understanding-your-compliance-score"></a>Descripción de la puntuación de cumplimiento

El Administrador de cumplimiento le otorga puntos por completar las acciones de mejora realizadas para cumplir con un reglamento, estándar o directiva, y combina esos puntos en una puntuación general de cumplimiento. Cada acción tiene un impacto diferente en la puntuación en función de los posibles riesgos implicados. La puntuación de cumplimiento puede ayudar a priorizar la acción en la que se debe centrarse para mejorar la posición general de cumplimiento.

El Administrador de cumplimiento le proporciona una puntuación inicial basada en la línea Microsoft 365 base de protección de datos. Esta línea base es un conjunto de controles que incluye normativas y estándares clave para la protección de datos y el gobierno general de datos.

##### <a name="learn-more"></a>Más información

[Comprender cómo se calcula la puntuación de cumplimiento](compliance-score-calculation.md).

[Obtenga información sobre cómo trabajar con acciones de mejora](compliance-manager-improvement-actions.md).

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a>Elementos clave: controles, evaluaciones, plantillas, acciones de mejora

El Administrador de cumplimiento usa varios elementos de datos para ayudarle a administrar sus actividades de cumplimiento. A medida que usa el Administrador de cumplimiento para asignar, probar y supervisar actividades de cumplimiento, resulta útil tener una comprensión básica de los elementos clave: controles, evaluaciones, plantillas y acciones de mejora.

### <a name="controls"></a>Controles

Un control es un requisito de un reglamento, estándar o directiva. Define cómo evaluar y administrar la configuración del sistema, el proceso organizativo y las personas responsables de cumplir un requisito específico de un reglamento, estándar o directiva.

El Administrador de cumplimiento realiza un seguimiento de los siguientes tipos de controles:

1. **Controles administrados por Microsoft:** controles para los servicios en la nube de Microsoft, que Microsoft es responsable de implementar
2. **Los controles:** a veces denominados controles administrados por el cliente, estos son controles implementados y administrados por la organización
3. **Controles compartidos:** estos son controles que su organización y Microsoft comparten la responsabilidad de implementar

##### <a name="learn-more"></a>Más información

[Supervisar el progreso de los controles](compliance-manager-assessments.md#monitor-assessment-progress-and-controls).

[Obtenga información sobre cómo el Administrador de cumplimiento evalúa continuamente los controles](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).

### <a name="assessments"></a>Evaluaciones

Una evaluación es la agrupación de controles de un reglamento, estándar o directiva específicos. Completar las acciones dentro de una evaluación le ayudará a cumplir los requisitos de una norma, reglamento o ley. Por ejemplo, es posible que tenga una evaluación que, al completar todas las acciones dentro de ella, ayude a que la configuración de Microsoft 365 se alinee con los requisitos iso 27001.

Las evaluaciones tienen varios componentes:

- **Servicios dentro del ámbito**: configuración específica de los servicios Microsoft aplicables a la evaluación
- **Controles administrados de Microsoft:** controles para los servicios en la nube de Microsoft, que Microsoft implementa en su nombre
- **Los controles:** a veces denominados controles administrados por el cliente, estos son controles implementados y administrados por la organización
- **Controles compartidos:** estos son controles que su organización y Microsoft comparten la responsabilidad de implementar
- **Puntuación de** evaluación: muestra el progreso en el logro de puntos posibles totales de las acciones dentro de la evaluación administradas por su organización y por Microsoft

Al crear evaluaciones, las asignará a un grupo. Puede configurar grupos de la forma que sea más lógica para su organización. Por ejemplo, puede agrupar evaluaciones por año de auditoría, región, solución, equipos dentro de su organización o de alguna otra forma. Una vez creados los grupos, puede filtrar el panel del Administrador [de cumplimiento](compliance-manager-setup.md#filtering-your-dashboard-view) para ver la puntuación por uno o varios grupos.

##### <a name="learn-more"></a>Más información

[Cree y administre evaluaciones en el Administrador de cumplimiento](compliance-manager-assessments.md).

### <a name="templates"></a>Plantillas

El Administrador de cumplimiento proporciona plantillas para ayudarle a crear rápidamente evaluaciones. Puede modificar estas plantillas para crear una evaluación optimizada para sus necesidades. También puede crear una evaluación personalizada creando una plantilla con sus propios controles y acciones. Por ejemplo, es posible que desee que una plantilla cubra un control de proceso empresarial interno o un estándar regional de protección de datos que no esté cubierto por una de nuestras más de 325 plantillas de evaluación predefinidas.

##### <a name="learn-more"></a>Más información

[Ver la lista de plantillas de evaluación proporcionadas por el Administrador de cumplimiento](compliance-manager-templates-list.md).

[Obtenga instrucciones detalladas para crear y modificar plantillas para evaluaciones.](compliance-manager-templates.md)

### <a name="improvement-actions"></a>Acciones de mejora

Las acciones de mejora ayudan a centralizar las actividades de cumplimiento. Cada acción de mejora proporciona instrucciones recomendadas que le ayudarán a alinearse con las normativas y estándares de protección de datos. Las acciones de mejora se pueden asignar a los usuarios de la organización para realizar el trabajo de implementación y pruebas. También puede almacenar documentación, notas y registrar actualizaciones de estado dentro de la acción de mejora.

##### <a name="learn-more"></a>Más información

[Use acciones de mejora para administrar el flujo de trabajo de cumplimiento](compliance-manager-improvement-actions.md).

[Obtenga información sobre cómo las acciones afectan a la puntuación de cumplimiento](compliance-score-calculation.md#action-types-and-points).

## <a name="supported-languages"></a>Idiomas admitidos

El Administrador de cumplimiento está disponible en los siguientes idiomas:

- Inglés
- Bahasa Indonesio
- Bahasa Malay
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

Obtenga información sobre cómo iniciar sesión, asignar permisos y roles, configurar la configuración y personalizar la vista del panel en [Introducción al Administrador de cumplimiento](compliance-manager-setup.md).

A continuación, comience a personalizar el Administrador de cumplimiento para ayudarle a cumplir con los estándares del sector que más importan a su organización mediante la [configuración de evaluaciones](compliance-manager-assessments.md).

Para ayudarle a cumplir con las normativas de privacidad de datos, hemos diseñado un flujo de trabajo para guiarlo a través de un proceso completo para planear e implementar funcionalidades en Microsoft 365, incluido el uso del Administrador de cumplimiento. Para obtener más información, consulte [Implementar la protección de la información para normativas de privacidad de datos con Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy). 