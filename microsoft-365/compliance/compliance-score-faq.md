---
title: Preguntas frecuentes sobre la puntuación de cumplimiento de Microsoft
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
ms.openlocfilehash: 9a71abba7b38bcf1e39073133f82abaedfc0d270
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078647"
---
# <a name="microsoft-compliance-score-preview-frequently-asked-questions"></a>Preguntas más frecuentes sobre la puntuación de cumplimiento de Microsoft (versión preliminar)

## <a name="what-is-compliance-score"></a>¿Qué es la puntuación de cumplimiento?

La puntuación de cumplimiento de Microsoft es una característica de vista previa del [centro de cumplimiento de microsoft 365](microsoft-365-compliance-center.md) que le ayuda a comprender la postura de cumplimiento de la organización. Calcula una puntuación basada en riesgos que mide su progreso en la realización de acciones que ayudan a reducir los riesgos en torno a la protección de datos y los estándares normativos. También proporciona una asignación de control integrada que ayuda a conectar controles comunes entre estándares y normativas clave, de modo que pueda realizar una acción para cumplir con varios requisitos al mismo tiempo y mejorar la escala del programa de cumplimiento.

## <a name="how-do-i-access-compliance-score"></a>¿Cómo se obtiene acceso a la puntuación de cumplimiento?

