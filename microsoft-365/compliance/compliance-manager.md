---
title: Administrador de cumplimiento de Microsoft Purview
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: Microsoft Purview Compliance Manager ayuda a las organizaciones a simplificar y automatizar las evaluaciones de riesgos, y sugiere acciones recomendadas para ayudar a abordar los riesgos.
ms.openlocfilehash: 74783c99873b76d3b3637947203bb58d4a656b13
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66634751"
---
# <a name="microsoft-purview-compliance-manager"></a>Administrador de cumplimiento de Microsoft Purview

> [!TIP]
> *¿Sabía que puede probar las versiones premium de las nueve soluciones de Microsoft Purview de forma gratuita?* Utilice la prueba de 90 días de las soluciones Purview para explorar cómo las sólidas capacidades de Purview pueden ayudar a su organización a satisfacer sus necesidades de cumplimiento. Los clientes Microsoft 365 E3 y Office 365 E3 pueden empezar ahora en el [Centro de pruebas del portal de cumplimiento de Microsoft Purview](https://compliance.microsoft.com/trialHorizontalHub?sku=ComplianceE5&ref=DocsRef). Obtenga información sobre [las personas que pueden registrarse y los términos de la prueba](compliance-easy-trials.md).

**En este artículo:** Obtenga información sobre qué es el Administrador de cumplimiento, cómo ayuda a simplificar el cumplimiento y reducir el riesgo, y sus componentes clave.

## <a name="what-is-compliance-manager"></a>¿Qué es el Administrador de cumplimiento?

[Microsoft Purview Compliance Manager](https://compliance.microsoft.com/compliancemanager) es una característica de la <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a> que le ayuda a administrar los requisitos de cumplimiento de su organización con mayor facilidad y comodidad. El Administrador de cumplimiento puede ayudarle a lo largo del proceso de cumplimiento, desde realizar un inventario de los riesgos de protección de datos hasta administrar las complejidades de la implementación de controles, estar al corriente de las normativas y certificaciones e informar a los auditores.

Vea el vídeo siguiente para obtener información sobre cómo el Administrador de cumplimiento puede ayudar a simplificar la forma en que su organización administra el cumplimiento:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4VdoO]

El Administrador de cumplimiento ayuda a simplificar el cumplimiento y reducir el riesgo proporcionando lo siguiente:

- Evaluaciones pregeneradas para estándares y reglamentos regionales y comunes del sector, o evaluaciones personalizadas para satisfacer sus necesidades de cumplimiento único (las evaluaciones disponibles dependen de su contrato de licencia; [más información](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)).

- Funcionalidades de flujo de trabajo que permiten completar de manera eficiente las evaluaciones de riesgos a través de una sola herramienta.

- Instrucciones detalladas paso a paso sobre las acciones de mejora sugeridas para ayudarle a cumplir con los estándares y regulaciones más relevantes para su organización. Para las acciones administradas por Microsoft, verá los detalles de la implementación y los resultados de la auditoría.

- Una puntuación de cumplimiento basada en riesgos que le ayudará a comprender su posición de cumplimiento mediante la medición del progreso en la realización de acciones de mejora.

La página de información general del Administrador de cumplimiento muestra la puntuación de cumplimiento actual, le ayuda a ver lo que necesita atención y le guía a las acciones de mejora clave. A continuación se muestra un ejemplo de la página de información general:

![Panel del Administrador de cumplimiento.](../media/compliance-manager-overview.png "Página de información general del Administrador de cumplimiento")

## <a name="understanding-your-compliance-score"></a>Descripción de la puntuación de cumplimiento

El Administrador de cumplimiento le concede puntos por completar las acciones de mejora realizadas para cumplir con una normativa, estándar o directiva, y combina esos puntos en una puntuación de cumplimiento general. Cada acción tiene un impacto diferente en la puntuación en función de los posibles riesgos implicados. La puntuación de cumplimiento puede ayudar a priorizar en qué acción centrarse para mejorar la posición general de cumplimiento.

El Administrador de cumplimiento proporciona una puntuación inicial basada en la línea base de protección de datos de Microsoft 365. Esta línea base es un conjunto de controles que incluye normas clave y estándares para la protección de datos y la gobernanza general de datos.

##### <a name="learn-more"></a>Más información

[Comprenda cómo se calcula la puntuación de cumplimiento](compliance-score-calculation.md).

[Aprenda a trabajar con acciones de mejora](compliance-manager-improvement-actions.md).

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a>Elementos clave: controles, evaluaciones, plantillas, acciones de mejora

El Administrador de cumplimiento usa varios elementos de datos para ayudarle a administrar las actividades de cumplimiento. Al usar el Administrador de cumplimiento para asignar, probar y supervisar las actividades de cumplimiento, resulta útil tener un conocimiento básico de los elementos clave: controles, evaluaciones, plantillas y acciones de mejora.

### <a name="controls"></a>Controles

Un control es un requisito de una normativa, un estándar o una directiva. Define cómo se evalúa y administra la configuración de un sistema, el proceso organizativo y las personas responsables de cumplir un requisito específico de un reglamento, un estándar o una directiva.

El Administrador de cumplimiento realiza un seguimiento de los siguientes tipos de controles:

1. **Controles administrados por Microsoft**: controles para los servicios en la nube de Microsoft, que Microsoft es responsable de implementar
2. **Los controles**: a veces se conocen como controles administrados por el cliente, estos son controles implementados y administrados por su organización.
3. **Controles compartidos**: son controles que tanto su organización como Microsoft comparten la responsabilidad de la implementación.

##### <a name="learn-more"></a>Más información

[Supervise el progreso de los controles](compliance-manager-assessments.md#monitor-assessment-progress-and-controls).

[Obtenga información sobre cómo el Administrador de cumplimiento evalúa continuamente los controles](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).

### <a name="assessments"></a>Evaluaciones

Una evaluación es la agrupación de controles de un reglamento, estándar o directiva específicos. Completar las acciones en una evaluación le ayuda a cumplir con los requisitos de unos estándares, una regulación o una ley. Por ejemplo, es posible que tenga una evaluación que, al completar todas las acciones que contiene, ayude a que la configuración de Microsoft 365 se alinee con los requisitos de ISO 27001.

Las evaluaciones tienen varios componentes:

- **Servicios dentro del ámbito**: configuración específica de los servicios Microsoft aplicables a la evaluación
- **Controles administrados por Microsoft**: controles para los servicios en la nube de Microsoft, que Microsoft implementa en su nombre
- **Los controles**: a veces se conocen como controles administrados por el cliente, estos son controles implementados y administrados por su organización.
- **Controles compartidos**: son controles que tanto su organización como Microsoft comparten la responsabilidad de la implementación.
- **Puntuación de evaluación**: muestra el progreso en el logro del total de puntos posibles de las acciones dentro de la evaluación administradas por su organización y por Microsoft.

Al crear evaluaciones, las asignará a un grupo. Puede configurar grupos de la manera más lógica para su organización. Por ejemplo, puede agrupar las evaluaciones por año de auditoría, región, solución, equipos de su organización o de alguna otra manera. Una vez creados los grupos, puede [filtrar el panel del Administrador de cumplimiento](compliance-manager-setup.md#filtering-your-dashboard-view) para ver la puntuación por uno o varios grupos.

##### <a name="learn-more"></a>Más información

[Cree y administre evaluaciones en el Administrador de cumplimiento](compliance-manager-assessments.md).

### <a name="templates"></a>Plantillas

El Administrador de cumplimiento proporciona plantillas que le ayudarán a crear rápidamente evaluaciones. Puede modificar estas plantillas para crear una evaluación optimizada para sus necesidades. También puede crear una evaluación personalizada mediante la creación de una plantilla con sus propios controles y acciones. Por ejemplo, es posible que desee que una plantilla cubra un control interno de procesos empresariales o un estándar de protección de datos regional que no esté cubierto por una de nuestras más de 325 plantillas de evaluación pregeneradas.

##### <a name="learn-more"></a>Más información

[Vea la lista de plantillas de evaluación proporcionadas por el Administrador de cumplimiento](compliance-manager-templates-list.md).

[Obtenga instrucciones detalladas para crear y modificar plantillas para evaluaciones](compliance-manager-templates.md).

### <a name="improvement-actions"></a>Acciones de mejora

Las acciones de mejora ayudan a centralizar las actividades de cumplimiento. Cada acción de mejora proporciona instrucciones recomendadas destinadas a ayudarle a alinearse con las normativas y estándares de protección de datos. Las acciones de mejora se pueden asignar a los usuarios de la organización para realizar el trabajo de implementación y pruebas. También puede almacenar la documentación, las notas y registrar las actualizaciones de estado dentro de la acción de mejora.

##### <a name="learn-more"></a>Más información

[Use acciones de mejora para administrar el flujo de trabajo de cumplimiento](compliance-manager-improvement-actions.md).

[Obtenga información sobre cómo afectan las acciones a la puntuación de cumplimiento](compliance-score-calculation.md#action-types-and-points).

## <a name="supported-languages"></a>Idiomas admitidos

El Administrador de cumplimiento está disponible en los siguientes idiomas:

- Inglés
- Bahasa indonesia
- Bahasa Malayo
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

## <a name="next-steps-set-up-and-customize"></a>Pasos siguientes: configuración y personalización

Obtenga información sobre cómo iniciar sesión, asignar permisos y roles, configurar opciones y personalizar la vista del panel en [Introducción al Administrador de cumplimiento](compliance-manager-setup.md).

A continuación, empiece a personalizar el Administrador de cumplimiento para ayudarle a cumplir con los estándares del sector que más le importan a su organización mediante [la configuración de evaluaciones](compliance-manager-assessments.md).

Para ayudarle a cumplir con las regulaciones de privacidad de datos, hemos diseñado un flujo de trabajo que le guiará a través de un proceso de un extremo a otro para planear e implementar funcionalidades en Microsoft 365, incluido el uso del Administrador de cumplimiento. Para obtener más información, consulte [Implementar la protección de la información para normativas de privacidad de datos con Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy). 
