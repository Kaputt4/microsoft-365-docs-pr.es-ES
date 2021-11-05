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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: e5bb82d82d0b96334e716c4c0efd5cb700942f4e
ms.sourcegitcommit: 27bf284b3bfe334eb98847798734625bd2ffafb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2021
ms.locfileid: "60792309"
---
# <a name="plan-for-communication-compliance"></a>Planear el cumplimiento de las comunicaciones

Antes de empezar con el cumplimiento [de](communication-compliance.md) las comunicaciones en su organización, hay importantes actividades de planeación y consideraciones que deben revisar los equipos de administración de tecnología de la información y cumplimiento. El conocimiento exhaustivo y la planeación de la implementación en las siguientes áreas ayudarán a garantizar que la implementación y el uso de las características de cumplimiento de comunicaciones se adapten a los procedimientos recomendados para la solución.

## <a name="transitioning-from-supervision-in-office-365"></a>Transición desde supervisión en Office 365

Para las organizaciones que usan directivas de supervisión en Office 365, debe planear inmediatamente la transición a las directivas de cumplimiento de comunicaciones en Microsoft 365 y debe comprender estos puntos importantes:

- La solución de supervisión en Office 365 se ha reemplazado completamente por la solución de cumplimiento de comunicaciones en Microsoft 365. Se recomienda crear nuevas directivas en el cumplimiento de comunicaciones que tengan la misma configuración que las directivas de supervisión existentes para usar las nuevas mejoras de investigación y corrección.
- Los mensajes guardados en supervisión en Office 365 coincidencias de directiva no se pueden mover ni compartir en el cumplimiento de la comunicación en Microsoft 365.
- Para las organizaciones con ambas soluciones usadas en paralelo durante el proceso de transición, las directivas usadas en cada solución deben tener nombres de directiva únicos. Los grupos y los diccionarios de palabras clave personalizados se pueden compartir entre soluciones durante un período de transición.

