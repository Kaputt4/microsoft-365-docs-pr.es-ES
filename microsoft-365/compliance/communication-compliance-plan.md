---
title: Planear el cumplimiento de las comunicaciones
description: Obtenga información sobre cómo planear el uso del cumplimiento de comunicaciones en su organización.
keywords: Microsoft 365, Microsoft Purview, cumplimiento, cumplimiento de comunicaciones
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
- tier1
- purview-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: c1463866c97e5618caa4bab0cc45328d1849fc01
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68730895"
---
# <a name="plan-for-communication-compliance"></a>Planear el cumplimiento de las comunicaciones

>[!IMPORTANT]
>Cumplimiento de comunicaciones de Microsoft Purview proporciona las herramientas para ayudar a las organizaciones a detectar infracciones de cumplimiento normativo (por ejemplo, SEC o FINRA), como información confidencial o confidencial, hostigamiento o amenazante del lenguaje y uso compartido de contenido para adultos. Creados con privacidad por diseño, los nombres de usuario se seudonimizan de forma predeterminada, los controles de acceso basados en roles están integrados, los investigadores son admitidos por un administrador y los registros de auditoría están en su lugar para ayudar a garantizar la privacidad del nivel de usuario.

Antes de empezar a trabajar con [el cumplimiento de la comunicación](/microsoft-365/compliance/communication-compliance) en su organización, hay importantes actividades y consideraciones de planeamiento que deben revisar los equipos de administración de la tecnología de la información y el cumplimiento. Comprender y planear exhaustivamente la implementación en las siguientes áreas ayudará a garantizar que la implementación y el uso de las características de cumplimiento de comunicaciones funcionen sin problemas y se alineen con los procedimientos recomendados para la solución.

