---
title: Obtenga más información sobre la administración del acceso con privilegios
description: En este artículo se proporciona información general sobre la administración del acceso con privilegios en Microsoft 365, incluidas las respuestas a las preguntas más frecuentes (PQ).
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

La administración de acceso con privilegios permite el control de acceso granular sobre las tareas de administración con privilegios en Office 365. Puede ayudar a proteger su organización contra infracciones que usan cuentas de administrador con privilegios existentes con acceso permanente a datos confidenciales o acceso a opciones de configuración críticas. La administración del acceso con privilegios requiere que los usuarios soliciten acceso just-in-time para completar tareas con privilegios elevados y con privilegios a través de un flujo de trabajo de aprobación muy limitado por tiempo y ámbito. Esta configuración proporciona a los usuarios acceso suficiente para realizar la tarea a mano, sin riesgo de exposición de datos confidenciales o opciones de configuración críticas. Habilitar la administración de acceso con privilegios en Microsoft 365 permite que su organización funcione con cero privilegios permanentes y proporcione un nivel de defensa contra vulnerabilidades de acceso administrativo permanentes.

Para obtener información general rápida sobre la Caja de seguridad del cliente integrada y el flujo de trabajo de administración de acceso con privilegios, vea este vídeo sobre la caja de seguridad del cliente y la [administración del acceso con privilegios.](https://go.microsoft.com/fwlink/?linkid=2066800)

## <a name="layers-of-protection"></a>Capas de protección

La administración del acceso con privilegios complementa otras protecciones de características de acceso y datos dentro de la arquitectura de seguridad de Microsoft 365. La inclusión de la administración de acceso con privilegios como parte de un enfoque integrado y en capas de seguridad proporciona un modelo de seguridad que maximiza la protección de información confidencial y las opciones de configuración de Microsoft 365. Como se muestra en el diagrama, la administración de acceso con privilegios se basa en la protección proporcionada con cifrado nativo de datos de Microsoft 365 y el modelo de seguridad de control de acceso basado en roles de los servicios de Microsoft 365. Cuando se usan [con Azure AD Privileged Identity Management,](/azure/active-directory/active-directory-privileged-identity-management-configure)estas dos características proporcionan control de acceso con acceso just-in-time en diferentes ámbitos.

![Protección en capas en Microsoft 365](../media/pam-layered-protection.png)

La administración de acceso con privilegios se define y se define en  el ámbito en el nivel de tarea, mientras que Azure AD Privileged Identity Management aplica protección en el nivel de rol con la capacidad de ejecutar varias tareas.  Azure AD Privileged Identity Management permite principalmente la administración de accesos para roles y grupos de roles de AD, mientras que la administración de acceso con privilegios en Microsoft 365 solo se aplica en el nivel de tareas.

- **Habilitar la administración de acceso con privilegios mientras ya usa Azure AD Privileged Identity Management:** La adición de la administración del acceso con privilegios proporciona otro nivel granular de protección y capacidades de auditoría para el acceso con privilegios a los datos de Microsoft 365.

- **Habilitar Azure AD Privileged Identity Management mientras ya usa la administración de acceso con privilegios en Office 365:**  Agregar Azure AD Privileged Identity Management a la administración de acceso con privilegios puede ampliar el acceso con privilegios a los datos fuera de Microsoft 365 que se define principalmente mediante roles de usuario o identidad.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Arquitectura de administración de acceso con privilegios y flujo de procesos

Cada uno de los siguientes flujos de proceso describe la arquitectura del acceso con privilegios y cómo interactúa con el substrato de Microsoft 365, la auditoría y el espacio de ejecución de administración de Exchange.

### <a name="step-1-configure-a-privileged-access-policy"></a>Paso 1: Configurar una directiva de acceso con privilegios

Cuando configura una directiva de acceso con privilegios con el Centro de administración de [Microsoft 365](https://admin.microsoft.com) o El PowerShell de administración de Exchange, define la directiva y los procesos de características de acceso con privilegios y los atributos de directiva en el substrato de Microsoft 365. Las actividades se registran en el Centro de &amp; cumplimiento de seguridad. La directiva ya está habilitada y lista para controlar las solicitudes entrantes de aprobaciones.

![Paso 1: Creación de directivas](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Paso 2: Solicitud de acceso

En el [Centro de administración de Microsoft 365](https://admin.microsoft.com) o con El PowerShell de administración de Exchange, los usuarios pueden solicitar acceso a tareas con privilegios elevados o con privilegios. La característica de acceso con privilegios envía la solicitud al substrato de Microsoft 365 para procesarla con la directiva de acceso con privilegios configurada y registra la actividad en los registros del Centro de &amp; cumplimiento de seguridad.

![Paso 2: Solicitud de acceso](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Paso 3: Aprobación de acceso

Se genera una solicitud de aprobación y la notificación de solicitud pendiente se envía por correo electrónico a los aprobadores. Si se aprueba, la solicitud de acceso con privilegios se procesa como una aprobación y la tarea está lista para completarse. Si se deniega, la tarea se bloquea y no se concede acceso al solicitante. El solicitante es notificado de la aprobación o denegación de la solicitud a través de un mensaje de correo electrónico.

![Paso 3: Aprobación de acceso](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Paso 4: Procesamiento de acceso

Para una solicitud aprobada, el espacio de ejecución de administración de Exchange procesa la tarea. La aprobación se comprueba con la directiva de acceso con privilegios y se procesa mediante el substrato de Microsoft 365. Toda la actividad de la tarea se registra en el Centro de &amp; cumplimiento de seguridad.

![Paso 4: Procesamiento de acceso](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>¿Qué SKU pueden usar el acceso con privilegios en Office 365?

La administración de acceso con privilegios está disponible para los clientes para una amplia selección de complementos y suscripciones de Microsoft 365 y Office 365. Consulte [Introducción a la administración de acceso con privilegios](privileged-access-management-configuration.md) para obtener más información.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>¿Cuándo admitirá el acceso con privilegios las cargas de trabajo de Office 365 más allá de Exchange?

La administración de acceso con privilegios estará disponible en otras cargas de trabajo de Office 365 próximamente. Para obtener más información, visite el mapa de ruta de [Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Mi organización necesita más de 30 directivas de acceso con privilegios, ¿se incrementará este límite?

Sí, el aumento del límite actual de 30 directivas de acceso con privilegios por organización se encuentra en la guía básica de características.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>¿Necesito ser administrador global para administrar el acceso con privilegios en Office 365?

No, necesita el rol Administración de roles de Exchange asignado a las cuentas que administran el acceso con privilegios en Office 365. Si no desea configurar el rol Administración de roles como un permiso de cuenta independiente, el rol Administrador global incluye este rol de forma predeterminada y puede administrar el acceso con privilegios. Los usuarios incluidos en un grupo de aprobadores no necesitan ser administradores globales ni tener asignado el rol administración de roles para revisar y aprobar solicitudes con PowerShell.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>¿Cómo está relacionada la administración del acceso con privilegios con la Caja de seguridad del cliente?

[La Caja de seguridad del cliente](/office365/admin/manage/customer-lockbox-requests) permite un nivel de control de acceso para las organizaciones cuando Microsoft accede a los datos. La administración de acceso con privilegios permite un control de acceso granular dentro de una organización para todas las tareas con privilegios de Microsoft 365.

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Empiece [a configurar su organización para la administración del acceso con privilegios.](privileged-access-management-configuration.md)

## <a name="learn-more"></a>Más información

[Guía interactiva: Supervisar y controlar tareas de administrador con administración de acceso con privilegios](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
