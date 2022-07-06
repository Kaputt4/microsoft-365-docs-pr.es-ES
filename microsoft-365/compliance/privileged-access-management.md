---
title: Obtenga más información sobre la administración del acceso con privilegios
description: En este artículo se proporciona información general sobre la administración de acceso con privilegios en Microsoft Purview, incluidas las respuestas a las preguntas más frecuentes (P+F).
keywords: Microsoft 365, Microsoft Purview, cumplimiento, administración de acceso con privilegios
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
f1.keywords:
- NOCSH
ms.service: O365-seccomp
ms.localizationpriority: medium
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
ms.openlocfilehash: 6bf13adb96ae5d4d4030ebe44f10dab22602196e
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66622555"
---
# <a name="learn-about-privileged-access-management"></a>Obtenga más información sobre la administración del acceso con privilegios

Microsoft Purview Privileged Access Management permite el control de acceso pormenorizado sobre las tareas de administración con privilegios en Office 365. Permite proteger la organización ante vulneraciones que puedan usar las cuentas existentes de administrador con privilegios y acceso permanente para acceder a datos confidenciales o a opciones de configuración críticas. Privileged Access Management requiere que los usuarios que deben llevar a cabo tareas con privilegios o privilegios elevados soliciten el acceso de forma puntual a través de un flujo de trabajo de aprobación muy limitado en cuanto al ámbito y al tiempo. Esta configuración proporciona a los usuarios el acceso suficiente para completar la tarea que deban realizar sin arriesgarse a la exposición de datos confidenciales o la configuración crítica. La habilitación de la administración de acceso con privilegios permite que su organización funcione con privilegios permanentes y proporcione una capa de defensa frente a vulnerabilidades de acceso administrativo permanentes.