Para obtener más información y una visión general del proceso de planeamiento para abordar las actividades de cumplimiento y riesgo en su organización, consulte [Inicio de un programa de administración de riesgos internos](https://download.microsoft.com/download/b/2/0/b208282a-2482-4986-ba07-15a9b9286df0/pwc-starting-an-insider-risk-management-program-with-pwc-and-microsoft.pdf).

También puede consultar el vídeo de [Microsoft Mechanics](https://www.youtube.com/watch?v=Ynkfu8OF0wQ) para ver cómo funcionan conjuntamente la administración de riesgos internos y el cumplimiento de comunicaciones para ayudar a minimizar los riesgos de datos de los usuarios de su organización.

> [!IMPORTANT]
> El cumplimiento de comunicaciones está disponible actualmente en los inquilinos hospedados en regiones geográficas y países compatibles con las dependencias del servicio de Azure. Para comprobar que el cumplimiento de comunicaciones es compatible con su organización, consulte [Disponibilidad de dependencias de Azure por país o región](/troubleshoot/azure/general/dependency-availability-by-country).

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="transition-from-supervision-in-office-365"></a>Transición de supervisión en Office 365

Para las organizaciones que usan directivas de supervisión en Office 365, debe planear inmediatamente la transición a las directivas de cumplimiento de comunicaciones en Microsoft Purview y debe comprender estos puntos importantes:

- La solución de supervisión de Office 365 se ha reemplazado por completo por la solución de cumplimiento de comunicaciones de Microsoft Purview. Se recomienda crear nuevas directivas en cumplimiento de comunicaciones que tengan la misma configuración que las directivas de supervisión existentes para usar las nuevas mejoras de investigación y corrección.
- Los mensajes guardados en supervisión en Office 365 coincidencias de directivas no se pueden mover ni compartir en el cumplimiento de la comunicación.
- En el caso de las organizaciones con ambas soluciones que se usan en paralelo durante el proceso de transición, las directivas usadas en cada solución deben tener nombres de directiva únicos. Los grupos y los diccionarios de palabras clave personalizados se pueden compartir entre soluciones durante un período de transición.

Para obtener información sobre la retirada de la supervisión en Office 365, consulte la [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obtener más información.

## <a name="work-with-stakeholders-in-your-organization"></a>Trabajar con las partes interesadas de la organización

Identifique las partes interesadas adecuadas de su organización para colaborar para realizar acciones en las alertas de cumplimiento de comunicaciones. Algunas partes interesadas recomendadas para considerar la posibilidad de incluir en el planeamiento inicial y el [flujo de trabajo de cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance#workflow) de un extremo a otro son personas de las siguientes áreas de la organización:

- Tecnología de la información
- Cumplimiento
- Privacidad
- Seguridad
- Recursos humanos
- Legal

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Planear el flujo de trabajo de investigación y corrección

Seleccione partes interesadas dedicadas para investigar y revisar las alertas y los casos con una cadencia regular en el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/). Asegúrese de comprender cómo va a asignar usuarios y partes interesadas a diferentes grupos de roles de cumplimiento de comunicaciones de su organización.

> [!IMPORTANT]
> Después de configurar los grupos de roles, los permisos del grupo de roles pueden tardar hasta 30 minutos en aplicarse a los usuarios asignados en toda la organización.

### <a name="configure-permissions"></a>Configurar permisos

Hay seis grupos de roles que se usan para configurar los permisos iniciales para administrar las características de cumplimiento de comunicaciones. Para que **el cumplimiento de la comunicación** esté disponible como una opción de menú en portal de cumplimiento Microsoft Purview y para continuar con estos pasos de configuración, debe estar asignado a uno de los siguientes roles o grupos de roles:

- Rol [*de administrador global*](/azure/active-directory/roles/permissions-reference#global-administrator) de Azure Active Directory
- Rol [*administrador de cumplimiento de*](/azure/active-directory/roles/permissions-reference#compliance-administrator) Azure Active Directory
- portal de cumplimiento Microsoft Purview grupo [*de roles De administración de la organización*](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)
- portal de cumplimiento Microsoft Purview grupo de roles [*administrador de cumplimiento*](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)
- *Grupo de roles de cumplimiento de comunicaciones*
- Grupo *de roles Administradores de cumplimiento de comunicaciones*

Los miembros de los roles siguientes tienen los mismos permisos de solución incluidos en el grupo de roles *Administradores de cumplimiento de comunicaciones* :

- *Administrador global* de Azure Active Directory
- *Administrador de cumplimiento de* Azure Active Directory
- administración de la *organización* portal de cumplimiento Microsoft Purview
- *Administrador de cumplimiento de* portal de cumplimiento Microsoft Purview

> [!IMPORTANT]
> Asegúrese de que siempre tiene al menos un usuario en los grupos de roles *Administradores de cumplimiento de comunicaciones* o cumplimiento de *comunicaciones* (según la opción que elija) para que la configuración de cumplimiento de comunicaciones no entre en un escenario de "administrador cero" si determinados usuarios abandonan la organización.

En función de cómo quiera administrar las directivas y alertas de cumplimiento de comunicaciones, deberá asignar usuarios a grupos de roles específicos para administrar diferentes conjuntos de características de cumplimiento de comunicaciones. Tiene la opción de asignar usuarios con diferentes responsabilidades de cumplimiento a grupos de roles específicos para administrar diferentes áreas de características de cumplimiento de comunicaciones. O bien, puede decidir asignar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados al grupo de roles *cumplimiento de comunicaciones* . Use un único grupo de roles o varios grupos de roles para adaptarse mejor a los requisitos de administración de cumplimiento.

Elija entre estas opciones de grupo de roles de solución al configurar y administrar el cumplimiento de las comunicaciones:

|**Rol**|**Permisos de funciones**|
|:-----|:-----|
| **Cumplimiento de comunicaciones** | Use este grupo de roles para administrar el cumplimiento de las comunicaciones de su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados, puede configurar los permisos de cumplimiento de comunicaciones en un solo grupo. Este grupo de roles contiene todos los roles de permiso de cumplimiento de comunicaciones. Esta configuración es la manera más fácil de empezar a trabajar rápidamente con el cumplimiento de las comunicaciones y es una buena opción para las organizaciones que no necesitan permisos independientes definidos para grupos de usuarios independientes. Los usuarios que crean directivas como administrador de cumplimiento de comunicaciones deben tener su buzón hospedado en Exchange Online. |
| **Administradores de cumplimiento de comunicaciones** | Use este grupo de roles para configurar inicialmente el cumplimiento de comunicaciones y, posteriormente, para separar a los administradores de cumplimiento de comunicaciones en un grupo definido. Los usuarios asignados a este grupo de roles pueden crear, leer, actualizar y eliminar directivas de cumplimiento de comunicaciones, configuración global y asignaciones de grupos de roles. Los usuarios asignados a este grupo de roles no pueden ver alertas de mensajes. Los usuarios que crean directivas como administrador de cumplimiento de comunicaciones deben tener su buzón hospedado en Exchange Online. |
| **Analistas de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver las directivas donde se asignan como revisores, ver los metadatos del mensaje (no el contenido del mensaje), escalar a revisores adicionales o enviar notificaciones a los usuarios. Los analistas no pueden resolver las alertas pendientes. |
| **Investigadores de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver los metadatos y el contenido del mensaje, escalar a revisores adicionales, escalar a un caso de eDiscovery (Premium), enviar notificaciones a los usuarios y resolver la alerta. |
| **Visores de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que administrarán los informes de comunicación. Los usuarios asignados a este grupo de roles pueden acceder a todos los widgets de informes en la página principal de cumplimiento de comunicaciones y pueden ver todos los informes de cumplimiento de comunicaciones. |

### <a name="supervised-users"></a>Usuarios supervisados

Antes de empezar a usar el cumplimiento de comunicaciones, necesita determinar a quién se debe revisar las comunicaciones. En la directiva, las direcciones de correo electrónico de los usuarios identifican a las personas o grupos de personas que se van a supervisar. Algunos ejemplos de estos grupos son Grupos de Microsoft 365, listas de distribución basadas en Exchange, comunidades de Yammer y canales de Microsoft Teams. También puede excluir usuarios o grupos específicos de la comprobación con un grupo de exclusión específico o una lista de grupos. Para obtener más información sobre los tipos de grupos admitidos en las directivas de cumplimiento de comunicaciones, consulte [Introducción al cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance-configure#step-3-optional-set-up-groups-for-communication-compliance).

> [!IMPORTANT]
> Los usuarios cubiertos por las directivas de cumplimiento de comunicaciones deben tener una licencia de Cumplimiento de Microsoft 365 E5, una licencia Office 365 Enterprise E3 con el complemento de cumplimiento avanzado o incluirse en una suscripción Office 365 Enterprise E5. Si no tiene un plan Enterprise E5 existente y quiere probar el cumplimiento de la comunicación, puede [registrarse para obtener una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

### <a name="reviewers"></a>Reviewers

Al crear una directiva de cumplimiento de comunicaciones, debe determinar quién revisa los mensajes de los usuarios supervisados. En la directiva, las direcciones de correo electrónico de los usuarios identifican a individuos o grupos de personas que revisarán las comunicaciones supervisadas. Todos los revisores deben tener buzones hospedados en Exchange Online, deben estar asignados a los grupos de roles *Analistas de cumplimiento de comunicaciones* o *Investigadores de cumplimiento de comunicaciones* y deben asignarse en la directiva que necesitan investigar. Cuando los revisores se agregan a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la directiva y proporciona vínculos a información sobre el proceso de revisión.

### <a name="groups-for-supervised-users-and-reviewers"></a>Grupos para usuarios y revisores supervisados

Para simplificar la configuración, se recomienda crear grupos para las personas que necesitan revisar sus comunicaciones y grupos para las personas que revisan esas comunicaciones. Si usa grupos, es posible que necesite varios. Por ejemplo, si desea identificar las comunicaciones entre dos grupos de personas distintos o si desea especificar un grupo que no esté supervisado. Al asignar un grupo de distribución en la directiva, la directiva detecta todos los correos electrónicos de cada usuario del grupo distribución. Al asignar un grupo de Microsoft 365 en la directiva, la directiva detecta todos los correos electrónicos enviados a ese grupo, no los correos electrónicos individuales recibidos por cada miembro del grupo.

La adición de grupos y listas de distribución a las directivas de cumplimiento de comunicaciones forma parte de las condiciones y reglas generales establecidas, por lo que el número máximo de grupos y listas de distribución que admite una directiva varía en función del número de condiciones que también se agreguen a la directiva. Cada directiva debe admitir aproximadamente 20 grupos o listas de distribución, en función del número de condiciones adicionales presentes en la directiva.

El siguiente gráfico puede ayudarle a configurar grupos en su organización para directivas de cumplimiento de comunicaciones:

| **Miembro de directiva** | **Grupos admitidos** | **Grupos no admitidos** |
|:-----|:-----|:-----|
|Usuarios supervisados <br> Usuarios excluidos | Grupos de distribución <br> Grupos de Microsoft 365 | Grupos de distribución dinámicos <br> Grupos de distribución anidados <br> Grupos de seguridad habilitados para correo <br> Grupos de Microsoft 365 con pertenencia dinámica |
| Reviewers | Ninguno | Grupos de distribución <br> Grupos de distribución dinámicos <br> Grupos de distribución anidados <br> Grupos de seguridad habilitados para correo |

### <a name="privacy"></a>Privacidad

La protección de la privacidad de los usuarios que tienen coincidencias de directivas es importante y puede ayudar a promover la objetividad en las revisiones de análisis y investigación de datos para las alertas de cumplimiento de comunicaciones. Esta configuración solo se aplica a los nombres de usuario que muestran la solución de cumplimiento de comunicaciones. No afecta a cómo se muestran los nombres en otras soluciones de cumplimiento o centro de administración.

Para los usuarios con una coincidencia de cumplimiento de comunicaciones, puede elegir una de las siguientes opciones en **Configuración de cumplimiento de comunicaciones**:

- **Mostrar versiones anónimas de nombres de usuario**: los nombres de usuario se anonimizan para evitar que los usuarios del grupo de roles *Analistas de cumplimiento de comunicaciones* vean quién está asociado a las alertas de directiva. Los usuarios del grupo de roles *Investigadores de cumplimiento de comunicaciones* siempre verán los nombres de usuario, no las versiones anonimizadas. Por ejemplo, un usuario "Grace Taylor" aparecería con un seudónimo aleatorio como "AnonIS8-988" en todas las áreas de la experiencia de cumplimiento de la comunicación. Al elegir esta configuración, se anonimizan todos los usuarios con coincidencias de directivas actuales y pasadas, y se aplica a todas las directivas. La información del perfil de usuario en los detalles de la alerta de cumplimiento de comunicaciones no estará disponible cuando se elija esta opción. Sin embargo, los nombres de usuario se muestran al agregar nuevos usuarios a directivas existentes o al asignar usuarios a nuevas directivas. Si decide desactivar esta configuración, se mostrarán los nombres de usuario de todos los usuarios que tengan coincidencias de directivas actuales o anteriores.
- **No mostrar versiones anonimizadas de nombres de usuario**: los nombres de usuario se muestran para todas las coincidencias de directivas actuales y anteriores para las alertas de cumplimiento de comunicaciones. La información del perfil de usuario (el nombre, el título, el alias y la organización o el departamento) se muestra para el usuario para todas las alertas de cumplimiento de comunicaciones.

## <a name="plan-for-communication-compliance-policies"></a>Planeamiento de directivas de cumplimiento de comunicaciones

La creación de directivas de cumplimiento de comunicaciones es rápida y sencilla con las [plantillas predefinidas](/microsoft-365/compliance/communication-compliance-policies#policy-templates) para analizar contenido potencialmente inadecuado, información confidencial y problemas de cumplimiento normativo. Las directivas de cumplimiento de comunicaciones personalizadas permiten la flexibilidad para detectar e investigar problemas específicos de la organización y los requisitos.

Al planear las directivas de cumplimiento de comunicaciones, tenga en cuenta las siguientes áreas:

- Considere la posibilidad de agregar todos los usuarios de la organización como en el ámbito de las directivas de cumplimiento de comunicaciones. La identificación de usuarios específicos como en el ámbito de las directivas individuales es útil en algunas circunstancias, pero la mayoría de las organizaciones deben incluir a todos los usuarios en las directivas de cumplimiento de comunicaciones optimizadas para la detección de acoso o discriminación.
- Configure el porcentaje de comunicaciones que se van a revisar al 100 % para asegurarse de que las directivas detectan todos los problemas que preocupan en las comunicaciones de su organización.
- Puede analizar las comunicaciones de [orígenes de terceros](/microsoft-365/compliance/communication-compliance-channels#third-party-sources) para los datos importados en buzones de su organización de Microsoft 365. Para incluir la revisión de las comunicaciones en estas plataformas, deberá configurar un conector de terceros para estos servicios antes de que una directiva de comunicación detecte los mensajes que cumplen las condiciones de la directiva.
- Las directivas pueden admitir la detección de idiomas distintos del inglés en las directivas de cumplimiento de comunicaciones personalizadas. Cree un [diccionario de palabras clave personalizadas](/microsoft-365/compliance/communication-compliance-policies#custom-keyword-dictionaries) de palabras ofensivas en el idioma que prefiera o cree su propio modelo de aprendizaje automático mediante [clasificadores entrenables](/microsoft-365/compliance/classifier-get-started-with) en Microsoft 365.
- Todas las organizaciones tienen diferentes estándares de comunicación y necesidades de directiva. Detecte palabras clave específicas mediante [condiciones de directiva](/microsoft-365/compliance/communication-compliance-policies#conditional-settings) de cumplimiento de comunicaciones o detecte tipos específicos de información con [tipos de información confidencial personalizados](/microsoft-365/compliance/create-a-custom-sensitive-information-type).

## <a name="create-a-communication-compliance-policy-walkthrough"></a>Tutorial sobre la creación de una directiva de cumplimiento de comunicaciones

¿Desea ver un tutorial detallado sobre cómo configurar una nueva directiva de cumplimiento de comunicaciones y corregir una alerta? Consulte el siguiente vídeo de 15 minutos para ver una demostración de cómo las directivas de cumplimiento de comunicaciones pueden ayudarle a detectar mensajes potencialmente inadecuados, investigar posibles infracciones y corregir problemas de cumplimiento.
<br>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RWNchy]
<br>

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Para configurar el cumplimiento de comunicaciones para su organización de Microsoft 365, consulte [Configuración del cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance-configure) o consulte el [caso práctico de Contoso](/microsoft-365/compliance/communication-compliance-case-study) y cómo configuraron rápidamente una directiva de cumplimiento de comunicaciones para detectar contenido potencialmente inadecuado en Microsoft Teams, Exchange Online y comunicaciones de Yammer.
