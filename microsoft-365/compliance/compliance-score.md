---
title: Puntuación de cumplimiento de Microsoft
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
description: La puntuación de cumplimiento de Microsoft ayuda a las organizaciones a simplificar y automatizar las evaluaciones de riesgos, y sugiere acciones recomendadas para enfrentarse a los riesgos.
ms.openlocfilehash: 3c7a4bdfd5de7a9a6dcbede5146ebb517acdb4bb
ms.sourcegitcommit: 56772bed89516cebc5eb370e292ccfbb4889cb38
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330804"
---
# <a name="microsoft-compliance-score-preview"></a>Puntuación de cumplimiento de Microsoft (versión preliminar)

La [puntuación de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancescore) ayuda a simplificar la forma en que administra el cumplimiento y reduce los riesgos de cumplimiento mediante una experiencia fácil de uso. La puntuación de cumplimiento está disponible para la versión preliminar pública en el [centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center.md).

**En este artículo:** Lea este artículo para comprender qué puntuación de cumplimiento es y cómo configurarlo para su organización.

**Obtenga información sobre las actualizaciones:** Publicamos varias actualizaciones en la versión de abril de 2020. Visite las [notas](compliance-score-release-notes.md) de la versión de calificación de cumplimiento para ver las novedades y los problemas conocidos con la versión preliminar de la puntuación de cumplimiento.

## <a name="what-is-compliance-score"></a>¿Qué es la puntuación de cumplimiento?

La puntuación de cumplimiento de Microsoft es una característica de vista previa del centro de cumplimiento de Microsoft 365 para ayudarle a comprender la postura de cumplimiento de la organización. Calcula una puntuación basada en riesgos que mide su progreso en la realización de acciones que ayudan a reducir los riesgos en torno a la protección de datos y los estándares normativos.

Puede usar la puntuación de cumplimiento como una herramienta para realizar un seguimiento de todas las evaluaciones de riesgos. Proporciona funcionalidades de flujo de trabajo para ayudarle a completar eficazmente las evaluaciones de riesgos mediante una herramienta común.

Si actualmente usa el [Administrador de cumplimiento](compliance-manager-overview.md), observará que la puntuación de cumplimiento es ahora una característica independiente con un diseño más sencillo y fácil de usar para ayudarle a administrar el cumplimiento con mayor facilidad. 

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

Piense en la puntuación de cumplimiento como una versión simplificada del administrador de cumplimiento. Aunque existen dos herramientas distintas pero integradas, la puntuación de cumplimiento hace que sea más fácil supervisar el nivel de cumplimiento general y tomar medidas para mejorarla.

La puntuación de cumplimiento comparte el mismo servidor con el administrador de cumplimiento, de modo que todos los datos que puedan existir en el administrador de cumplimiento se mostrarán en la puntuación de cumplimiento.

Algunas funcionalidades se conservan únicamente en el administrador de cumplimiento durante la versión preliminar pública, como la administración de evaluaciones y la creación de plantillas. Se recomienda comenzar todas las actividades de administración de cumplimiento en puntuación de cumplimiento. Cuando llegue a funciones administradas por el administrador de cumplimiento, se le guiará a esa herramienta. Por ese motivo, parte de esta documentación le dirige a los temas del administrador de cumplimiento.

Obtenga más información sobre la relación entre la puntuación de cumplimiento y el administrador de cumplimiento en las notas de la [versión de puntuación de cumplimiento](compliance-score-release-notes.md).

## <a name="understanding-your-score"></a>Descripción de la puntuación

La puntuación de cumplimiento proporciona una puntuación inicial basada en la línea base de protección de datos 365 de Microsoft. Esta línea de base es un conjunto de controles que incluye reglamentos y normas comunes de la industria. Aunque esta puntuación es un buen punto de partida para evaluar su postura de cumplimiento, la puntuación de cumplimiento será más eficaz una vez que agregue evaluaciones que sean más relevantes para su organización.

