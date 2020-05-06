---
title: Planeación del cumplimiento de la comunicación
description: Obtenga información sobre la planeación para usar el cumplimiento de la comunicación en su organización.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 214c5376d4c074525253707e181eee69cefff85e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045859"
---
# <a name="plan-for-communication-compliance"></a>Planeación del cumplimiento de la comunicación

Antes de empezar a trabajar con el cumplimiento de la [comunicación](communication-compliance.md) en su organización, existen importantes actividades y consideraciones de planificación que deben ser revisadas por los equipos de la tecnología de la información y el cumplimiento normativo. La comprensión y planeación exhaustiva de la implementación en las siguientes áreas le ayudarán a garantizar que la implementación y el uso de las características de cumplimiento de comunicaciones se ajustan correctamente a los procedimientos recomendados para la solución.

## <a name="work-with-stakeholders-in-your-organization"></a>Trabajar con las partes interesadas de la organización

Identificar las partes interesadas adecuadas de la organización para colaborar para emprender acciones sobre las alertas de cumplimiento de comunicaciones. Algunas partes interesadas recomendadas que se deben considerar incluir en la planeación inicial y el [flujo de trabajo de cumplimiento de comunicaciones](communication-compliance.md#workflow) de un extremo a otro son personas de las siguientes áreas de la organización:

- Tecnología de la información
- Cumplimiento
- Privacidad
- Seguridad
- Recursos humanos
- Legal

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Planeación del flujo de trabajo de investigación y corrección

Seleccione revisores dedicados para supervisar y revisar las alertas con una cadencia regular en el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/). Recuerde que tendrá que [crear un nuevo grupo de roles](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) para habilitar los permisos para revisores con el **Administrador de revisión de supervisión**, la administración de **casos**, el **Administrador de cumplimiento**y la **revisión** de roles para investigar y corregir mensajes con coincidencias de directivas.

## <a name="plan-for-policies"></a>Planeación de directivas

La creación de directivas de cumplimiento de la comunicación es rápida y sencilla con las [plantillas predefinidas](communication-compliance-feature-reference.md#policy-templates) para el lenguaje ofensivo, la información confidencial y el cumplimiento normativo. Las directivas de cumplimiento de comunicaciones personalizadas permiten la flexibilidad para detectar e investigar problemas específicos de la organización y los requisitos.

Al planear las directivas de cumplimiento de comunicaciones, tenga en cuenta lo siguiente:

- Considere la posibilidad de agregar todos los usuarios de su organización como en el ámbito de las directivas de cumplimiento de la comunicación. La identificación de usuarios específicos como en el ámbito de las directivas individuales resulta útil en algunas circunstancias, pero la mayoría de las organizaciones deben incluir a todos los usuarios en las directivas de cumplimiento de comunicaciones optimizadas para la detección de acoso o discriminación.
- Para simplificar la configuración, considere la posibilidad de crear grupos para los usuarios que necesitan sus comunicaciones revisadas. Si está usando grupos; es posible que necesite varias. Por ejemplo, si desea examinar las comunicaciones entre dos grupos de personas distintos, o si desea especificar un grupo que no está supervisado.
- Configure el porcentaje de comunicaciones que se van a revisar al 100% para asegurarse de que las directivas detectan todas las cuestiones de preocupación en las comunicaciones de la organización.
- Puede examinar las comunicaciones de [orígenes de terceros](communication-compliance-feature-reference.md#supported-communication-types) para los datos importados en buzones de la organización de Microsoft 365. Para incluir la revisión de comunicaciones en estas plataformas, deberá configurar un conector para estos servicios antes de que las condiciones de la Directiva de reunión de los mensajes se supervisan mediante una directiva de comunicación.
- Las directivas pueden admitir idiomas de supervisión distintos del inglés en las directivas de cumplimiento de comunicaciones personalizadas. Cree un [Diccionario de palabras clave personalizadas](communication-compliance-feature-reference.md#custom-keyword-dictionaries) con palabras ofensivas en el idioma de su elección o cree su propio modelo de aprendizaje de la máquina mediante [clasificadores capacitados](classifier-getting-started-with.md) en Microsoft 365.
- Todas las organizaciones tienen diferentes normas de comunicación y necesidades de directivas. Supervisar palabras clave específicas usando [las condiciones](communication-compliance-feature-reference.md#conditional-settings) de la Directiva de cumplimiento de comunicaciones o monitor para tipos específicos de información con [tipos personalizados de información confidencial](create-a-custom-sensitive-information-type.md).

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Para configurar el cumplimiento de comunicaciones para su organización de Microsoft 365, vea [Configure Communication Compliance for Microsoft 365](communication-compliance-configure.md) o consulte el [caso práctico de Contoso](communication-compliance-case-study.md) y cómo se configuró rápidamente una directiva de cumplimiento de comunicaciones para supervisar el idioma ofensivo en Microsoft Teams, Exchange Online y las comunicaciones de Yammer.
