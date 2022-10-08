---
title: Uso del Administrador de cumplimiento para administrar acciones de mejora
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
- zerotrust-solution
ms.custom: admindeeplinkCOMPLIANCE
description: Obtenga información sobre cómo usar la puntuación de cumplimiento y el Administrador de cumplimiento para mejorar el nivel de protección de los datos personales.
ms.openlocfilehash: f5cc20e77e480369a6f6e606ea9245a928368184
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986232"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Uso del Administrador de cumplimiento para administrar acciones de mejora

Microsoft Purview Compliance Manager puede ayudarle a administrar mejoras relacionadas con las regulaciones de privacidad de datos, como el [Reglamento General de Protección de Datos (RGPD)](/compliance/regulatory/gdpr) de la Unión Europea, la [Ley de Protección del Consumidor de California (CCPA)](/compliance/regulatory/ccpa-faq), HIPAA-HITECH (ley de privacidad del cuidado de salud de EE. UU.) y la Ley de protección de datos de Brasil (LGPD).

En este artículo se proporcionan instrucciones sobre el uso de esta herramienta con fines de privacidad de datos.

> [!NOTE]
> Las recomendaciones del Administrador de cumplimiento no deberán interpretarse como una garantía de cumplimiento. Depende de usted evaluar y validar la eficacia de los controles de los clientes según su entorno normativo. Estos servicios están sujetos a los términos y condiciones de los [Términos de servicios en línea](https://go.microsoft.com/fwlink/?linkid=2108910). Consulte también [la guía de licencias de Microsoft 365 para obtener información sobre seguridad y cumplimiento.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

## <a name="getting-started-with-compliance-manager"></a>Introducción al Administrador de cumplimiento

#### <a name="what-is-compliance-manager"></a>¿Qué es el Administrador de cumplimiento?

[El Administrador de cumplimiento](../compliance/compliance-manager.md) es una herramienta de evaluación de riesgos basada en flujos de trabajo en la portal de cumplimiento Microsoft Purview para administrar las actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft. Como parte de su suscripción de Microsoft 365 o Azure Active Directory (Azure AD), el Administrador de cumplimiento le ayuda a administrar el cumplimiento normativo dentro del modelo de responsabilidad compartida para los servicios en la nube de Microsoft.

**Evaluaciones listas para usar**

El Administrador de cumplimiento proporciona plantillas pregeneradas para [crear evaluaciones](../compliance/compliance-manager-assessments.md) que están alineadas con las regulaciones relacionadas con la privacidad de los datos, como RGPD e HIPAA/HITECH. Las plantillas tienen una asignación de control integrada para ayudarle a realizar acciones de mejora para cumplir los requisitos del reglamento. Cada evaluación proporciona información sobre los controles que cada regulación llama a para específico del servicio de destino, desglosados por los controles que administra y controla Microsoft.

El uso de una plantilla pregenerada le ayuda a empezar a trabajar rápidamente con las evaluaciones de riesgos. A medida que se vuelve más experto en el uso del Administrador de cumplimiento, puede personalizar una plantilla pregenerada agregando sus propios controles y acciones de mejora, o bien puede crear sus propias evaluaciones personalizadas para satisfacer las necesidades de su organización.

Vea la [lista completa de plantillas de evaluación](../compliance/compliance-manager-templates-list.md) proporcionadas por el Administrador de cumplimiento.

**Puntuación de cumplimiento en tiempo real**

El Administrador de cumplimiento también proporciona una puntuación de cumplimiento que mide el progreso al completar las acciones de mejora recomendadas dentro de los controles. Puede usar esta puntuación para ayudar a supervisar el progreso y priorizar las acciones en función de su potencial para reducir el riesgo.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>Uso de la guía de inicio rápido del Administrador de cumplimiento

La guía de [inicio rápido del Administrador](../compliance/compliance-manager-quickstart.md) de cumplimiento proporciona pasos graduados y vínculos a recursos clave para ayudarle a trabajar con el Administrador de cumplimiento:

- [Primera visita: familiarizarse con el Administrador de cumplimiento](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Trabajar con el panel del Administrador de cumplimiento
    - Descripción de la puntuación de cumplimiento
    - Información sobre las acciones de mejora
    - Descripción de las evaluaciones y plantillas
- [Aumento: configuración del Administrador de cumplimiento para administrar las actividades de cumplimiento](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Creación y administración de la primera evaluación
    - Realización de trabajos de implementación y pruebas en acciones de mejora para completar controles en las evaluaciones
    - Descripción de cómo afectan las distintas acciones a la puntuación de cumplimiento
- [Escalado vertical: use la funcionalidad avanzada para satisfacer sus necesidades personalizadas](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Creación de evaluaciones personalizadas para realizar un seguimiento de productos que no son de Microsoft 365
    - Modificación de plantillas existentes para agregar o quitar controles
    - Configuración de pruebas automatizadas de acciones de mejora

## <a name="how-your-compliance-score-is-calculated"></a>Cómo se calcula su puntuación de cumplimiento

La puntuación de cumplimiento se calcula en función de una combinación de implementaciones de control administradas por el cliente y Microsoft. Consulte [el cálculo de la puntuación de cumplimiento](../compliance/compliance-score-calculation.md) para obtener una explicación detallada.

A los controles se les asigna un valor de puntuación en función de si son obligatorios o discrecionales, y de si son preventivos, detectives o correctivos. Estos representan colectivamente el riesgo de no implementarla en relación con otros controles.

Como se presenta en el artículo de cálculo de la puntuación de cumplimiento, los controles preventivos obtienen una puntuación más alta que los controles de detectives y correctivos, y los controles obligatorios obtienen una puntuación más alta que los discrecionales.

La interfaz de usuario de administrador de puntuación de cumplimiento no enumera estos parámetros ni proporciona la capacidad de filtrar por ellos. Sin embargo, si descarga la plantilla asociada del Administrador de cumplimiento, el conjunto de datos resultante enumera estos parámetros para la mayoría de las regulaciones.

En el caso de los controles técnicos, el Administrador de cumplimiento actualiza automáticamente la puntuación de acción de mejora una vez que la acción se ha implementado y probado correctamente. Otras acciones&mdash;de control no técnico, como las que son operativas o relacionadas con la documentación&mdash;, deben registrarse manualmente como implementadas antes de que los puntos cuenten para la puntuación.

Muchos también están implementando ciertas acciones de mejora para otros fines&mdash;, por ejemplo, usar etiquetas de retención por razones distintas del cumplimiento de&mdash;la normativa de privacidad de datos, por lo que obtendría crédito para usar dicha característica incluso si se usa para otros fines y no forma parte de una acción deliberada de cumplimiento.

La puntuación de cumplimiento debe considerarse una medida relativa para realizar un seguimiento de la mejora a gran escala. No deberías buscar una puntuación perfecta.

## <a name="additional-guidance"></a>Instrucciones adicionales

Estas son algunas sugerencias importantes para usar el Administrador de cumplimiento para ayudarle a lograr el cumplimiento de la normativa de privacidad de datos:

- Cada reglamento de privacidad de datos tiene una combinación de controles técnicos, especificaciones de documentación y requisitos operativos, de procesos e informes. Todas estas se muestran en las acciones de mejora.

- Para centrar la vista de las acciones de mejora en su área de interés, puede filtrar por tipo de acción en la pestaña **Soluciones** del administrador de cumplimiento. Obtenga más información sobre [el filtrado de la vista del panel del Administrador de cumplimiento](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).

- La importancia relativa y la prioridad de las acciones de mejora identificadas en el Administrador de cumplimiento deben considerarse como parte de una revisión de riesgos más amplia junto con el riesgo de privacidad de datos que ha determinado que su organización necesita administrar.

- Incluso con la agregación de acciones de mejora en varios requisitos normativos, si se seleccionan las plantillas de evaluación de regulación para RGPD, LGPD, CCPA e HIPAA-HITECH, por ejemplo, casi 400 acciones de mejora aparecerán en el Administrador de cumplimiento. Para abordar mejor esta lista larga, use el filtro de acción de mejora para reducir el conjunto de resultados a una lista más fácil de administrar.

- El filtro Categorías proporciona un medio para filtrar las acciones de mejora mediante la agrupación lógica, a la que se alinean los artículos Seguimiento, Impedir, Proteger, Conservar e Investigar de esta solución general.

- Algunos de los controles enumerados en las acciones de mejora pueden considerarse más directamente vinculados a un artículo normativo específico, mientras que otros controles pueden estar más asociados indirectamente con el espíritu de un reglamento y muchas veces son simplemente actividades recomendadas o procedimientos recomendados.