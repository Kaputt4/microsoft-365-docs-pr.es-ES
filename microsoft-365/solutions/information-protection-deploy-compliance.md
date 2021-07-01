---
title: Usar el Administrador de cumplimiento para administrar acciones de mejora
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
description: Obtenga información sobre cómo usar el Administrador de cumplimiento y puntuación de cumplimiento para mejorar el nivel de protección de los datos personales.
ms.openlocfilehash: 26e9f54ce77869f4f6ef07c18147483628ddc223
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229304"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Usar el Administrador de cumplimiento para administrar acciones de mejora

El Administrador de cumplimiento de Microsoft puede ayudarle a administrar mejoras relacionadas con las normativas de privacidad de datos, como el Reglamento general de protección de datos [(RGPD)](/compliance/regulatory/gdpr)de la Unión Europea, la Ley de protección de consumidores de [California CCPA),](/compliance/regulatory/ccpa-faq)hipaa-hitech (ley de privacidad del cuidado de la salud de Estados Unidos) y la Ley de protección de datos de Brasil (LGPD).

En este artículo se proporcionan instrucciones sobre el uso de esta herramienta con fines de privacidad de datos.

> [!NOTE]
> Las recomendaciones del Administrador de cumplimiento no deberán interpretarse como una garantía de cumplimiento. Debe evaluar y validar la eficacia de los controles de los clientes según su entorno normativo. Estos servicios están sujetos a los términos y condiciones de los Términos [de servicios en línea](https://go.microsoft.com/fwlink/?linkid=2108910). Vea también Microsoft 365 [de licencias para seguridad y cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

## <a name="getting-started-with-compliance-manager"></a>Introducción al Administrador de cumplimiento

#### <a name="what-is-compliance-manager"></a>Qué es el Administrador de cumplimiento

[Compliance Manager](../compliance/compliance-manager.md) es una herramienta de evaluación de riesgos basada en flujos de trabajo en el Centro de cumplimiento de Microsoft 365 para administrar actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft. Como parte de la suscripción Microsoft 365 o Azure Active Directory (Azure AD), el Administrador de cumplimiento le ayuda a administrar el cumplimiento normativo dentro del modelo de responsabilidad compartida para los servicios en la nube de Microsoft.

**Evaluaciones listas para usar**

El Administrador de cumplimiento proporciona plantillas predefinidas para crear evaluaciones alineadas con las [normativas](../compliance/compliance-manager-assessments.md) relacionadas con la privacidad de datos, como RGPD e HIPAA/HITECH. Las plantillas tienen asignación de control integrada para ayudarle a tomar medidas de mejora para cumplir los requisitos del reglamento. Cada evaluación proporciona información sobre los controles que cada reglamento llama para específicos del servicio de destino, desglosados por los controles que administra y los controles que administra Microsoft.

El uso de una plantilla predefinida le ayuda a empezar rápidamente con las evaluaciones de riesgos. A medida que sea más competente en el uso del Administrador de cumplimiento, puede personalizar una plantilla predefinida agregando sus propios controles y acciones de mejora, o puede crear sus propias evaluaciones personalizadas para satisfacer las necesidades de su organización.

Vea la [lista completa de plantillas de evaluación proporcionadas](../compliance/compliance-manager-templates-list.md) por el Administrador de cumplimiento.

**Puntuación de cumplimiento en tiempo real**

El Administrador de cumplimiento también le proporciona una puntuación de cumplimiento que mide su progreso en la realización de acciones de mejora recomendadas dentro de los controles. Puedes usar esta puntuación para ayudar a supervisar el progreso y priorizar las acciones en función de su potencial para reducir el riesgo.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>Usar la guía de inicio rápido del Administrador de cumplimiento

La [guía de inicio rápido del Administrador](../compliance/compliance-manager-quickstart.md) de cumplimiento proporciona pasos graduados y vínculos a recursos clave para ayudarle a trabajar con el Administrador de cumplimiento:

- [Primera visita: familiarizarse con el Administrador de cumplimiento](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Trabajar con el panel del Administrador de cumplimiento
    - Descripción de la puntuación de cumplimiento
    - Learning sobre acciones de mejora
    - Descripción de evaluaciones y plantillas
- [Aceleración: configurar el Administrador de cumplimiento para administrar las actividades de cumplimiento](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Crear y administrar la primera evaluación
    - Realizar trabajos de implementación y pruebas en acciones de mejora para completar controles en las evaluaciones
    - Comprender cómo afectan las distintas acciones a la puntuación de cumplimiento
- [Escalado vertical: use la funcionalidad avanzada para satisfacer sus necesidades personalizadas](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Creación de evaluaciones personalizadas para realizar un seguimiento de productos que no Microsoft 365 datos
    - Modificación de plantillas existentes para agregar o quitar controles
    - Configuración de pruebas automatizadas de acciones de mejora

## <a name="how-your-compliance-score-is-calculated"></a>Cómo se calcula su puntuación de cumplimiento

La puntuación de cumplimiento se calcula en función de una combinación de implementaciones de control administradas por el cliente y Microsoft. Vea [cálculo de puntuación de cumplimiento](../compliance/compliance-score-calculation.md) para obtener una explicación detallada.

A los controles se les asigna un valor de puntuación en función de si son obligatorios o discrecionales, y si son preventivos, detectives o correctivos. Estos representan colectivamente el riesgo de no implementarlo en relación con otros controles.

Como se muestra en el artículo de cálculo de puntuación de cumplimiento, los controles preventivos obtienen una puntuación mayor que los de detective y correctivo, y los controles obligatorios obtienen una puntuación mayor que los discrecionales.

La interfaz de usuario de administrador de puntuación de cumplimiento no enumera estos parámetros ni proporciona la capacidad de filtrar por ellos. Sin embargo, si descarga la plantilla asociada del Administrador de cumplimiento, el conjunto de datos resultante enumera estos parámetros para la mayoría de las regulaciones.

Para los controles técnicos, el Administrador de cumplimiento actualiza automáticamente la puntuación de acción de mejora una vez que la acción se ha implementado y probado correctamente. Otras acciones de control no técnicas, como las que están operativas o relacionadas con la documentación, deben registrarse manualmente como implementadas antes de que los puntos cuenten &mdash; &mdash; para su puntuación.

You many also be implementing certain improvement actions for other purposes for example using retention labels for reasons &mdash; other than data privacy regulation compliance so you would get credit for using such a feature even if &mdash; it is being used for other purposes, and not part of a deliberate compliance action.

La puntuación de cumplimiento debe considerarse una medida relativa para realizar un seguimiento de la mejora a gran escala. No debe buscar una puntuación perfecta.

## <a name="additional-guidance"></a>Instrucciones adicionales

Estos son algunos consejos importantes para usar el Administrador de cumplimiento para ayudarle a lograr el cumplimiento de la normativa de privacidad de datos:

- Cada reglamento de privacidad de datos tiene una combinación de controles técnicos, especificaciones de documentación y requisitos operativos, de proceso e informes. Todas estas acciones se muestran en las acciones de mejora.

- Para centrar la vista de las acciones de mejora en su  área de interés, puede filtrar por tipo de acción en la pestaña Soluciones en el administrador del Administrador de cumplimiento. Obtenga más información sobre [cómo filtrar la vista de panel del Administrador de cumplimiento.](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)

- La importancia relativa y la prioridad de las acciones de mejora identificadas en el Administrador de cumplimiento deben considerarse como parte de una revisión de riesgos más amplia junto con el riesgo de privacidad de datos que ha determinado que su organización debe administrar.

- Incluso con la agregación de acciones de mejora en varios requisitos normativos, si se seleccionan las plantillas de evaluación de normativas para RGPD, LGPD, CCPA y HIPAA-HITECH, por ejemplo, se mostrarán casi 400 acciones de mejora en el Administrador de cumplimiento. Para abordar mejor esta lista larga, use el filtro de acción de mejora para reducir el conjunto de resultados a una lista más manejable.

- El filtro Categorías proporciona un medio para filtrar acciones de mejora por agrupación lógica, a las que se alinean los artículos Track, Prevent, Protect, Retain e Investigate de esta solución general.

- Algunos de los controles enumerados en las acciones de mejora pueden considerarse más directamente vinculados a un artículo normativo específico, mientras que otros controles pueden asociarse más indirectamente con el ánimo de un reglamento y muchas veces son simplemente actividades recomendadas o procedimientos recomendados.