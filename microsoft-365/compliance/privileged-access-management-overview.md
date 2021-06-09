---
title: Obtenga más información sobre la administración del acceso con privilegios
description: En este artículo se proporciona información general sobre la administración de acceso con privilegios en Microsoft 365, incluidas las respuestas a las preguntas más frecuentes (preguntas frecuentes).
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
f1.keywords:
- NOCSH
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.openlocfilehash: 059e1653d7db9140dbc80fd69fe36e95a744b079
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126609"
---
# <a name="learn-about-privileged-access-management"></a>Obtenga más información sobre la administración del acceso con privilegios

La administración de acceso con privilegios permite un control de acceso granular sobre las tareas de administración con privilegios en Office 365. Permite proteger la organización ante vulneraciones que puedan usar las cuentas existentes de administrador con privilegios y acceso permanente para acceder a datos confidenciales o a opciones de configuración críticas. Privileged Access Management requiere que los usuarios que deben llevar a cabo tareas con privilegios o privilegios elevados soliciten el acceso de forma puntual a través de un flujo de trabajo de aprobación muy limitado en cuanto al ámbito y al tiempo. Esta configuración proporciona a los usuarios el acceso suficiente para completar la tarea que deban realizar sin arriesgarse a la exposición de datos confidenciales o la configuración crítica. Habilitar la administración de acceso con privilegios en Microsoft 365 permite que su organización funcione con cero privilegios permanentes y proporcione una capa de defensa contra vulnerabilidades de acceso administrativo permanentes.