Vaya al [centro de cumplimiento de microsoft 365](https://compliance.microsoft.com/) e **inicie sesión** con un rol de administrador global de Microsoft 365, administrador de cumplimiento o administración de datos de cumplimiento. Seleccione **puntuación de cumplimiento** en el panel de navegación izquierdo. A continuación, debería ver el [Panel de puntuación de cumplimiento con su puntuación](compliance-score-setup.md#understand-the-compliance-score-dashboard). Si no tiene el acceso adecuado a la función, el administrador global de su organización puede concederle permiso.

## <a name="what-roles-or-permissions-are-needed-to-use-compliance-score"></a>¿Qué roles o permisos se necesitan para usar la puntuación de cumplimiento?

La puntuación de cumplimiento usa un modelo de permisos de control de acceso basado en roles (RBAC) y las acciones que puede realizar dependen del tipo de rol que se le haya asignado. El administrador global de Microsoft 365 de su organización es la persona que puede realizar las funciones de configuración y administrar roles en puntuación de cumplimiento. Como mínimo, los usuarios necesitan la función **lector global de Azure ad** para leer datos con la puntuación de cumplimiento. Obtenga más información sobre los permisos, los roles y los procedimientos de configuración en la configuración de la [puntuación de cumplimiento](compliance-score-setup.md).

## <a name="what-is-the-difference-between-compliance-score-and-compliance-manager"></a>¿Cuál es la diferencia entre el administrador de cumplimiento y la puntuación de cumplimiento?

La puntuación de cumplimiento y el administrador de cumplimiento comparten el mismo servidor, pero se encuentran en dos ubicaciones diferentes (la puntuación de cumplimiento se encuentra en el centro de cumplimiento de Microsoft 365 y el administrador de cumplimiento se encuentra en el portal de confianza de servicios de Microsoft). Piense en la puntuación de cumplimiento como una versión simplificada del administrador de cumplimiento, que le ofrece una vista más completa de la postura de cumplimiento actual de su organización y los pasos que puede realizar para mejorarla. Aunque puede realizar muchas acciones directamente en cuanto a la puntuación de cumplimiento, algunas funcionalidades residen en el administrador de cumplimiento por ahora. Obtenga más información acerca de la [relación entre la puntuación de cumplimiento y el administrador de cumplimiento](compliance-score.md#relationship-to-compliance-manager).

## <a name="who-should-use-compliance-score-and-who-should-use-compliance-manager"></a>¿Quién debe usar la puntuación de cumplimiento y quién debe usar el administrador de cumplimiento?

La puntuación de cumplimiento es útil para todos los usuarios de la organización que desempeñan un papel en la supervisión del cumplimiento y la realización de actividades para cumplir con los estándares normativos. Con la puntuación de cumplimiento, no es necesario estar familiarizado con las regulaciones y los estándares para ayudar a mejorar la protección de datos de su organización. La puntuación de cumplimiento es el punto de partida óptimo para todos los usuarios. Desde aquí, puede ver la puntuación de cumplimiento, saber qué acciones recomendadas pueden ayudar a minimizar los riesgos y, en muchos casos, iniciar directamente en las soluciones para llevar a cabo esas acciones.

Por ahora, el administrador de cumplimiento es el lugar en el que los usuarios pueden administrar las evaluaciones y crear plantillas personalizadas para compilar evaluaciones. Obtenga más información sobre [qué acciones solo admite el administrador de cumplimiento durante la](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager) versión preliminar pública.

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>Si tengo una puntuación alta, ¿significa que estoy completamente conforme?

No. La puntuación de cumplimiento mide su progreso en la finalización de las acciones recomendadas que ayudan a reducir los riesgos alrededor de la protección de datos y los estándares normativos. No se expresa una medida absoluta de cumplimiento organizacional con cualquier norma o reglamentación en particular. La puntuación de cumplimiento no debe interpretarse como una garantía de ningún modo.

## <a name="what-regulations-and-standards-does-compliance-score-monitor"></a>¿Qué normativas y estándares realiza el monitor de puntuación de cumplimiento?

La puntuación de cumplimiento proporciona una puntuación inicial basada en la línea base de protección de datos 365 de Microsoft, que es un conjunto de controles que incluye normas y estándares comunes de la industria. Esta línea base dibuja los elementos principalmente desde NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Normalization), así como de FedRAMP (federal Risk and Authorization Management Programa) y RGPD (regla general de protección de datos de la Unión Europea).

Las organizaciones pueden crear y agregar evaluaciones personalizadas que sean más relevantes para su organización. Puede usar una de [las plantillas de la](compliance-score.md#templates) puntuación de cumplimiento para crear evaluaciones para estándares concretos, o bien [crear su propia plantilla](working-with-compliance-manager.md#create-a-template-1).

Obtenga más información sobre [cómo la puntuación de cumplimiento calcula la puntuación](compliance-score-methodology.md).

## <a name="what-is-the-difference-between-compliance-score-and-secure-score"></a>¿Cuál es la diferencia entre la puntuación de cumplimiento y la puntuación segura?

La puntuación de cumplimiento proporciona una vista amplia de la postura de cumplimiento y protección de datos de la organización. La puntuación de cumplimiento también proporciona herramientas de flujo de trabajo integradas; permite a las organizaciones asignar trabajo a los usuarios, realizar un seguimiento de la implementación del control y el estado de las pruebas, y cargar pruebas y crear informes de auditoría.

La calificación segura de Microsoft es una herramienta de análisis de seguridad para ayudarle a comprender su postura de seguridad. [Obtenga más información sobre la puntuación segura y cómo funciona](../security/mtp/microsoft-secure-score.md).

## <a name="which-cloud-services-are-covered-by-compliance-score"></a>¿Qué servicios en la nube están cubiertos por la puntuación de cumplimiento?

La puntuación de cumplimiento proporciona actualmente evaluaciones para Office 365 e Intune. Se espera una cobertura ampliada en versiones futuras, que se indicará en las notas de la [versión de puntuación de cumplimiento](compliance-score-release-notes.md).

## <a name="can-i-use-compliance-score-for-non-microsoft-products"></a>¿Puedo usar la puntuación de cumplimiento para productos que no son de Microsoft?

Mientras que la puntuación de cumplimiento proporciona supervisión continua y acciones recomendadas solo para los servicios en la nube de Microsoft, puede Agregar evaluaciones personalizadas en el administrador de cumplimiento para los servicios de terceros locales. De esta forma, puede usar la puntuación de cumplimiento de Microsoft como herramienta de administración de cumplimiento de SaaS para ayudarle a administrar todos los controles de los activos digitales.

Puede usar una de [las plantillas de la](compliance-score.md#templates) puntuación de cumplimiento para crear evaluaciones para estándares concretos, o bien [crear su propia plantilla](working-with-compliance-manager.md#create-a-template-1).

## <a name="how-do-i-delete-a-template-or-assessment-i-no-longer-need"></a>¿Cómo elimino una plantilla o una evaluación que ya no necesito?

No puede eliminar una evaluación o plantilla, pero sí puede ocultarlas en la vista. Revise las [instrucciones para ocultar evaluaciones](working-with-compliance-manager.md#hide-a-template-or-an-assessment).
