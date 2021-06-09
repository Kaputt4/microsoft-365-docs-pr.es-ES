---
title: Planear el cumplimiento de las comunicaciones
description: Obtenga información sobre cómo planear el uso del cumplimiento de comunicaciones en su organización.
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
ms.openlocfilehash: d64edc9d80722080db18c45127bfc82110d1ea9e
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131542"
---
# <a name="plan-for-communication-compliance"></a>Planear el cumplimiento de las comunicaciones

Antes de empezar con el cumplimiento [de](communication-compliance.md) las comunicaciones en su organización, hay importantes actividades de planeación y consideraciones que deben revisar los equipos de administración de tecnología de la información y cumplimiento. El conocimiento exhaustivo y la planeación de la implementación en las siguientes áreas ayudarán a garantizar que la implementación y el uso de las características de cumplimiento de comunicaciones se adapten a los procedimientos recomendados para la solución.

## <a name="work-with-stakeholders-in-your-organization"></a>Trabajar con las partes interesadas de la organización

Identifique a las partes interesadas apropiadas de su organización para colaborar en la toma de acciones en las alertas de cumplimiento de comunicaciones. Algunas partes interesadas recomendadas que deben considerar incluir [](communication-compliance.md#workflow) en la planeación inicial y el flujo de trabajo de cumplimiento de comunicaciones de extremo a extremo son personas de las siguientes áreas de su organización:

- Tecnología de la información
- Cumplimiento
- Privacidad
- Seguridad
- Recursos humanos
- Legal

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Planear el flujo de trabajo de investigación y corrección

Seleccione partes interesadas dedicadas para supervisar y revisar las alertas y los casos en una cadencia regular en el centro de Microsoft 365 [cumplimiento.](https://compliance.microsoft.com/) Asegúrese de comprender cómo asignará usuarios y partes interesadas a diferentes grupos de roles de cumplimiento de comunicaciones de su organización.

Dependiendo de cómo desee administrar las directivas de comunicación y las alertas, deberá asignar usuarios a uno o varios grupos de roles para administradores, revisores e investigadores. Tiene la opción de asignar usuarios a grupos de roles específicos para administrar diferentes conjuntos de características de cumplimiento de comunicación. O puede decidir asignar todos los usuarios de cumplimiento de comunicación al grupo de roles Cumplimiento de comunicación. Use un único grupo de roles o varios grupos para ajustarse mejor a sus requisitos de administración de cumplimiento.

Planee elegir entre estas opciones de grupo de roles al configurar el cumplimiento de la comunicación:

|**Rol**|**Permisos de funciones**|
|:-----|:-----|
| **Cumplimiento de comunicaciones** | Use este grupo de roles para administrar el cumplimiento de comunicaciones de su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores designados, analistas, investigadores y visores, puede configurar los permisos de cumplimiento de comunicaciones en un solo grupo. Este grupo de funciones contiene todos los roles de permisos de cumplimiento de comunicación. Esta configuración es la forma más sencilla de empezar rápidamente con el cumplimiento de las comunicaciones y es una buena opción para las organizaciones que no necesitan permisos independientes definidos para grupos independientes de usuarios. |
| **Administrador de cumplimiento de comunicaciones** | Use este grupo de roles para configurar inicialmente el cumplimiento de las comunicaciones y posteriormente para segregar a los administradores de cumplimiento de comunicaciones en un grupo definido. Los usuarios asignados a este grupo de roles pueden crear, leer, actualizar y eliminar directivas de cumplimiento de comunicación, configuración global y asignaciones de grupos de roles. Los usuarios asignados a este grupo de roles no pueden ver alertas de mensajes. |
| **Analista de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver directivas en las que se les asigna como revisores, ver metadatos de mensajes (no contenido del mensaje), escalar a revisores adicionales o enviar notificaciones a los usuarios. Los analistas no pueden resolver alertas pendientes. |
| **Investigador de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver los metadatos y el contenido de los mensajes, escalar a revisores adicionales, escalar a un caso Advanced eDiscovery, enviar notificaciones a los usuarios y resolver la alerta. |
| **Visor de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que administrarán informes de comunicación. Los usuarios asignados a este grupo de roles pueden tener acceso a todos los widgets de informes de la página principal de cumplimiento de comunicaciones y pueden ver todos los informes de cumplimiento de comunicaciones. |

## <a name="plan-for-policies"></a>Planeación de directivas

La creación de directivas de cumplimiento de comunicaciones es rápida y fácil con las plantillas [predefinidas](communication-compliance-feature-reference.md#policy-templates) para el lenguaje ofensivo, la información confidencial y el cumplimiento normativo. Las directivas de cumplimiento de comunicaciones personalizadas permiten la flexibilidad para detectar e investigar problemas específicos de la organización y los requisitos.

Al planear las directivas de cumplimiento de comunicaciones, tenga en cuenta las siguientes áreas:

- Considere la posibilidad de agregar todos los usuarios de la organización como en el ámbito de las directivas de cumplimiento de comunicación. La identificación de usuarios específicos como en el ámbito de las directivas individuales es útil en algunas circunstancias, pero la mayoría de las organizaciones deben incluir a todos los usuarios en directivas de cumplimiento de comunicaciones optimizadas para la detección de acoso o discriminación.
- Para simplificar la configuración, considere la posibilidad de crear grupos para las personas que necesitan revisar sus comunicaciones. Si usa grupos; es posible que necesite varios. Por ejemplo, si quiere examinar las comunicaciones entre dos grupos distintos de personas, o si desea especificar un grupo que no esté supervisado.
- Configure el porcentaje de comunicaciones que se revisará al 100 % para asegurarse de que las directivas están atando todos los problemas que preocupan en las comunicaciones de su organización.
- Puede examinar las comunicaciones de [orígenes de terceros en](communication-compliance-feature-reference.md#supported-communication-types) busca de datos importados en buzones de correo de su Microsoft 365 organización. Para incluir la revisión de las comunicaciones en estas plataformas, deberá configurar un conector para estos servicios antes de que la directiva de comunicación supervise los mensajes que cumplen las condiciones de la directiva.
- Las directivas pueden admitir la supervisión de idiomas distintos del inglés en directivas de cumplimiento de comunicaciones personalizadas. Crea un [diccionario de palabras](communication-compliance-feature-reference.md#custom-keyword-dictionaries) clave personalizado de palabras ofensivas en el idioma que prefieras o crea tu propio modelo de aprendizaje automático con clasificadores [capacitados](classifier-get-started-with.md) en Microsoft 365.
- Todas las organizaciones tienen diferentes estándares de comunicación y necesidades de directiva. Supervisar palabras clave específicas mediante condiciones de directiva de [cumplimiento](communication-compliance-feature-reference.md#conditional-settings) de comunicación o supervisar tipos específicos de información con tipos de información [confidencial personalizados.](create-a-custom-sensitive-information-type.md)

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Para configurar el cumplimiento de comunicaciones para su organización de [Microsoft 365,](communication-compliance-configure.md) vea Configure communication compliance for Microsoft 365 or check out the [case study for Contoso](communication-compliance-case-study.md) and how they quickly configured a communication compliance policy to monitor for offensive language in Microsoft Teams, Exchange Online, and Yammer communications.
