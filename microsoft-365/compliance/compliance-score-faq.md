---
title: Preguntas más frecuentes sobre la calificación de cumplimiento de Microsoft (vista previa)
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
description: Encuentre respuestas a las preguntas más frecuentes sobre la puntuación de cumplimiento de Microsoft, que ayuda a las organizaciones a simplificar y automatizar las evaluaciones de riesgos.
ms.openlocfilehash: 6ba71620d689e6d028b61ff24f7c837337ef60c6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016205"
---
# <a name="compliance-score-preview-frequently-asked-questions"></a>Resultados de la puntuación de cumplimiento (versión preliminar) preguntas más frecuentes

## <a name="what-is-compliance-score"></a>¿Qué es la puntuación de cumplimiento?

La puntuación de cumplimiento de Microsoft es una característica de vista previa del [centro de cumplimiento de microsoft 365](microsoft-365-compliance-center.md) que le ayuda a comprender la postura de cumplimiento de la organización. Calcula una puntuación basada en riesgos que mide su progreso en la realización de acciones que ayudan a reducir los riesgos en torno a la protección de datos y los estándares normativos. La puntuación de cumplimiento proporciona una asignación de control integrada que ayuda a conectar controles comunes entre los estándares y las regulaciones clave. Esta asignación le permite realizar una acción para cumplir varios requisitos al mismo tiempo, lo que le ayuda a escalar el programa de cumplimiento.

## <a name="whats-new-in-the-preview-version-of-compliance-score"></a>¿Cuáles son las novedades de la versión preliminar de la puntuación de cumplimiento?

Visite las [notas](compliance-score-release-notes.md) de la versión de calificación de cumplimiento para obtener información sobre las actualizaciones de características y los problemas conocidos.

## <a name="how-do-i-access-compliance-score"></a>¿Cómo se obtiene acceso a la puntuación de cumplimiento?

