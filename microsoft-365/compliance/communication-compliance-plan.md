---
title: Planear el cumplimiento de las comunicaciones
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
ms.openlocfilehash: 4c44610f4d74fe9ebf3c8e549692d9cc7cc6cb34
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597427"
---
# <a name="plan-for-communication-compliance"></a>Planear el cumplimiento de las comunicaciones

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

Seleccione las partes interesadas dedicadas para supervisar y revisar las alertas y los casos en una cadencia regular en el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/). Asegúrese de comprender cómo asignará diferentes roles de cumplimiento de comunicaciones a las partes interesadas de su organización.

En función de cómo desee administrar las directivas y alertas de comunicación, tendrá que crear uno o más grupos de roles nuevos para los administradores, revisores e investigadores. Tiene la opción de asignar usuarios a grupos de roles específicos para administrar distintos conjuntos de características de cumplimiento de comunicaciones. O bien, puede decidir crear un grupo de roles y asignar todos los roles de cumplimiento de comunicaciones al grupo. Cree un solo grupo de roles o varios grupos para adecuarlos mejor a sus requisitos de administración de cumplimiento.

Planee elegir entre estas opciones de rol al configurar los grupos de funciones de cumplimiento de la comunicación:

|**Rol**|**Permisos de funciones**|
|:-----|:-----|
| **Administrador de cumplimiento de comunicaciones** | Los usuarios que tienen asignado este rol pueden crear, leer, actualizar y eliminar las directivas de cumplimiento de la comunicación, la configuración global y las asignaciones del grupo de roles. Los usuarios asignados a esta función no pueden ver los mensajes de alerta. |
| **Análisis de cumplimiento de comunicaciones** | Los usuarios que tienen asignado este rol pueden ver las directivas en las que se asignan como revisores, ver los metadatos de los mensajes (no el contenido del mensaje), remitir a otros revisores o enviar notificaciones a los usuarios. Los analistas no pueden resolver alertas pendientes. |
| **Investigación de cumplimiento en la comunicación** | Los usuarios que tienen asignado este rol pueden ver el contenido y los metadatos de los mensajes, escalar a revisores adicionales, escalar a un caso de exhibición de documentos electrónicos avanzado, enviar notificaciones a los usuarios y resolver la alerta. |
| **Visor de cumplimiento de comunicaciones** | Los usuarios a los que se les asigna esta función pueden tener acceso a todos los widgets de informes en la Página principal de cumplimiento de comunicaciones y pueden ver todos los informes de cumplimiento de comunicaciones. |
| **Administración de casos de cumplimiento de comunicaciones** | Los usuarios que tienen asignado este rol pueden administrar casos y actuar en alertas. Este rol es necesario para cuando se crean grupos de roles personalizados para administradores, analistas e investigadores. Los grupos personalizados para visores no necesitan esta función asignada. |

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