Por ejemplo, si su organización pertenece a la industria de servicios financieros, es posible que quiera agregar la evaluación de FFIEC. Si su organización pertenece a la industria de la salud, puede Agregar la evaluación de HIPAA/alta tecnología. Obtenga información sobre cómo [Agregar evaluaciones en el administrador de cumplimiento](working-with-compliance-manager.md#assessments).

Obtenga más información sobre [cómo se calcula y se supervisa continuamente la puntuación de cumplimiento](compliance-score-methodology.md).


## <a name="key-components-controls-assessments-templates-groups"></a>Componentes clave: controles, evaluaciones, plantillas, grupos

La puntuación de cumplimiento usa varios componentes para ayudarle a administrar las actividades de cumplimiento. A medida que se usa la puntuación de cumplimiento para asignar, probar y supervisar las actividades de cumplimiento, resulta útil tener un conocimiento básico de los componentes clave: controles, evaluaciones, plantillas y grupos.

### <a name="controls"></a>Controles

Un control define cómo se evalúa y administra la configuración del sistema, el proceso de organización y las personas responsables de cumplir un requisito específico de una regla, un estándar o una directiva interna.

La puntuación de cumplimiento hace un seguimiento de dos tipos de controles:

1. **Controles administrados por Microsoft**: controles para los servicios en la nube de Microsoft, que Microsoft es responsable de implementar
2. **Controles administrados**por el cliente: controles administrados por su organización, que es responsable de implementar
 
### <a name="assessments"></a>Evaluaciones

Una evaluación es una evaluación de una plantilla que inicia el proceso de calificación de la organización. Las evaluaciones agrupan las acciones necesarias para cumplir los requisitos de normas, reglamentaciones o legales. Por ejemplo, puede tener una evaluación que, al completar todas las acciones de la misma, la configuración de Office 365 en línea con los requisitos de la norma ISO 27001.

Puntuación de cumplimiento proporciona a su organización una evaluación inicial basada en la línea base de protección de datos 365 de Microsoft. Esta evaluación es una recomendación para reducir los riesgos de protección y cumplimiento de datos (más[información](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).

Las evaluaciones tienen varios componentes:

- **Servicios en el ámbito**: el conjunto específico de servicios de Microsoft que se aplican a la evaluación
- **Controles administrados por Microsoft**: controles que Microsoft implementó y probó
- **Controles administrados por el cliente**: controles que administra
- **Puntuación**de la evaluación: porcentaje de los puntos logrados al completar acciones dentro de dicha evaluación.

> [!NOTE]
> Puntuación de cumplimiento muestra las evaluaciones y la forma en que se factorizan en la puntuación general. Sin embargo, en la versión preliminar pública se le dirigirá al administrador de cumplimiento para que administre sus evaluaciones.

Vea las instrucciones detalladas para [administrar las evaluaciones en el administrador de cumplimiento](working-with-compliance-manager.md#assessments).

### <a name="templates"></a>Plantillas

La puntuación de cumplimiento proporciona plantillas preconfiguradas para las evaluaciones. También puede crear una evaluación personalizada agregando sus propios controles y acciones a una plantilla preconfigurada. Por ejemplo, puede crear una plantilla para el control del proceso de negocio o una plantilla para un estándar de protección o cumplimiento de datos regional que no esté cubierta por una de las plantillas preconfiguradas. Al incluir sus propias plantillas en la puntuación de cumplimiento, puede realizar un seguimiento no solo de las evaluaciones de la nube de Microsoft, sino también de otras evaluaciones de riesgos en el ámbito de su organización.

Las plantillas preconfiguradas para la puntuación de cumplimiento son:

1. [Ley de protección de datos general de Brasil (LGPD)](https://go.microsoft.com/fwlink/?linkid=2115387)
2. [Ley de privacidad del consumidor de California (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (versión preliminar)
3. [Matriz de controles de nube (CCM) de Cloud Security Alliance (CSA) 3.0.1](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [Solución de seguridad de la información Dubai (DGISR)](https://go.microsoft.com/fwlink/?linkid=2131193)
5. [RGPD de la Unión Europea](https://go.microsoft.com/fwlink/?linkid=2108870)
6. [Instituciones financieras federales centro de examen (FFIEC) folleto de seguridad de la información](https://go.microsoft.com/fwlink/?linkid=2109077)
7. [Moderado FedRAMP](https://go.microsoft.com/fwlink/?linkid=2108869)
8. [HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078)  /  [Alta tecnología](https://go.microsoft.com/fwlink/?linkid=2109079)
9. [IRAP](https://go.microsoft.com/fwlink/?linkid=2113709)  /  [ISM del gobierno australiano](https://go.microsoft.com/fwlink/?linkid=2113024) (versión preliminar)
10. [ISO 27001:2013](https://go.microsoft.com/fwlink/?linkid=2109073)
11. [ISO 27018:2014](https://go.microsoft.com/fwlink/?linkid=2109074)
12. [ISO 27701:2019](https://go.microsoft.com/fwlink/?linkid=2113025)
13. [Línea base de protección de datos 365 de Microsoft](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
14. [NIST 800-53 Rev. 4](https://go.microsoft.com/fwlink/?linkid=2109075)
15. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
16. [NIST Cybersecurity Framework (CSF)](https://go.microsoft.com/fwlink/?linkid=2108868)
17. [SOC 1](https://go.microsoft.com/fwlink/?linkid=2115184)
18. [SOC 2](https://go.microsoft.com/fwlink/?linkid=2115184)

Vea [las instrucciones detalladas para crear plantillas](working-with-compliance-manager.md#templates), que se produce en el administrador de cumplimiento.

### <a name="groups"></a>Grupos

Los grupos le permiten organizar las evaluaciones de forma lógica para usted. Por ejemplo, puede optar por agrupar las evaluaciones por año, el estándar de cumplimiento, el servicio, los equipos de la organización o algún otro modo.

Cuando dos evaluaciones distintas en el mismo grupo comparten acciones administradas por el cliente, las actualizaciones que se realizan en los detalles de implementación, las pruebas y el estado de la acción en una evaluación se sincronizarán automáticamente con la misma acción en cualquier otra evaluación del grupo. La sincronización de acciones de esta manera unifica las acciones de mejora asignadas en el grupo y reduce el trabajo de duplicación.

Obtenga información sobre cómo [crear grupos en el administrador de cumplimiento](working-with-compliance-manager.md#groups). Una vez que haya creado los grupos, puede [filtrar el panel de puntuaciones de cumplimiento](compliance-score-setup.md#filtering-your-dashboard-view) para ver la puntuación de uno o varios grupos.

## <a name="next-step-begin-setup"></a>Siguiente paso: iniciar la instalación

Obtenga información sobre cómo iniciar sesión, configurar los permisos y configurar las actualizaciones y las vistas del panel en la configuración de la [puntuación de cumplimiento](compliance-score-setup.md).
