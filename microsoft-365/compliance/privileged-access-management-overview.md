---
title: Privileged Access Management
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
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
ms.assetid: ''
description: En este artículo se proporciona información general sobre la administración del acceso con privilegios en Microsoft 365, incluidas las respuestas a las preguntas más frecuentes (p + f).
ms.openlocfilehash: a1bcf1fbe767b4657be8a8ebcc8bf7b101c498d8
ms.sourcegitcommit: 79a21583a52aedd06317bbcabd8be40663379dec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341238"
---
# <a name="privileged-access-management"></a>Privileged Access Management

La administración de acceso privilegiado permite un control de acceso granular sobre las tareas de administración con privilegios en Office 365. Puede ayudar a proteger a su organización de las infracciones que usan cuentas de administrador con privilegios existentes con acceso permanente a los datos confidenciales o al acceso a las opciones de configuración críticas. La administración de acceso privilegiado requiere que los usuarios soliciten acceso puntual para completar las tareas elevadas y privilegiadas a través de un flujo de trabajo de aprobación limitado por el ámbito y de gran alcance. Esta configuración proporciona a los usuarios un acceso suficiente para realizar la tarea a mano, sin arriesgar la exposición de los datos confidenciales o las opciones de configuración críticas. La habilitación de la administración de acceso privilegiada en Microsoft 365 permite que su organización opere con privilegios que no tienen ningún derecho y proporciona un nivel de defensa contra las vulnerabilidades de acceso administrativo.

