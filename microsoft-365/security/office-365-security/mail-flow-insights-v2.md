---
title: Información sobre el flujo de correo en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Los administradores pueden obtener información sobre las opiniones y los informes que están disponibles en el panel del flujo de correo en el centro de seguridad & cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9ac8b8b0d346d78af252a9e427d0ef2b1a4c4ea
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769023"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Reportes de flujo de Correo en el Centro de seguridad y cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Los administradores pueden usar el panel de flujo de correo en el centro de seguridad & cumplimiento para descubrir tendencias, información y emprender acciones para corregir problemas relacionados con el flujo de correo en su organización.

![Panel del flujo de correo en el centro de seguridad & cumplimiento](../../media/mail-flow-dashboard-v2.png)

Los conocimientos disponibles son los siguientes:

- [Información de mensajes reenviados automáticamente](mfi-auto-forwarded-messages-report.md)

- [Revisión de la información posible del bucle de correo](mfi-mail-loop-insight.md)<sup>1</sup>

- [Corrección de las reglas de flujo de correo lenta Insight](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [Mapa de flujo de correo](mfi-mail-flow-map-report.md)

- [Nuevos dominios que se reenvían correo electrónico Insight](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [Nuevos usuarios reenvío de correo electrónico Insight](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [Informe de dominios no aceptados](mfi-non-accepted-domain-report.md)

- [Informe de no entrega](mfi-non-delivery-report.md)

- [Información de flujo de correo entrante y saliente](mfi-outbound-and-inbound-mail-flow.md)

- [Información de colas](mfi-queue-alerts-and-queues.md)

- [Información e informes de clientes de autenticación SMTP](mfi-smtp-auth-clients-report.md)

- [Información de estado de flujo de correo de dominio superior](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> esta información aparece en el área **recomendada para** el panel del flujo de correo solo después de que se detecte el problema. De lo contrario, no lo verá.

<sup>2</sup> esta información no aparece en el panel de flujo de correo, pero es visible en la página del [Informe de reenvío](view-mail-flow-reports.md#forwarding-report) después de que se detecte el problema. De lo contrario, no lo verá.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Permisos necesarios para ver el panel de flujo de correo

El panel de flujo de correo está disponible para los miembros de los siguientes grupos de roles:

- **Administración** de la organización en el centro de seguridad & cumplimiento (administradores globales).

- **[Administrador de Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** en Azure Active Directory.

- **Administrador de flujo** de trabajo en el centro de cumplimiento de & de seguridad: Si un miembro de este grupo de roles no es también miembro de los grupos de roles de administrador global o administrador de Exchange, tenga en cuenta los siguientes problemas y requisitos:

  - El usuario debe iniciar sesión en el centro de seguridad & cumplimiento directamente en <https://protection.office.com> .
  - El usuario solo tendrá permiso de solo lectura en el panel de flujo de correo.
  - El usuario no tendrá acceso al centro de administración de Microsoft 365.

Para obtener más información acerca de los permisos en el centro de seguridad & cumplimiento, consulte [permisos en el centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md) y [proporcionar a los usuarios acceso al centro de seguridad & cumplimiento](grant-access-to-the-security-and-compliance-center.md).

## <a name="where-to-find-the-mail-flow-dashboard"></a>Dónde encontrar el panel de flujo de correo

Abra el centro de seguridad & cumplimiento en <https://protection.office.com> , expanda **flujo de correo** y, a continuación, seleccione **Panel** .

Para ir directamente al panel de flujo de correo, Abra <https://protection.office.com/mailflow/dashboard> .