Para obtener información general rápida sobre la caja de seguridad del cliente integrada y el flujo de trabajo de administración de acceso con privilegios, consulte este [vídeo de administración de acceso con privilegios y caja de seguridad del cliente](https://go.microsoft.com/fwlink/?linkid=2066800).

## <a name="layers-of-protection"></a>Capas de protección

Privileged Access Management complementa otras protecciones de características de acceso y datos dentro de la arquitectura de Seguridad de Microsoft 365. Incluir Privileged Access Management como parte de un enfoque integrado y por niveles de seguridad proporciona un modelo de seguridad que maximiza la protección de la información confidencial y las opciones de configuración de Microsoft 365. Como se muestra en el diagrama, Privileged Access Management se basa en la protección proporcionada con el cifrado nativo de datos de Microsoft 365 y el modelo de seguridad del control de acceso basado en roles de los servicios de Microsoft 365. Cuando se usan con [azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure), estas dos características proporcionan control de acceso con acceso Just-In-Time en ámbitos diferentes.

![Protección por capas en Microsoft 365.](../media/pam-layered-protection.png)

La administración del acceso con privilegios se define y se limita al nivel de **tarea**, mientras que Azure AD Privileged Identity Management aplica protección en el nivel de **rol** con la capacidad de ejecutar varias tareas. Azure AD Privileged Identity Management permite principalmente la administración de accesos para roles y grupos de roles de AD, mientras que Microsoft Purview Privileged Access Management solo se aplica en el nivel de tarea.

- **Habilitación de la administración de acceso con privilegios mientras ya se usa azure AD Privileged Identity Management:** la adición de la administración de acceso con privilegios proporciona otra capa granular de funcionalidades de protección y auditoría para el acceso con privilegios a los datos de Microsoft 365.

- **Habilitación de Azure AD Privileged Identity Management mientras ya se usa Microsoft Purview Privileged Access Management:** la adición de Privileged Identity Management de Azure AD a Microsoft Purview Privileged Access Management puede ampliar el acceso con privilegios a datos fuera de Microsoft 365 definidos principalmente por roles de usuario o identidad .  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Arquitectura de administración de acceso con privilegios y flujo de procesos

Cada uno de los flujos de proceso siguientes describe la arquitectura del acceso con privilegios y cómo interactúa con el sustrato de Microsoft 365, la auditoría y el espacio de ejecución de administración de Exchange.

### <a name="step-1-configure-a-privileged-access-policy"></a>Paso 1: Configurar una directiva de acceso con privilegios

Al configurar una directiva de acceso con privilegios con el [Centro de administración de Microsoft 365](https://admin.microsoft.com) o PowerShell de administración de Exchange, se define la directiva y los procesos de características de acceso con privilegios y los atributos de directiva en el sustrato de Microsoft 365. Las actividades se registran en el Centro de cumplimiento de seguridad &amp; . Ahora la directiva está habilitada y preparada para administrar las solicitudes entrantes para aprobaciones.

![Paso 1: Creación de directivas.](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Paso 2: Solicitud de acceso

En el [Centro de administración de Microsoft 365](https://admin.microsoft.com) o con PowerShell de administración de Exchange, los usuarios pueden solicitar acceso a tareas con privilegios elevados o con privilegios. La característica de acceso con privilegios envía la solicitud al sustrato de Microsoft 365 para su procesamiento en la directiva de acceso con privilegios configurada y registra la actividad en los registros del Centro de cumplimiento de seguridad &amp; .

![Paso 2: Solicitud de acceso.](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Paso 3: aprobación del acceso

Se generará una solicitud de aprobación y la notificación de solicitud pendiente se enviará por correo electrónico a los aprobadores. Si se aprueba, la solicitud de acceso con privilegios se procesa como una aprobación y la tarea está lista para completarse. Si se deniega, la tarea se bloquea y no se concede acceso al solicitante. Se notificará al solicitante de la aprobación o denegación de la solicitud por correo electrónico.

![Paso 3: Aprobación de acceso.](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Paso 4: procesamiento del acceso

Para una solicitud aprobada, la tarea se procesa mediante el espacio de ejecución de la administración de Exchange. La aprobación se comprueba con la directiva de acceso con privilegios y la procesa el sustrato de Microsoft 365. Toda la actividad de la tarea se registra en el Centro de cumplimiento de seguridad &amp; .

![Paso 4: Procesamiento de acceso.](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>¿Qué SKU pueden usar el acceso con privilegios en Office 365?

La administración de acceso con privilegios está disponible para los clientes para una amplia selección de suscripciones y complementos de Microsoft 365 y Office 365. Consulte [Introducción a la administración de acceso con privilegios](privileged-access-management-configuration.md) para obtener más información.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>¿Cuándo admitirá el acceso con privilegios Office 365 cargas de trabajo más allá de Exchange?

La administración de acceso con privilegios estará disponible pronto en otras cargas de trabajo de Office 365. Visite la [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obtener más detalles.

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Mi organización necesita más de 30 directivas de acceso con privilegios, ¿se aumentará este límite?

Sí, el aumento del límite actual de 30 directivas de acceso con privilegios por organización está en la hoja de ruta de características.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>¿Debo ser un Administración global para administrar el acceso con privilegios en Office 365?

No, necesita el rol administración de roles de Exchange asignado a las cuentas que administran el acceso con privilegios en Office 365. Si no desea configurar el rol De administración de roles como un permiso de cuenta independiente, el rol Administrador global incluye este rol de forma predeterminada y puede administrar el acceso con privilegios. Los usuarios incluidos en el grupo de aprobadores no necesitan ser un Administración global ni tener asignado el rol De administración de roles para revisar y aprobar solicitudes con PowerShell.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>¿Cómo se relaciona la administración de acceso con privilegios con la caja de seguridad del cliente?

[La caja de seguridad del cliente](/office365/admin/manage/customer-lockbox-requests) permite un nivel de control de acceso para las organizaciones cuando Microsoft accede a los datos. La administración de acceso con privilegios permite el control de acceso pormenorizado dentro de una organización para todas las tareas con privilegios de Microsoft 365.

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Empiece [a configurar la organización para la administración de acceso con privilegios](privileged-access-management-configuration.md).

## <a name="learn-more"></a>Más información

[Guía interactiva: Supervisión y control de tareas de administrador con administración de acceso con privilegios](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