Para obtener una introducción rápida a los flujos de trabajo de clientes integrados y el flujo de trabajo de administración de acceso privilegiado, consulte este [vídeo de caja de control de acceso de cliente y acceso privilegiado](https://go.microsoft.com/fwlink/?linkid=2066800).

## <a name="layers-of-protection"></a>Niveles de protección

La administración de acceso privilegiada complementa a otros datos y otras protecciones de características de la arquitectura de seguridad de Microsoft 365. La inclusión de la administración de acceso privilegiada como parte de un enfoque integrado y por capas de la seguridad proporciona un modelo de seguridad que maximiza la protección de la información confidencial y las opciones de configuración de Microsoft 365. Como se muestra en el diagrama, la administración del acceso con privilegios se basa en la protección proporcionada con el cifrado nativo de los datos de Microsoft 365 y el modelo de seguridad de control de acceso basado en roles de los servicios de Microsoft 365. Cuando se usan con [Azure ad privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), estas dos características proporcionan control de acceso con acceso Just-in-Time en diferentes ámbitos.

![Protección por niveles en Microsoft 365](../media/pam-layered-protection.png)

La administración del acceso con privilegios se define y se limita en el nivel de la **tarea** , mientras que la administración de identidades de Azure ad privilegiada aplica protección a nivel de **rol** con la capacidad de ejecutar varias tareas. Azure AD privileged Identity Management permite básicamente administrar los accesos para los grupos de roles y roles de AD, mientras que la administración de acceso privilegiada en Microsoft 365 solo se aplica en el nivel de tarea.

- **Habilitación de la administración de acceso privilegiado mientras se usa Azure ad privileged Identity Management:** Agregar administración de acceso privilegiada proporciona otra capa granular de capacidades de protección y auditoría para el acceso privilegiado a los datos de Microsoft 365.

- **Habilitación de la administración de identidades privilegiada de Azure ad mientras se usa la administración de acceso con privilegios en Office 365:**  La adición de la administración de identidades privilegiada de Azure AD a la administración de acceso privilegiada puede ampliar el acceso privilegiado a datos externos a Microsoft 365 que se definen principalmente por los roles de usuario o la identidad.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Arquitectura de administración del acceso privilegiado y flujo del proceso

Cada uno de los siguientes flujos de proceso describe la arquitectura de acceso privilegiado y el modo en que interactúa con el sustrato de Microsoft 365, la auditoría y el espacio de ejecución de administración de Exchange.

### <a name="step-1-configure-a-privileged-access-policy"></a>Paso 1: configurar una directiva de acceso privilegiado

Cuando se configura una directiva de acceso privilegiado con el [centro de administración de Microsoft 365](https://admin.microsoft.com) o PowerShell de administración de Exchange, se define la Directiva y los procesos de características de acceso privilegiado y los atributos de directiva en el sustrato de Microsoft 365. Las actividades se registran en el centro de seguridad y &amp; cumplimiento. La Directiva está ahora habilitada y lista para administrar las solicitudes entrantes para aprobaciones.

![Paso 1: creación de la Directiva](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Paso 2: solicitud de acceso

En el [centro de administración de Microsoft 365](https://admin.microsoft.com) o con PowerShell de administración de Exchange, los usuarios pueden solicitar acceso a tareas elevadas o privilegiadas. La característica de acceso privilegiado envía la solicitud al sustrato de 365 de Microsoft para su procesamiento con respecto a la Directiva configurada de acceso a privilegios y registra la actividad en los registros del centro de cumplimiento de seguridad &amp; .

![Paso 2: solicitud de acceso](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Paso 3: aprobación de acceso

Se genera una solicitud de aprobación y la notificación de solicitud pendiente se envíe por correo electrónico a los aprobadores. Si se aprueba, la solicitud de acceso privilegiado se procesa como una aprobación y la tarea está lista para completarse. Si se deniega, la tarea se bloqueará y no se concederá acceso al solicitante. El solicitante recibe la notificación de la aprobación o la denegación de la solicitud mediante un mensaje de correo electrónico.

![Paso 3: aprobación de acceso](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Paso 4: acceso al procesamiento

Para una solicitud aprobada, el espacio de ejecución de administración de Exchange procesa la tarea. La aprobación se comprueba contra la Directiva de acceso privilegiado y la procesa el sustrato 365 de Microsoft. Toda la actividad de la tarea se registra en el centro de seguridad y &amp; cumplimiento.

![Paso 4: acceso al procesamiento](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>¿Qué SKU puede usar el acceso con privilegios en Office 365?

La administración del acceso con privilegios está disponible para los clientes para una amplia selección de suscripciones y complementos de Microsoft 365 y Office 365. Consulte [Get Started with privileged Access Management](privileged-access-management-configuration.md) para obtener más información.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>¿Cuándo será compatible el acceso a Office 365 cargas de trabajo de Office más allá de Exchange?

La administración del acceso privilegiado estará disponible en otras cargas de trabajo de Office 365 pronto. Visite el [mapa de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obtener más información.

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Mi organización necesita más de 30 directivas de acceso privilegiadas, ¿aumentará este límite?

Sí, aumentar el límite actual de 30 directivas de acceso con privilegios por organización se encuentra en la guía básica de características.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>¿Es necesario ser administrador global para administrar el acceso con privilegios en Office 365?

No, necesita la función de administración de roles de Exchange asignada a cuentas que administran el acceso privilegiado en Office 365. Si no desea configurar el rol de administración de roles como un permiso de cuenta independiente, el rol de administrador global incluye esta función de forma predeterminada y puede administrar el acceso privilegiado. Los usuarios incluidos en un grupo de aprobadores no tienen que ser administrador global o tener el rol de administración de roles asignado para revisar y aprobar solicitudes con PowerShell.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>¿Cómo se relaciona la administración del acceso con privilegios con las cajas de caja del cliente?

[Caja de caja del cliente](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) permite un nivel de control de acceso para las organizaciones cuando Microsoft obtiene acceso a los datos. La administración de acceso privilegiado permite un control de acceso granular dentro de una organización para todas las tareas privilegiadas de Microsoft 365.

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Inicie [la configuración de la organización para la administración del acceso privilegiado](privileged-access-management-configuration.md).

## <a name="learn-more"></a>Más información

[Guía interactiva: supervise y controle las tareas de administrador con privilegios de administración de acceso](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
