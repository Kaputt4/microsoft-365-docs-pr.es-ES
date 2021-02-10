---
title: Información sobre el flujo de correo en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Los administradores pueden obtener información sobre las perspectivas y los informes que están disponibles en el panel de flujo de correo en el Centro de & cumplimiento.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b65e235e3446fa62bca1c9f8aef73f2387b1140b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167100"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Reportes de flujo de Correo en el Centro de seguridad y cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Los administradores pueden usar el panel de flujo de correo en el Centro de seguridad y cumplimiento de & para detectar tendencias, información y realizar acciones para solucionar problemas relacionados con el flujo de correo en su organización.

![Panel de flujo de correo en el Centro de & cumplimiento](../../media/mail-flow-dashboard-v2.png)

Las conclusiones disponibles son:

- [Información de mensajes reenviados automáticamente](mfi-auto-forwarded-messages-report.md)

- [Corregir posible información de bucle de correo](mfi-mail-loop-insight.md)<sup>1</sup>

- [Corregir la información de reglas de flujo de correo lentas](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [Mapa de flujo de correo](mfi-mail-flow-map-report.md)

- [Información de correo electrónico de nuevos dominios que se reenvía](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [Nuevos usuarios reenviando la información de correo](mfi-new-users-forwarding-email.md)electrónico<sup>2</sup>

- [Informe de dominios no aceptados](mfi-non-accepted-domain-report.md)

- [Informe de no entrega](mfi-non-delivery-report.md)

- [Información de flujo de correo entrante y saliente](mfi-outbound-and-inbound-mail-flow.md)

- [Información de colas](mfi-queue-alerts-and-queues.md)

- [Información e informes de clientes de autenticación SMTP](mfi-smtp-auth-clients-report.md)

- [Información de estado de flujo de correo de dominio superior](mfi-domain-mail-flow-status-insight.md)

<sup>1 Esta</sup> información aparece en el área Recomendado **para usted** del panel de flujo de correo solo después de detectar el problema. De lo contrario, no lo verás.

<sup>2</sup> Esta información no aparece en el panel de [](view-mail-flow-reports.md#forwarding-report) flujo de correo, pero está visible en la página del informe de reenvío después de detectar el problema. De lo contrario, no lo verás.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Permisos necesarios para ver el panel de flujo de correo

El panel flujo de correo está disponible para los miembros de los siguientes grupos de roles:

- **Administración de la** organización en el Centro de & cumplimiento (administradores globales).

- **[Administrador de Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** en Azure Active Directory.

- **Administrador de flujo de** correo en el Centro de & cumplimiento. Si la cuenta no es también miembro de los grupos de roles Administración de la organización o Administrador de Exchange, tenga en cuenta los siguientes problemas:
  - El usuario debe iniciar sesión en el Centro de seguridad & cumplimiento directamente en <https://protection.office.com> .
  - El usuario solo tendrá permiso de solo lectura en el panel de flujo de correo.
  - El usuario no tendrá acceso al Centro de administración de Microsoft 365.

Para obtener más información acerca de los permisos, vea Permisos en el Centro de seguridad [& Cumplimiento](permissions-in-the-security-and-compliance-center.md) y conceder a los usuarios acceso al Centro de seguridad [& cumplimiento.](grant-access-to-the-security-and-compliance-center.md)

## <a name="where-to-find-the-mail-flow-dashboard"></a>Dónde encontrar el panel de flujo de correo

Abra el Centro de & cumplimiento en , expanda Flujo de <https://protection.office.com> correo y, a continuación, **seleccione Panel.** 

Para ir directamente al panel flujo de correo, abra <https://protection.office.com/mailflow/dashboard> .