Para obtener una introducción rápida al flujo de trabajo integrado de administración de acceso con privilegios y caja de seguridad del cliente, vea este vídeo de administración de acceso con privilegios y caja de seguridad [del cliente.](https://go.microsoft.com/fwlink/?linkid=2066800)

## <a name="layers-of-protection"></a>Capas de protección

La administración de acceso con privilegios complementa otras protecciones de características de acceso y datos dentro de la Microsoft 365 de seguridad. La inclusión de la administración de acceso con privilegios como parte de un enfoque integrado y por capas de seguridad proporciona un modelo de seguridad que maximiza la protección de la información confidencial y Microsoft 365 configuración. Como se muestra en el diagrama, la administración de acceso con privilegios se basa en la protección proporcionada con el cifrado nativo de datos de Microsoft 365 y el modelo de seguridad de control de acceso basado en roles de Microsoft 365 servicios. Cuando se usan con [Azure AD Privileged Identity Management,](/azure/active-directory/active-directory-privileged-identity-management-configure)estas dos características proporcionan control de acceso con acceso justo a tiempo en distintos ámbitos.

![Protección por capas en Microsoft 365](../media/pam-layered-protection.png)

La administración de acceso con privilegios se define y se aplica al ámbito  en el nivel de tarea, mientras que Azure AD Privileged Identity Management aplica protección en el nivel de función con la capacidad de ejecutar varias tareas.  Azure AD Privileged Identity Management permite principalmente la administración de accesos para roles y grupos de roles de AD, mientras que Privileged Access Management en Microsoft 365 solo se aplica en el nivel de tarea.

- **Habilitar la administración de acceso con privilegios mientras ya usa Azure AD Privileged Identity Management:** Agregar administración de acceso con privilegios proporciona otra capa granular de capacidades de protección y auditoría para obtener acceso con privilegios a Microsoft 365 datos.

- **Habilitar Azure AD Privileged Identity Management mientras ya se usa la administración de acceso con privilegios en Office 365:**  La adición de Privileged Identity Management de Azure AD a la administración de acceso con privilegios puede extender el acceso con privilegios a los datos fuera de Microsoft 365 que se define principalmente por roles de usuario o identidad.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Arquitectura de administración de acceso con privilegios y flujo de procesos

Cada uno de los siguientes flujos de proceso describe la arquitectura del acceso con privilegios y cómo interactúa con el substrato de Microsoft 365, auditoría y el espacio de ejecución de Exchange administración.

### <a name="step-1-configure-a-privileged-access-policy"></a>Paso 1: Configurar una directiva de acceso con privilegios

Cuando configura una directiva de acceso con privilegios con el Centro de administración de [Microsoft 365](https://admin.microsoft.com) o powerShell de administración de Exchange, define la directiva y los procesos de características de acceso con privilegios y los atributos de directiva en el substrato de Microsoft 365. Las actividades se registran en el Centro de &amp; cumplimiento de seguridad. Ahora la directiva está habilitada y preparada para administrar las solicitudes entrantes para aprobaciones.

![Paso 1: Creación de directivas](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Paso 2: Solicitud de acceso

En el [Microsoft 365 de administración](https://admin.microsoft.com) o con el PowerShell de administración Exchange, los usuarios pueden solicitar acceso a tareas con privilegios o privilegios elevados. La característica de acceso con privilegios envía la solicitud al substrato de Microsoft 365 para su procesamiento con la directiva de acceso a privilegios configurada y registra la actividad en los registros del Centro de &amp; seguridad y cumplimiento.

![Paso 2: Solicitud de acceso](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Paso 3: aprobación del acceso

Se generará una solicitud de aprobación y la notificación de solicitud pendiente se enviará por correo electrónico a los aprobadores. Si se aprueba, la solicitud de acceso con privilegios se procesa como una aprobación y la tarea está lista para completarse. Si se deniega, la tarea se bloquea y no se concede acceso al solicitante. Se notificará al solicitante de la aprobación o denegación de la solicitud por correo electrónico.

![Paso 3: aprobación del acceso](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Paso 4: procesamiento del acceso

Para una solicitud aprobada, la tarea se procesa mediante el espacio de ejecución de la administración de Exchange. La aprobación se comprueba con la directiva de acceso con privilegios y la procesa el sustrato de Microsoft 365. Toda la actividad de la tarea se registra en el Centro de &amp; seguridad y cumplimiento.

![Paso 4: procesamiento del acceso](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>¿Qué SKU pueden usar acceso con privilegios en Office 365?

La administración de acceso con privilegios está disponible para los clientes para una amplia selección de Microsoft 365 y Office 365 suscripciones y complementos. Consulte [Introducción a la administración de acceso con privilegios](privileged-access-management-configuration.md) para obtener más información.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>¿Cuándo admitirá el acceso con privilegios Office 365 cargas de trabajo más allá Exchange?

La administración de acceso con privilegios estará disponible en otras Office 365 de trabajo próximamente. Visite el [Microsoft 365 guía de desarrollo](https://www.microsoft.com/microsoft-365/roadmap) para obtener más información.

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Mi organización necesita más de 30 directivas de acceso con privilegios, ¿se incrementará este límite?

Sí, el aumento del límite actual de 30 directivas de acceso con privilegios por organización está en el mapa de ruta de características.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>¿Necesito ser administrador global para administrar el acceso con privilegios en Office 365?

No, necesita el rol Exchange administración de roles asignado a cuentas que administran el acceso con privilegios en Office 365. Si no desea configurar el rol administración de roles como un permiso de cuenta independiente, el rol Administrador global incluye esta función de forma predeterminada y puede administrar el acceso con privilegios. Los usuarios incluidos en un grupo de aprobadores no necesitan ser administradores globales ni tener asignado el rol administración de roles para revisar y aprobar solicitudes con PowerShell.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>¿Cómo está relacionada la administración de acceso con privilegios con la Caja de seguridad del cliente?

[La caja de seguridad del cliente](/office365/admin/manage/customer-lockbox-requests) permite un nivel de control de acceso para las organizaciones cuando Microsoft accede a los datos. La administración de acceso con privilegios permite un control de acceso granular dentro de una organización para todas Microsoft 365 tareas con privilegios.

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Comience [a configurar su organización para la administración de acceso con privilegios.](privileged-access-management-configuration.md)

## <a name="learn-more"></a>Más información

[Guía interactiva: Supervisar y controlar tareas de administrador con administración de acceso con privilegios](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