Para obtener información sobre la retirada para la supervisión en Office 365, consulte [Microsoft 365 Roadmap para](https://www.microsoft.com/microsoft-365/roadmap) obtener más información.

## <a name="work-with-stakeholders-in-your-organization"></a>Trabajar con las partes interesadas de la organización

Identifique a las partes interesadas apropiadas de su organización para colaborar en la toma de acciones en las alertas de cumplimiento de comunicaciones. Algunas partes interesadas recomendadas que deben considerar incluir [](communication-compliance.md#workflow) en la planeación inicial y el flujo de trabajo de cumplimiento de comunicaciones de extremo a extremo son personas de las siguientes áreas de su organización:

- Tecnología de la información
- Cumplimiento
- Privacidad
- Seguridad
- Recursos humanos
- Legal

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Planear el flujo de trabajo de investigación y corrección

### <a name="permissions"></a>Permisos

Seleccione las partes interesadas dedicadas para supervisar y revisar las alertas y los casos en una cadencia regular en el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/). Asegúrese de comprender cómo asignará usuarios y partes interesadas a diferentes grupos de roles de cumplimiento de comunicaciones de su organización.

Hay cinco grupos de roles que se usan para configurar permisos para administrar las características de cumplimiento de comunicaciones. Para que **el cumplimiento** de la comunicación esté disponible como una opción de menú  en Centro de cumplimiento de Microsoft 365 y continuar con estos pasos de configuración, debe asignarse a los grupos de roles Cumplimiento de comunicaciones o Administración de cumplimiento *de* comunicaciones. Para obtener acceso y administrar las características de cumplimiento de comunicaciones después de la configuración inicial, los usuarios deben ser miembros de al menos un grupo de roles de cumplimiento de comunicaciones.

> [!IMPORTANT]
> De forma predeterminada, los administradores globales no tienen acceso a las características de cumplimiento de la comunicación. Los roles asignados en este paso son necesarios antes de que se pueda acceder a las características de cumplimiento de comunicaciones.

Dependiendo de cómo desee administrar las directivas de comunicación y las alertas, deberá asignar usuarios a grupos de roles específicos. Puede elegir asignar usuarios con diferentes responsabilidades de cumplimiento a grupos de roles específicos para administrar diferentes áreas de características de cumplimiento de comunicación. O puede decidir asignar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados al grupo de roles *Cumplimiento* de comunicaciones. Use un único grupo de roles o varios grupos de roles para ajustarse mejor a sus requisitos de administración de cumplimiento.

Elija entre estas opciones de grupo de roles al configurar el cumplimiento de la comunicación:

|**Rol**|**Permisos de funciones**|
|:-----|:-----|
| **Cumplimiento de comunicaciones** | Use este grupo de roles para administrar el cumplimiento de comunicaciones de su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores designados, analistas, investigadores y visores, puede configurar los permisos de cumplimiento de comunicaciones en un solo grupo. Este grupo de funciones contiene todos los roles de permisos de cumplimiento de comunicación. Esta configuración es la forma más sencilla de empezar rápidamente con el cumplimiento de las comunicaciones y es una buena opción para las organizaciones que no necesitan permisos independientes definidos para grupos independientes de usuarios. Los usuarios que creen directivas como administrador de cumplimiento de comunicaciones deben tener su buzón hospedado en Exchange Online. |
| **Administrador de cumplimiento de comunicaciones** | Use este grupo de roles para configurar inicialmente el cumplimiento de las comunicaciones y posteriormente para segregar a los administradores de cumplimiento de comunicaciones en un grupo definido. Los usuarios asignados a este grupo de roles pueden crear, leer, actualizar y eliminar directivas de cumplimiento de comunicación, configuración global y asignaciones de grupos de roles. Los usuarios asignados a este grupo de roles no pueden ver alertas de mensajes. Los usuarios que creen directivas como administrador de cumplimiento de comunicaciones deben tener su buzón hospedado en Exchange Online. |
| **Analista de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver directivas en las que se les asigna como revisores, ver metadatos de mensajes (no contenido del mensaje), escalar a revisores adicionales o enviar notificaciones a los usuarios. Los analistas no pueden resolver alertas pendientes. |
| **Investigador de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver los metadatos y el contenido de los mensajes, escalar a revisores adicionales, escalar a un caso Advanced eDiscovery, enviar notificaciones a los usuarios y resolver la alerta. |
| **Visor de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que administrarán informes de comunicación. Los usuarios asignados a este grupo de roles pueden tener acceso a todos los widgets de informes de la página principal de cumplimiento de comunicaciones y pueden ver todos los informes de cumplimiento de comunicaciones. |

### <a name="supervised-users"></a>Usuarios supervisados

Antes de empezar a usar el cumplimiento de comunicaciones, necesita determinar a quién se debe revisar las comunicaciones. En la directiva, las direcciones de correo electrónico de los usuarios identifican a las personas o grupos de personas que se van a supervisar. Algunos ejemplos de estos grupos son Microsoft 365, listas de distribución basadas Exchange, Yammer comunidades y Microsoft Teams canales. Asimismo, puede excluir usuarios o grupos específicos de la revisión con un grupo de exclusión específico o una lista de grupos. Para obtener más información acerca de los tipos de grupos admitidos en las directivas de cumplimiento de comunicaciones, vea [Introducción al cumplimiento de comunicaciones.](communication-compliance-configure.md#step-3-optional-set-up-groups-for-communication-compliance)

> [!IMPORTANT]
> Los usuarios cubiertos por directivas de cumplimiento de comunicaciones deben tener una licencia de Cumplimiento de Microsoft 365 E5, una licencia de E3 de Office 365 Enterprise con el complemento de cumplimiento avanzado o estar incluidos en una suscripción Office 365 Enterprise E5. Si no tiene un plan Enterprise E5 y desea probar el cumplimiento de las comunicaciones, puede registrarse para una prueba de [Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

### <a name="reviewers"></a>Reviewers

Al crear una directiva de cumplimiento de comunicaciones, debe determinar quién revisa los mensajes de los usuarios supervisados. En la directiva, las direcciones de correo electrónico de los usuarios identifican a individuos o grupos de personas que revisarán las comunicaciones supervisadas. Todos los revisores deben tener buzones hospedados en Exchange Online  y deben estar asignados a los roles análisis de cumplimiento de comunicación o investigación de cumplimiento *de* comunicación. Los revisores (analistas o investigadores) también deben tener asignado el rol *de administración* de casos de cumplimiento de comunicación. Cuando se agregan revisores a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la directiva y proporciona vínculos a información sobre el proceso de revisión.

### <a name="groups-for-supervised-users-and-reviewers"></a>Grupos para usuarios y revisores supervisados

Para simplificar la configuración, cree grupos para las personas que necesitan revisar sus comunicaciones y grupos para las personas que revisan dichas comunicaciones. Si usa grupos, es posible que necesite varios. Por ejemplo, si quiere examinar las comunicaciones entre dos grupos distintos de personas, o si desea especificar un grupo que no esté supervisado. Al asignar un grupo de distribución en la directiva, la directiva supervisa todos los correos electrónicos de cada usuario en el grupo de distribución. Al asignar un grupo Microsoft 365 en la directiva, la directiva supervisa todos los correos electrónicos enviados a ese grupo, no los correos electrónicos individuales recibidos por cada miembro del grupo.

La adición de grupos y listas de distribución a las directivas de cumplimiento de comunicaciones forma parte de las condiciones generales y las reglas establecidas, por lo que el número máximo de grupos y listas de distribución que admite una directiva varía en función del número de condiciones que también se agreguen a la directiva. Cada directiva debe admitir aproximadamente 20 grupos o listas de distribución, según el número de condiciones adicionales presentes en la directiva.

Use el siguiente gráfico para ayudarle a configurar grupos en su organización para las directivas de cumplimiento de comunicaciones:

| **Miembro de la directiva** | **Grupos admitidos** | **Grupos no admitidos** |
|:-----|:-----|:-----|
|Usuarios supervisados <br> Usuarios excluidos | Grupos de distribución <br> Grupos de Microsoft 365 | Grupos de distribución dinámicos <br> Grupos de distribución anidados <br> Grupos de seguridad habilitados para correo <br> Microsoft 365 grupos con pertenencia dinámica |
| Reviewers | Ninguno | Grupos de distribución <br> Grupos de distribución dinámicos <br> Grupos de distribución anidados <br> Grupos de seguridad habilitados para correo |

### <a name="privacy"></a>Privacidad

Proteger la privacidad de los usuarios que tienen coincidencias de directiva es importante y puede ayudar a promover la objetividad en las revisiones de investigación y análisis de datos para alertas de cumplimiento de comunicaciones. Esta configuración solo se aplica a los nombres de usuario que muestran la solución de cumplimiento de comunicaciones. No afecta a cómo se muestran los nombres en otras soluciones de cumplimiento o en el Centro de administración.

Para los usuarios con una coincidencia de cumplimiento de comunicación, puede elegir una de las siguientes opciones en **Configuración de cumplimiento de comunicaciones:**

- **Mostrar versiones anonimizadas** de nombres de usuario:  los nombres de usuario se anonimizan para impedir que los usuarios del grupo de roles de analista de cumplimiento de comunicaciones vean quién está asociado con las alertas de directiva. Los usuarios del grupo *de roles Investigador de cumplimiento* de comunicaciones siempre verán nombres de usuario, no las versiones anonimizadas. Por ejemplo, un usuario "Grace Taylor" aparecería con un seudónimo aleatorio como "AnonIS8-988" en todas las áreas de la experiencia de cumplimiento de comunicación. Al elegir esta configuración, se anonimizan todos los usuarios con coincidencias de directivas actuales y pasadas, y se aplica a todas las directivas. La información del perfil de usuario en los detalles de la alerta de cumplimiento de comunicaciones no estará disponible cuando se elija esta opción. Sin embargo, los nombres de usuario se muestran al agregar nuevos usuarios a directivas existentes o al asignar usuarios a nuevas directivas. Si decide desactivar esta configuración, se mostrarán los nombres de usuario para todos los usuarios que tengan coincidencias de directiva actuales o pasadas.
- **No mostrar versiones anónimas de** nombres de usuario: los nombres de usuario se muestran para todas las coincidencias de directiva actuales y pasadas para las alertas de cumplimiento de comunicaciones. La información de perfil de usuario (nombre, título, alias y organización o departamento) se muestra para el usuario para todas las alertas de cumplimiento de comunicaciones.

## <a name="plan-for-policies"></a>Planeación de directivas

La creación de directivas de cumplimiento de comunicaciones es rápida y fácil con las plantillas [predefinidas](communication-compliance-policies.md#policy-templates) para contenido inadecuado, información confidencial y cumplimiento normativo. Las directivas de cumplimiento de comunicaciones personalizadas permiten la flexibilidad para detectar e investigar problemas específicos de la organización y los requisitos.

Al planear las directivas de cumplimiento de comunicaciones, tenga en cuenta las siguientes áreas:

- Considere la posibilidad de agregar todos los usuarios de la organización como en el ámbito de las directivas de cumplimiento de comunicación. La identificación de usuarios específicos como en el ámbito de las directivas individuales es útil en algunas circunstancias, pero la mayoría de las organizaciones deben incluir a todos los usuarios en directivas de cumplimiento de comunicaciones optimizadas para la detección de acoso o discriminación.
- Configure el porcentaje de comunicaciones que se revisará al 100 % para asegurarse de que las directivas están atando todos los problemas que preocupan en las comunicaciones de su organización.
- Puede examinar las comunicaciones de [orígenes de terceros en](communication-compliance-channels.md#third-party-sources) busca de datos importados en buzones de correo de su Microsoft 365 organización. Para incluir la revisión de las comunicaciones en estas plataformas, deberá configurar un conector para estos servicios antes de que la directiva de comunicación supervise los mensajes que cumplen las condiciones de la directiva.
- Las directivas pueden admitir la supervisión de idiomas distintos del inglés en directivas de cumplimiento de comunicaciones personalizadas. Crea un [diccionario de palabras](communication-compliance-policies.md#custom-keyword-dictionaries) clave personalizado de palabras ofensivas en el idioma que prefieras o crea tu propio modelo de aprendizaje automático con clasificadores [capacitados](classifier-get-started-with.md) en Microsoft 365.
- Todas las organizaciones tienen diferentes estándares de comunicación y necesidades de directiva. Supervisar palabras clave específicas mediante condiciones de directiva de [cumplimiento](communication-compliance-policies.md#conditional-settings) de comunicación o supervisar tipos específicos de información con tipos de información [confidencial personalizados.](create-a-custom-sensitive-information-type.md)

## <a name="creating-a-communication-compliance-policy-walkthrough"></a>Crear un tutorial de directiva de cumplimiento de comunicaciones

¿Desea ver un tutorial detallado sobre cómo configurar una nueva directiva de cumplimiento de comunicaciones y corregir una alerta? Consulte el siguiente vídeo de 15 minutos para ver una demostración de cómo las directivas de cumplimiento de comunicación pueden ayudarle a detectar mensajes inapropiados, investigar posibles infracciones y corregir problemas de cumplimiento.
<br>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RWNchy]
<br>

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Para configurar el cumplimiento de comunicaciones para su organización de Microsoft 365, vea Configure communication compliance for Microsoft 365 or check out the [case study for Contoso](communication-compliance-case-study.md) and how they quickly configured a communication compliance policy to monitor for inappropriate content in [Microsoft Teams,](communication-compliance-configure.md) Exchange Online, and Yammer communications.
