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

Antes de empezar [a](communication-compliance.md) trabajar con el cumplimiento de las comunicaciones en su organización, hay importantes actividades de planeación y consideraciones que deben revisar los equipos de administración de cumplimiento y tecnología de la información. Comprender y planear exhaustivamente la implementación en las siguientes áreas le ayudará a garantizar que la implementación y el uso de las características de cumplimiento de comunicaciones se adapten correctamente a los procedimientos recomendados para la solución.

## <a name="work-with-stakeholders-in-your-organization"></a>Trabajar con las partes interesadas de la organización

Identifique a las partes interesadas adecuadas de su organización para colaborar en la toma de medidas en las alertas de cumplimiento de comunicaciones. Algunas partes interesadas recomendadas que deben considerar incluir [](communication-compliance.md#workflow) en la planeación inicial y el flujo de trabajo de cumplimiento de comunicaciones de un extremo a otro son personas de las siguientes áreas de la organización:

- Tecnología de la información
- Cumplimiento
- Privacidad
- Seguridad
- Recursos humanos
- Legal

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Planeación del flujo de trabajo de investigación y corrección

Seleccione las partes interesadas dedicadas para supervisar y revisar las alertas y los casos con una cadencia regular en el Centro de cumplimiento de [Microsoft 365.](https://compliance.microsoft.com/) Asegúrese de comprender cómo asignará usuarios y partes interesadas a diferentes grupos de roles de cumplimiento de comunicaciones de su organización.

Dependiendo de cómo quiera administrar las directivas y alertas de comunicación, deberá asignar usuarios a uno o más grupos de roles para administradores, revisores e investigadores. Tiene la opción de asignar usuarios a grupos de roles específicos para administrar distintos conjuntos de características de cumplimiento de comunicaciones. También puede decidir asignar todos los usuarios de cumplimiento de comunicaciones al grupo de roles Cumplimiento de comunicaciones. Use un único grupo de roles o varios grupos para ajustarse mejor a sus requisitos de administración de cumplimiento.

Planee elegir entre estas opciones de grupo de roles al configurar el cumplimiento de las comunicaciones:

|**Rol**|**Permisos de funciones**|
|:-----|:-----|
| **Cumplimiento de comunicaciones** | Use este grupo de roles para administrar el cumplimiento de las comunicaciones de su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados, puede configurar los permisos de cumplimiento de comunicaciones en un solo grupo. Este grupo de roles contiene todas las funciones de permisos de cumplimiento de comunicaciones. Esta configuración es la forma más sencilla de empezar rápidamente con el cumplimiento de las comunicaciones y es una buena opción para las organizaciones que no necesitan permisos independientes definidos para grupos de usuarios independientes. |
| **Administrador de cumplimiento de comunicaciones** | Use este grupo de roles para configurar inicialmente el cumplimiento de las comunicaciones y, posteriormente, separar a los administradores de cumplimiento de comunicaciones en un grupo definido. Los usuarios asignados a este grupo de roles pueden crear, leer, actualizar y eliminar directivas de cumplimiento de comunicaciones, configuraciones globales y asignaciones de grupos de roles. Los usuarios asignados a este grupo de roles no pueden ver alertas de mensajes. |
| **Analista de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver directivas donde se asignan como revisores, ver metadatos de mensajes (no contenido del mensaje), escalar a revisores adicionales o enviar notificaciones a los usuarios. Los analistas no pueden resolver alertas pendientes. |
| **Investigador de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver los metadatos y el contenido de los mensajes, escalar a revisores adicionales, escalar a un caso de eDiscovery avanzado, enviar notificaciones a los usuarios y resolver la alerta. |
| **Visor de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que administrarán informes de comunicación. Los usuarios asignados a este grupo de roles pueden acceder a todos los widgets de informes en la página principal de cumplimiento de comunicaciones y ver todos los informes de cumplimiento de comunicaciones. |

## <a name="plan-for-policies"></a>Planeación de directivas

La creación de directivas de [](communication-compliance-feature-reference.md#policy-templates) cumplimiento de comunicaciones es rápida y fácil con las plantillas predefinidas para lenguaje ofensivo, información confidencial y cumplimiento normativo. Las directivas de cumplimiento de comunicaciones personalizadas permiten la flexibilidad para detectar e investigar problemas específicos de su organización y requisitos.

Al planear directivas de cumplimiento de comunicaciones, tenga en cuenta las siguientes áreas:

- Considere la posibilidad de agregar todos los usuarios de la organización como parte del ámbito de las directivas de cumplimiento de comunicaciones. La identificación de usuarios específicos como dentro del ámbito de directivas individuales es útil en algunas circunstancias, pero la mayoría de las organizaciones deben incluir a todos los usuarios en directivas de cumplimiento de comunicaciones optimizadas para la detección de acoso o discriminación.
- Para simplificar la configuración, considere la posibilidad de crear grupos para las personas que necesitan revisar sus comunicaciones. Si usa grupos; es posible que necesite varios. Por ejemplo, si desea examinar las comunicaciones entre dos grupos distintos de personas o si desea especificar un grupo que no esté supervisado.
- Configure el porcentaje de comunicaciones que se revisará al 100 % para asegurarse de que las directivas están desasoyiendo todos los problemas relacionados con las comunicaciones de su organización.
- Puede examinar las comunicaciones de [orígenes de terceros en](communication-compliance-feature-reference.md#supported-communication-types) busca de datos importados en buzones de correo de su organización de Microsoft 365. Para incluir la revisión de las comunicaciones en estas plataformas, deberá configurar un conector para estos servicios antes de que la directiva de comunicación supervise los mensajes que cumplen las condiciones de la directiva.
- Las directivas pueden admitir la supervisión de idiomas distintos del inglés en las directivas de cumplimiento de comunicaciones personalizadas. Cree un [diccionario personalizado](communication-compliance-feature-reference.md#custom-keyword-dictionaries) de palabras clave de palabras [ofensivas](classifier-get-started-with.md) en el idioma que prefiera o cree su propio modelo de aprendizaje automático con clasificadores que se pueden entrenar en Microsoft 365.
- Todas las organizaciones tienen diferentes estándares de comunicación y necesidades de directivas. Supervise las palabras clave específicas mediante condiciones de directiva de [cumplimiento](communication-compliance-feature-reference.md#conditional-settings) de comunicaciones o supervise los tipos específicos de información con tipos personalizados de [información confidencial.](create-a-custom-sensitive-information-type.md)

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Para configurar el cumplimiento de comunicaciones para su organización de Microsoft 365, consulte Configurar el cumplimiento de comunicaciones para [Microsoft 365](communication-compliance-configure.md) o consulte el caso práctico de [Contoso](communication-compliance-case-study.md) y cómo configuró rápidamente una directiva de cumplimiento de comunicaciones para supervisar el lenguaje ofensivo en las comunicaciones de Microsoft Teams, Exchange Online y Yammer.
