---
title: 'Directivas recomendadas de Teams: Microsoft 365 Enterprise | Microsoft docs'
description: Describe las directivas de recomendaciones de Microsoft sobre cómo proteger la comunicación y el acceso a archivos de Microsoft Teams.
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: heidip
ms.date: 10/31/2019
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 645abf48297ddcf186d8971a422588d46f7b2fef
ms.sourcegitcommit: 7c977771fc295ca1e4e9b16a6d05faee8edeadad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "37913123"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Recomendaciones de directivas para proteger los chats, grupos y archivos de Microsoft Teams

En este artículo se describe cómo implementar la identidad recomendada y las directivas de acceso a dispositivos para proteger los chats, grupos y contenido de Microsoft Teams, como archivos y calendarios. Esta guía se basa en las [directivas comunes de identidad y acceso a dispositivos](identity-access-policies.md), con información adicional que es específica de cada equipo. Como Microsoft Teams se integra con nuestros otros productos, vea también [recomendaciones de directivas para proteger los sitios y archivos de SharePoint](sharepoint-file-access-policies.md) y [recomendaciones de directivas para proteger el correo electrónico](secure-email-recommended-policies.md).

Estas recomendaciones se basan en tres niveles diferentes de seguridad y protección para Teams que se pueden aplicar en función de la granularidad de sus necesidades: línea de base, confidencial y muy regulada. Puede obtener más información sobre estos niveles de seguridad y las directivas recomendadas a las que se hace referencia con estas recomendaciones en las [configuraciones de identidad y acceso a dispositivos](microsoft-365-policies-configurations.md).

En este artículo se incluyen recomendaciones adicionales específicas de la implementación de Teams para cubrir determinadas circunstancias de autenticación, incluidas las de los usuarios externos a la organización. Tendrá que seguir esta guía para obtener una experiencia de seguridad completa.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Introducción a teams antes de otros servicios dependientes

No es necesario que habilite los servicios dependientes para empezar a trabajar con Microsoft Teams. Todo "simplemente funcionará". Sin embargo, debe estar preparado para administrar lo siguiente:

- Grupos de Office 365
- Sitios de grupo de SharePoint
- OneDrive para la Empresa
- Buzones
- Vídeos de secuencia y planes de Planner (si estos servicios están habilitados)

## <a name="updating-common-policies-to-include-teams"></a>Actualización de directivas comunes para incluir equipos

El siguiente diagrama ilustra el conjunto de directivas recomendadas para proteger chats, grupos y contenido en Teams. El icono de lápiz indica qué directivas deben revisarse para asegurarse de que Teams y los servicios dependientes se incluyen en la asignación de aplicaciones en la nube.

![Un diagrama que muestra cómo usar Microsoft Teams en varios dispositivos.](../images/identity-access-ruleset-teams.png)

Estos son los servicios dependientes que se deben incluir en la asignación de aplicaciones en la nube para Teams:

- Microsoft Teams
- SharePoint Online y OneDrive para la Empresa
- Exchange Online
- Skype Empresarial Online
- Microsoft Stream (grabaciones de reuniones)
- Microsoft Planner (tareas de Planner y datos del plan)

En esta tabla se enumeran las directivas que deben revisitarse y vínculos a cada directiva en [las directivas comunes de identidad y acceso a dispositivos](identity-access-policies.md), que tienen el conjunto de reglas más amplio para todas las aplicaciones de Office.

