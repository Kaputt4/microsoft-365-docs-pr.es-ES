---
title: Personalizar las aplicaciones de Teams para sus trabajadores de primera línea
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Obtenga información sobre la experiencia de aplicación personalizada para los trabajadores de primera línea en Microsoft Teams.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: debc8a975d132c83183fce4a4f0d4f6905dcbb40
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2022
ms.locfileid: "68565988"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>Personalizar las aplicaciones de Teams para sus trabajadores de primera línea

## <a name="overview"></a>Información general

Teams ancla aplicaciones basadas en la licencia para proporcionar a los trabajadores de primera línea una experiencia rápida en Teams adaptada a sus necesidades. 

Con la experiencia de aplicación de primera línea personalizada, los trabajadores de primera línea obtienen las aplicaciones más relevantes en Teams sin que el administrador necesite ninguna acción.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4VuCH]

## <a name="tailored-frontline-app-experience"></a>Experiencia de aplicación de primera línea personalizada

La aplicaciones se anclan a la barra de aplicaciones. Esta es la barra situada en el lateral del cliente de escritorio de Teams y en la parte inferior de los clientes móviles (iOS y Android). Las siguientes aplicaciones están ancladas para los usuarios que tienen una [licencia F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt):

- [Conexiones Viva](https://support.microsoft.com/office/your-intranet-is-now-in-microsoft-teams-8b4e7f76-f305-49a9-b6d2-09378476f95b) ([próximamente](#coming-soon))
- [Actividad](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [Chat](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Tasks](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Turnos](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [Aprobaciones](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams para dispositivos móviles**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="La experiencia de aplicación de primera línea personalizada en dispositivos móviles de Teams" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Escritorio de Teams**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="La experiencia de aplicación de primera línea personalizada en el escritorio de Teams" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>Controles de administración

> [!NOTE]
> La configuración **de anclaje de usuario** debe estar activada en la [directiva de configuración de la aplicación](/microsoftteams/teams-app-setup-policies) global (predeterminada para toda la organización) para que esta característica surta efecto.

La experiencia de la aplicación de primera línea personalizada se controla mediante la configuración **Mostrar aplicaciones adaptadas** para toda la organización en la página [Administrar aplicaciones](/microsoftteams/manage-apps#manage-org-wide-app-settings) del Centro de administración de Teams. Si la característica está activada, todos los usuarios de su organización que tengan una licencia F obtendrán la experiencia de aplicación personalizada.

Tenga en cuenta que las [directivas de configuración de aplicaciones](/microsoftteams/teams-app-setup-policies) personalizadas asignadas a los usuarios tienen prioridad. Esto significa que si un usuario ya tiene asignada una directiva de configuración de aplicación personalizada, el usuario obtiene la configuración definida en la directiva de configuración de la aplicación personalizada. Para obtener más información sobre cómo funciona la característica con las [directivas](#scenarios) de aplicaciones de Teams, incluida la directiva de configuración de aplicaciones global, consulte la sección Escenarios más adelante en este artículo.

Esta característica está activada de forma predeterminada. Sin embargo, si no desea la experiencia de aplicación de primera línea adaptada proporcionada por Microsoft, puede desactivar la característica. Para activar o desactivar la característica:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones** y, a continuación, seleccione **Configuración de aplicaciones para toda la organización**.
2. En **Aplicaciones personalizadas**, cambie el botón **Mostrar aplicaciones personalizadas** a **Desactivado** o **Activado**.

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Captura de pantalla de la configuración Mostrar aplicaciones personalizadas en la página Administrar aplicaciones del Centro de administración de Teams" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>Escenarios

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>¿Cómo afecta la experiencia de la aplicación de primera línea personalizada a mi directiva de configuración global de aplicaciones?

Obtenga información sobre cómo funciona la experiencia de la aplicación de primera línea personalizada junto con la directiva de configuración de aplicaciones global. Los escenarios de esta tabla se aplican a los trabajadores de primera línea que tienen una licencia F y la directiva de configuración de aplicaciones global, con **el anclaje de usuario** activado.

|Si... |Entonces... |
|---------|---------|
|Un trabajador de primera línea tiene la directiva de configuración de la aplicación global y la característica está desactivada. |El trabajador de primera línea obtiene las aplicaciones definidas en la directiva de configuración global de aplicaciones.|
|Un trabajador de primera línea tiene la directiva de configuración de la aplicación global y la característica está activada.     | El trabajador de primera línea obtiene la experiencia de aplicación de primera línea personalizada. Las aplicaciones definidas en la directiva de configuración global de aplicaciones se anclan debajo de las aplicaciones personalizadas.      |
|Actualice la directiva de configuración de la aplicación global y la característica está activada.     |El trabajador de primera línea obtiene la experiencia de aplicación de primera línea adaptada y las aplicaciones definidas en la directiva de configuración global de aplicaciones se anclan debajo de las aplicaciones adaptadas.         |
|Un trabajador de primera línea tiene la directiva de configuración de la aplicación global y el **anclaje de usuarios** está desactivado. |El trabajador de primera línea obtiene las aplicaciones definidas en la directiva de configuración global de aplicaciones.|
|Un trabajador de primera línea tiene la directiva de configuración global de la aplicación y la directiva de configuración global de la aplicación se cambia para incluir una aplicación de línea de negocio (LOB) en la segunda posición de la lista de aplicaciones. |La aplicación LOB está anclada debajo de las aplicaciones personalizadas. El trabajador de primera línea puede cambiar el orden de la aplicación si el **anclaje de usuario** está activado.         |
|Un trabajador de primera línea tiene la directiva de configuración global y la directiva de configuración global de la aplicación se cambia para incluir turnos en la primera posición.  |Los turnos se anclan a la sexta posición, tal como se define en la experiencia de la aplicación de primera línea personalizada. El trabajador de primera línea puede cambiar el orden de la aplicación si el **anclaje de usuario** está activado.          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>¿Cómo funciona la experiencia de la aplicación de primera línea personalizada con otras directivas de aplicaciones de Teams?

Obtenga información sobre cómo funciona la experiencia de la aplicación de primera línea personalizada con otras directivas de aplicaciones de Teams.

|Si...  |Entonces... |
|---------|---------|
La característica está desactivada.   | El trabajador de primera línea obtiene las aplicaciones definidas en la directiva de configuración de aplicaciones global o en la directiva de configuración de aplicaciones personalizada asignada a ellas.          |
|Un trabajador de primera línea tiene una directiva de configuración de aplicación personalizada y la característica está activada.    |El trabajador de primera línea obtiene las aplicaciones definidas en la directiva de configuración de aplicaciones personalizada.          |
|Una aplicación de la experiencia de aplicación de primera línea personalizada está bloqueada para un usuario o para su organización.      |La experiencia de aplicación de primera línea adaptada respeta la [directiva de permisos de la aplicación](/microsoftteams/teams-app-permission-policies). Si se bloquea una aplicación, el trabajador de primera línea no verá la aplicación bloqueada.           |
|Una aplicación de la experiencia de aplicación de primera línea personalizada ya está definida en una directiva de configuración de aplicaciones y la característica está activada. |La aplicación se ancla en función del orden definido por la lista de aplicaciones adaptadas.        |
|Un usuario tiene una licencia E, A o G y la característica está activada.   | El usuario no obtiene la experiencia de aplicación de primera línea personalizada. Actualmente, la experiencia solo se aplica a los usuarios que tienen una licencia F.        |

> [!NOTE]
> No puede cambiar las aplicaciones ni el orden de las aplicaciones en la experiencia de aplicación de primera línea personalizada. Por ahora, si desea realizar cambios, puede configurar su propia experiencia personalizada. Para ello, primero desactive la característica. A continuación, [cree una directiva de configuración de aplicación personalizada](/microsoftteams/teams-app-setup-policies) y [asígnela a usuarios o grupos](/microsoftteams/assign-policies-users-and-groups).

### <a name="coming-soon"></a>Próximamente

 Conexiones Viva pronto formará parte de la experiencia de aplicaciones personalizadas de primera línea. Los usuarios de primera línea que vean la experiencia de aplicación personalizada tendrán Conexiones Viva anclados en la primera posición tanto en dispositivos móviles como de escritorio.

Esta experiencia incluye un panel predeterminado con tarjetas de primera línea relevantes como Tareas, Turnos, Aprobaciones y Noticias principales que se pueden personalizar para satisfacer las necesidades de su organización. Si su organización ya ha configurado un Conexiones Viva sitio principal, tendrá prioridad sobre la experiencia predeterminada. Para obtener más información, consulte la [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=99706).

**Teams para dispositivos móviles**

:::image type="content" source="media/tailored-teams-apps-viva-connections-mobile.png" alt-text="Captura de pantalla que muestra Conexiones Viva en la experiencia de aplicación de primera línea personalizada en teams mobile." lightbox="media/tailored-teams-apps-viva-connections-mobile.png":::

**Escritorio de Teams**

:::image type="content" source="media/tailored-teams-apps-viva-connections-desktop.png" alt-text="Captura de pantalla que muestra Conexiones Viva en la experiencia de aplicación de primera línea personalizada en el escritorio de Teams." lightbox="media/tailored-teams-apps-viva-connections-desktop.png":::

## <a name="related-articles"></a>Artículos relacionados

- [Administrar la aplicación Walkie Talkie](/microsoftteams/walkie-talkie?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Administrar la aplicación Tareas en Teams](/microsoftteams/manage-tasks-app?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Administrar la aplicación Turnos en Teams](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Administrar la aplicación Aprobaciones en Microsoft Teams](/microsoftteams/approval-admin?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Administrar directivas de configuración de aplicación en Teams](/microsoftteams/teams-app-setup-policies)
- [Administrar directivas de permisos de aplicación en Teams](/microsoftteams/teams-app-permission-policies)