Vaya al [centro de cumplimiento de microsoft 365](https://compliance.microsoft.com/) e **inicie sesión** con un rol de administrador global de Microsoft 365, administrador de cumplimiento o administración de datos de cumplimiento. Seleccione **puntuación de cumplimiento** en el panel de navegación izquierdo. A continuación, debería ver el [Panel de puntuación de cumplimiento con su puntuación](compliance-score-setup.md#understand-the-compliance-score-dashboard). Si no tiene el acceso adecuado a la función, el administrador global de su organización puede concederle permiso.

## <a name="what-roles-or-permissions-are-needed-to-use-compliance-score"></a>¿Qué roles o permisos se necesitan para usar la puntuación de cumplimiento?

La puntuación de cumplimiento usa un modelo de permisos de control de acceso basado en roles (RBAC). Las acciones que puede realizar dependen del tipo de rol que se le haya asignado. El administrador global de Microsoft 365 de su organización es la persona que puede realizar las funciones de configuración y administrar roles en puntuación de cumplimiento. Como mínimo, los usuarios necesitan la función **lector global de Azure ad** para leer datos con la puntuación de cumplimiento. Obtenga más información sobre los permisos, los roles y los procedimientos de configuración en la configuración de la [puntuación de cumplimiento](compliance-score-setup.md).

## <a name="what-is-the-difference-between-compliance-score-and-compliance-manager"></a>¿Cuál es la diferencia entre el administrador de cumplimiento y la puntuación de cumplimiento?

La puntuación de cumplimiento y el administrador de cumplimiento comparten el mismo back-end. Todo lo que haga en una herramienta se mostrará en la otra herramienta. Residen en dos ubicaciones distintas: la puntuación de cumplimiento se encuentra en el centro de cumplimiento de Microsoft 365 y el administrador de cumplimiento se encuentra en el portal de confianza de servicios de Microsoft. Piense en la puntuación de cumplimiento como una versión simplificada del administrador de cumplimiento, que le ofrece una vista más completa de la postura de cumplimiento actual de su organización y los pasos que puede realizar para mejorarla.

Aunque puede realizar varias acciones directamente en cuanto a la puntuación de cumplimiento, algunas funciones residen en el administrador de cumplimiento durante la versión preliminar pública. Obtenga más información acerca de la [relación entre la puntuación de cumplimiento y el administrador de cumplimiento](compliance-score.md#relationship-to-compliance-manager).

Obtener acceso al [Administrador de cumplimiento en el portal de confianza de servicios de Microsoft](https://servicetrust.microsoft.com/ComplianceManager/V3). Asegúrese de **seleccionar el administrador de cumplimiento** en el menú desplegable de navegación superior, que tiene las características más actuales y no con el administrador de *cumplimiento (clásico)*, que contiene las características de la versión preliminar.

## <a name="should-i-use-compliance-score-or-compliance-manager"></a>¿Debo usar la puntuación de cumplimiento o el administrador de cumplimiento?

La puntuación de cumplimiento es útil para todos los usuarios de la organización que desempeñan un papel en cumplimiento. Con la puntuación de cumplimiento, no es necesario estar familiarizado con las regulaciones y los estándares para ayudar a mejorar la protección de datos de su organización. La puntuación de cumplimiento es el punto de partida óptimo para todos los usuarios. Desde aquí, puede ver la puntuación de cumplimiento, saber qué acciones recomendadas pueden ayudar a minimizar los riesgos y administrar las evaluaciones.

Por ahora, el administrador de cumplimiento es el lugar donde puede crear plantillas personalizadas para compilar evaluaciones. Obtenga más información sobre [qué acciones solo admite el administrador de cumplimiento durante la](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager) versión preliminar pública.

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>Si tengo una puntuación alta, ¿significa que estoy completamente conforme?

No. La puntuación de cumplimiento mide su progreso en la finalización de las acciones recomendadas que ayudan a reducir los riesgos alrededor de la protección de datos y los estándares normativos. No se expresa una medida absoluta de cumplimiento organizacional con cualquier norma o reglamentación en particular. La puntuación de cumplimiento no debe interpretarse como una garantía de ningún modo.

## <a name="what-regulations-and-standards-does-compliance-score-monitor"></a>¿Qué normativas y estándares realiza el monitor de puntuación de cumplimiento?

La puntuación de cumplimiento proporciona una puntuación inicial basada en la línea base de protección de datos 365 de Microsoft, que es un conjunto de controles que incluye normas y estándares comunes de la industria. Esta base dibuja los elementos principalmente desde NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Normalization), así como de FedRAMP (programa federal de administración de riesgos y autorización) y RGPD (norma general de protección de datos de la Unión Europea).

Las organizaciones pueden crear y agregar evaluaciones personalizadas que sean más relevantes para su organización. Use una de las puntuaciones de cumplimiento listas para usar [plantillas](compliance-score-templates.md), personalice una plantilla de Microsoft con sus propios controles y acciones, o cree su propia plantilla. Lea detalles sobre cómo [trabajar con evaluaciones y plantillas](compliance-score-assessments.md).

## <a name="how-does-compliance-score-continuously-assess-my-environment"></a>¿Cómo evalúa continuamente mi entorno la puntuación de cumplimiento?

La puntuación de cumplimiento examina automáticamente el entorno y usa la puntuación segura para detectar la configuración del sistema. Obtenga más información sobre la [evaluación continua](compliance-score-methodology.md#how-compliance-score-continuously-assesses-controls).

## <a name="what-is-the-difference-between-compliance-score-and-secure-score"></a>¿Cuál es la diferencia entre la puntuación de cumplimiento y la puntuación segura?

La puntuación de cumplimiento proporciona una vista amplia de la postura de cumplimiento y protección de datos de la organización. La puntuación de cumplimiento también proporciona herramientas de flujo de trabajo integradas; permite a las organizaciones asignar trabajo a los usuarios, realizar un seguimiento de la implementación del control y el estado de las pruebas, y cargar pruebas y crear informes de auditoría.

La calificación segura de Microsoft es una herramienta de análisis de seguridad para ayudarle a comprender su postura de seguridad. [Obtenga más información sobre la puntuación segura y cómo funciona](../security/mtp/microsoft-secure-score-new.md).

## <a name="which-cloud-services-are-covered-by-compliance-score"></a>¿Qué servicios en la nube están cubiertos por la puntuación de cumplimiento?

La puntuación de cumplimiento proporciona actualmente evaluaciones para Office 365 e Intune. Se espera una cobertura ampliada en versiones futuras, que se indicará en las notas de la [versión de puntuación de cumplimiento](compliance-score-release-notes.md).

## <a name="can-i-use-compliance-score-for-non-microsoft-products"></a>¿Puedo usar la puntuación de cumplimiento para productos que no son de Microsoft?

Mientras que la puntuación de cumplimiento proporciona supervisión continua y acciones recomendadas solo para los servicios en la nube de Microsoft, puede Agregar evaluaciones personalizadas en el administrador de cumplimiento para los servicios de terceros locales. De esta forma, puede usar la puntuación de cumplimiento de Microsoft como herramienta de administración de cumplimiento de SaaS para ayudarle a administrar todos los controles de los activos digitales.

Puede usar una puntuación de cumplimiento preparada para usar [plantillas](compliance-score-templates.md) para crear evaluaciones para estándares concretos o [crear su propia plantilla](working-with-compliance-manager.md#create-a-template), que deberá realizar en el administrador de cumplimiento.

## <a name="how-do-i-delete-a-template-or-assessment-i-no-longer-need"></a>¿Cómo elimino una plantilla o una evaluación que ya no necesito?

Para eliminar una evaluación, abra la evaluación que desea eliminar y seleccione **eliminar evaluación**. Tenga en cuenta que la eliminación de una evaluación es permanente. Permite ver más detalles sobre cómo [eliminar evaluaciones](compliance-score-assessments.md#delete-an-assessment). La eliminación de una evaluación no elimina su plantilla. Las plantillas no se pueden eliminar, pero pueden ocultarse de la vista. Revise [las instrucciones para ocultar plantillas](working-with-compliance-manager.md#hide-a-template-or-an-assessment).

## <a name="what-test-procedures-does-microsoft-follow-for-controls"></a>¿Qué procedimientos de prueba sigue Microsoft para los controles?

Microsoft participa en auditorías anuales de controles. Puede revisar los informes de auditoría de nuestros auditores, que están disponibles para su descarga desde el [portal de confianza de servicios de Microsoft](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3).

## <a name="why-are-some-controls-tested-annually-and-others-tested-every-three-years"></a>¿Por qué algunos controles se han probado anualmente y otros se han probado cada tres años?

La evaluación de FedRAMP es un ejemplo de por qué podría ser el caso. Se lleva a cabo cada año y prueba una sección de controles entre las familias de control principales. FedRAMP clasifica los controles como **principales** cuando son lo suficientemente importantes como para requerir una prueba anual. Los controles designados como no básicos se prueban cada tres años. Un subconjunto de controles que abarcan todas las familias de controles principales se prueban anualmente. De este modo, cada auditoría anual examina los escenarios en todo el panel para garantizar que la solución es sólida. Obtenga más información sobre el [proceso de evaluación anual de FedRAMP](https://www.fedramp.gov/annual-assessment-guidance/).