|Nivel de protección|Directivas|Información adicional para la implementación de Teams|
|:---------------|:-------|:----------------|
|**Baseline**|[Requerir MFA cuando el riesgo de inicio de sesión sea *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Asegúrese de que Microsoft Teams y los servicios dependientes se incluyen en la lista de aplicaciones. Teams tiene también acceso de invitado y reglas de acceso externo que se deben tener en cuenta, obtendrá más información sobre estos en este artículo.|
|        |[Bloquear a los clientes que no sean compatibles con la autenticación moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Incluir equipos y servicios dependientes en la asignación de aplicaciones en la nube.|
|        |[Los usuarios de riesgo alto deben cambiar la contraseña](identity-access-policies.md#high-risk-users-must-change-password)|Obliga a los usuarios de Microsoft Teams a cambiar su contraseña al iniciar sesión si se detecta una actividad de alto riesgo para su cuenta. Asegúrese de que Microsoft Teams y los servicios dependientes se incluyen en la lista de aplicaciones.|
|        |[Definir directivas de protección de aplicaciones](identity-access-policies.md#define-app-protection-policies)|Asegúrese de que Microsoft Teams y los servicios dependientes se incluyen en la lista de aplicaciones. Actualice la Directiva para cada plataforma (iOS, Android, Windows).|
|        |[Requerir aplicaciones aprobadas](identity-access-policies.md#require-approved-apps)|Incluir equipos y servicios dependientes en esta Directiva.|
|        |[Definir directivas de cumplimiento de dispositivos](identity-access-policies.md#define-device-compliance-policies)|Incluir equipos y servicios dependientes en esta Directiva.|
|        |[Exigir equipos PC compatibles](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Incluir equipos y servicios dependientes en esta Directiva.|
|**Confidencial**|[Requerir MFA cuando el riesgo de inicio de sesión es *bajo*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams tiene también acceso de invitado y reglas de acceso externo que se deben tener en cuenta, obtendrá más información sobre estos en este artículo. Incluir equipos y servicios dependientes en esta Directiva.|
|         |[Requerir equipos *y* dispositivos móviles compatibles](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Incluir equipos y servicios dependientes en esta Directiva.|
|**Extremadamente regulado**|[Requerir *siempre* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Independientemente de la identidad del usuario, la organización usará la MFA. Incluir equipos y servicios dependientes en esta Directiva.
| | |

## <a name="teams-dependent-services-architecture"></a>Arquitectura de servicios dependientes de Teams

Como referencia, el siguiente diagrama ilustra los equipos de servicios en los que se basa. Para obtener más información e ilustraciones adicionales, consulte [Microsoft Teams y los servicios de productividad relacionados en microsoft 365 para arquitectos de ti](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects).

![Diagrama que muestra las dependencias de Teams en SharePoint Online, OneDrive para la empresa y Exchange.](../images/identity-access-logical-architecture-teams.png)

## <a name="enabling-guest-and-external-access-for-teams"></a>Habilitación del acceso externo y de invitado para Microsoft Teams

En Azure AD, los usuarios externos y invitados son los mismos. El tipo de usuario para ambos es invitado. Los usuarios invitados son usuarios B2B. Microsoft Teams diferencia entre los usuarios invitados y los usuarios externos de la aplicación. Aunque es importante comprender cómo se trata cada uno de ellos en Teams, ambos tipos de usuarios son usuarios B2B de Azure AD y las directivas recomendadas para los usuarios B2B se aplican a ambos. Para las directivas recomendadas para permitir el acceso de invitado, consulte [directivas para permitir el acceso de invitado y de B2B externo](identity-access-policies-guest-access.md).

### <a name="guest-access-in-teams"></a>Acceso de invitado en Microsoft Teams

Además de las directivas para los usuarios que son internas a su empresa u organización, los administradores pueden habilitar el acceso de invitado para permitir, de forma individual para cada usuario, que los usuarios externos a su empresa u organización obtengan acceso a los recursos de Microsoft Teams e interactúen con personas internas para cosas como conversaciones de grupo, chat y reuniones. Puede obtener más información sobre el acceso de invitado en el siguiente vínculo: [acceso de invitado de Teams](https://docs.microsoft.com/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Acceso externo en Microsoft Teams

El acceso externo se confunde a veces con el acceso de invitado, por lo que es importante estar claro que estos dos mecanismos de acceso no interno son muy diferentes en realidad. Mientras que el acceso de invitado tiene lugar por usuario (se agrega un usuario cada vez), cuando un administrador habilita el acceso externo, le permite agregar todos los usuarios de un dominio externo al mismo tiempo a teams. Sin embargo, estos usuarios externos tienen menos acceso y funcionalidad que una persona que se agregó mediante el acceso de invitado. Los usuarios de acceso externo pueden chatear con los usuarios internos a través de Teams.

Para obtener más información sobre el acceso externo y cómo implementarlo si es necesario, revise [Manage external Access in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access) .

## <a name="teams-policies"></a>Directivas de Microsoft Teams

Fuera de las directivas comunes enumeradas anteriormente, hay directivas específicas de Microsoft teams que se pueden y deben configurar para administrar diversas funcionalidades de Teams.

### <a name="teams-and-channels-policies"></a>Directivas de Microsoft Teams y Channels

Los equipos y canales son dos elementos que se usan con frecuencia en Microsoft Teams y hay directivas que se pueden aplicar para controlar lo que los usuarios pueden y no pueden hacer cuando usan equipos y canales. Aunque puede crear un equipo global, si su organización tiene 5000 usuarios o menos, es probable que le resulte útil tener equipos y canales más pequeños con fines específicos y en línea con las necesidades de su organización.

Se recomienda cambiar la directiva predeterminada o crear directivas personalizadas y puede obtener más información sobre cómo administrar las directivas en este vínculo: [Manage Teams policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).

### <a name="messaging-policies"></a>Directivas de mensajería

La mensajería o el chat también se pueden administrar a través de la directiva global predeterminada o mediante directivas personalizadas, lo que puede ayudar a los usuarios a comunicarse entre sí de manera adecuada para su organización. Esta información puede revisarse en [Administración de directivas de mensajería en Microsoft Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).

### <a name="meeting-policies"></a>Directivas de reunión

Ninguna discusión de Microsoft Teams estaría completa sin planear e implementar directivas alrededor de las reuniones de Teams. Las reuniones son un componente esencial de Teams, que permite a los usuarios reunirse y presentar de forma formal a muchos usuarios a la vez, así como compartir contenido relevante para la reunión. Es esencial establecer las directivas adecuadas para la organización en relación con las reuniones.

Consulte [Manage Meeting policies in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) para obtener más información.

### <a name="app-permission-policies"></a>Directivas de permisos de aplicaciones

Teams también le permite usar aplicaciones en varios lugares, como canales o chats personales. Contar con directivas alrededor de las aplicaciones que se pueden agregar y usar, y dónde, es esencial para mantener un entorno enriquecido de contenido que también es seguro.

Para obtener más información sobre las directivas de permisos de la aplicación, consulte [Manage App Permission policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).

## <a name="next-steps"></a>Siguientes pasos

[Obtenga información sobre cómo habilitar el acceso condicional para Exchange Online](secure-email-recommended-policies.md)


