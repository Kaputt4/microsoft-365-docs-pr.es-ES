---
title: Usar el administrador de cumplimiento para administrar acciones de mejora
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Obtenga información sobre cómo usar la puntuación de cumplimiento y el administrador de cumplimiento para mejorar el nivel de protección de los datos personales.
ms.openlocfilehash: f90826795197b392f629eb8eec71b7f27081b697
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791887"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Usar el administrador de cumplimiento para administrar acciones de mejora

El administrador de cumplimiento de Microsoft puede ayudarle a administrar las mejoras relacionadas con las regulaciones de privacidad de datos como el [Reglamento de protección general de datos (RGPD)](../compliance/gdpr.md)de la Unión Europea, la ley de protección del [consumidor de California CCPA)](../compliance/ccpa-faq.md), HIPAA-up (Act de Sanidad de Estados Unidos) y la ley de protección de datos de Brasil (LGPD).

En este artículo se proporcionan instrucciones sobre el uso de esta herramienta para fines de privacidad de datos.

>[!Note]
>Las recomendaciones del Administrador de cumplimiento no deberán interpretarse como una garantía de cumplimiento. Depende de usted evaluar y validar la eficacia de los controles de cliente según su entorno de reglamentación. Estos servicios están sujetos a los términos y condiciones de los [términos de servicios en línea](https://go.microsoft.com/fwlink/?linkid=2108910). Consulte también la [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)
>

## <a name="getting-started-with-compliance-manager"></a>Introducción al administrador de cumplimiento

#### <a name="what-is-compliance-manager"></a>Qué es el administrador de cumplimiento

El [Administrador de cumplimiento](../compliance/compliance-manager.md) es una herramienta de evaluación de riesgos basada en flujos de trabajo en el centro de cumplimiento de Microsoft 365 para administrar las actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft. Como parte de su suscripción a Microsoft 365 o Azure Active Directory (Azure AD), el administrador de cumplimiento le ayuda a administrar el cumplimiento de normativas en el modelo de responsabilidad compartida para los servicios en la nube de Microsoft.

**Listo para usar evaluaciones**

El administrador de cumplimiento proporciona plantillas predefinidas para [crear evaluaciones](../compliance/compliance-manager-assessments.md) que se alinean con las regulaciones relacionadas con la privacidad de los datos, como RGPD y HIPAA/alta tecnología. Las plantillas tienen una asignación de control integrada para ayudarle a llevar a cabo las acciones de mejora para cumplir los requisitos de la regla. Cada evaluación proporciona información acerca de los controles a los que cada regla llama específicamente para el servicio de destino, desglosado por los controles que administra y controla los administrados por Microsoft. 

Usar una plantilla predefinida le ayudará a empezar rápidamente con las evaluaciones de riesgos. A medida que sea más experto en el uso del administrador de cumplimiento, puede personalizar una plantilla predefinida agregando sus propios controles y acciones de mejora, o puede crear sus propias evaluaciones personalizadas que se adapten a las necesidades de su organización.

Ver la [lista completa de plantillas de evaluación](../compliance/compliance-manager-templates-list.md) que proporciona el administrador de cumplimiento.

**Puntuación de cumplimiento en tiempo real**

El administrador de cumplimiento también proporciona una puntuación de cumplimiento que mide el progreso de la finalización de las acciones de mejora recomendadas dentro de los controles. Puede usar esta puntuación como ayuda para supervisar el progreso y priorizar las acciones según su potencial para reducir el riesgo.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>Usar la guía de inicio rápido del administrador de cumplimiento

La guía de [Inicio rápido del administrador de cumplimiento](../compliance/compliance-manager-quickstart.md) proporciona pasos graduados y vínculos a recursos clave para ayudarle a trabajar con el administrador de cumplimiento:

- [Primera visita: familiarizarse con el administrador de cumplimiento](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Trabajar con el panel del administrador de cumplimiento
    - Descripción de la puntuación de cumplimiento
    - Aprendizaje de las acciones de mejora
    - Descripción de las evaluaciones y las plantillas
- [Rampa en marcha: configurar el administrador de cumplimiento para administrar las actividades de cumplimiento](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Creación y administración de la primera evaluación
    - Realización de pruebas y pruebas de las acciones de mejora para completar los controles en las evaluaciones
    - Descripción de cómo afectan las distintas acciones a la puntuación de cumplimiento
- [Escalado vertical: Use la funcionalidad avanzada para satisfacer sus necesidades personalizadas.](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Crear evaluaciones personalizadas para realizar un seguimiento de productos que no son de 365 de Microsoft
    - Modificación de las plantillas existentes para agregar o quitar controles
    - Configuración de pruebas automáticas de acciones de mejora

## <a name="how-your-compliance-score-is-calculated"></a>Cómo se calcula su puntuación de cumplimiento

La puntuación de cumplimiento se calcula en función de una combinación de implementaciones de controles administrados por el cliente y Microsoft. Consulte [cálculo](../compliance/compliance-score-calculation.md) de la puntuación de cumplimiento para obtener una explicación detallada.

A los controles se les asigna un valor de puntuación en función de si son obligatorios o discrecionales, y si son preventivos, detectives o correctivos. Estos representan colectivamente el riesgo de no implementarlo en relación con otros controles.

Como se muestra en el artículo de cálculo de la puntuación de cumplimiento, los controles preventivos obtienen una puntuación mayor que el detective y los correctivos, y los controles obligatorios obtienen una puntuación mayor que los discrecionales.

La interfaz de usuario del administrador de puntuación de cumplimiento no enumera estos parámetros, ni proporciona la capacidad de filtrarlos por ellos. Sin embargo, si descarga la plantilla asociada desde el administrador de cumplimiento, el conjunto de datos resultante enumera estos parámetros para la mayoría de las regulaciones.

Para los controles técnicos, el administrador de cumplimiento actualiza automáticamente el resultado de la acción de mejora una vez que la acción se ha implementado y probado correctamente. Otras acciones de control no técnicas, como &mdash; las operaciones operativas o relacionadas con la documentación, &mdash; deben registrarse manualmente como implementadas antes de que los puntos se resuman a su puntuación.

También puede implementar ciertas acciones de mejora para otros fines &mdash; por ejemplo, mediante el uso de etiquetas de retención por motivos que no sean el cumplimiento normativo de la privacidad de los datos, por lo que recibirá &mdash; crédito por usar dicha característica incluso si se usa para otros fines y no como parte de una acción de cumplimiento deliberada.

La puntuación de cumplimiento debe considerarse una medida relativa para realizar el seguimiento de la mejora en una escala amplia. No debe obtener una puntuación perfecta.

## <a name="additional-guidance"></a>Instrucciones adicionales

Estas son algunas sugerencias importantes para usar el administrador de cumplimiento para ayudarle a lograr el cumplimiento normativo de privacidad de datos:

- Cada normativa de privacidad de los datos tiene una combinación de controles técnicos, especificaciones de documentación y requisitos de funcionamiento, proceso e informes. Todas estas se muestran en las acciones de mejora.

- Para centrarse en la vista de las acciones de mejora en su área de interés, puede filtrar por tipo de acción en la ficha **soluciones** del administrador del administrador de cumplimiento. Obtenga más información sobre cómo [filtrar la vista de panel del administrador de cumplimiento](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).

- La importancia relativa y la prioridad de las acciones de mejora que se identifican en el administrador de cumplimiento deben considerarse como parte de una revisión de riesgos más amplia junto con los riesgos de privacidad de datos que ha determinado que su organización debe administrar.

- Incluso con la agregación de acciones de mejora en varios requisitos normativos, si se seleccionan las plantillas de evaluación del Reglamento para RGPD, LGPD, CCPA y HIPAA-alta tecnología, por ejemplo, las acciones de mejora de 400 se enumerarán en el administrador de cumplimiento. Para abordar mejor esta larga lista, use el filtro acción de mejora para reducir el conjunto de resultados a una lista más fácil de administrar.

- El filtro categorías proporciona un medio para filtrar acciones de mejora mediante la Agrupación lógica, que los artículos Track, impiden, Protect, retain e Investigate en esta solución general se alinean con.

- Es posible que algunos de los controles enumerados en las acciones de mejora se consideren directamente ligados a un artículo reglamentario específico, mientras que otros controles pueden asociarse más indirectamente con el espíritu de un Reglamento y muchas veces son simplemente actividades recomendadas o procedimientos recomendados.