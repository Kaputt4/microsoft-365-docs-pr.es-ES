---
title: Información sobre el flujo de correo en el panel Flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Los administradores pueden obtener información sobre los conocimientos e informes que están disponibles en el panel flujo de correo en el Centro de seguridad & cumplimiento.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 39f7b43db62fd19f7500972a3016fdd8dd0875b6
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207279"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Reportes de flujo de Correo en el Centro de seguridad y cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Los administradores pueden usar el panel flujo de correo en el Centro de seguridad & cumplimiento para detectar tendencias, información y realizar acciones para solucionar problemas relacionados con el flujo de correo en su organización.

![Panel flujo de correo en el Centro de seguridad & cumplimiento](../../media/mail-flow-dashboard-v2.png)

Las perspectivas disponibles son:

- [Información de mensajes reenviados automáticamente](mfi-auto-forwarded-messages-report.md)

- [Corregir posibles perspectivas de bucle de correo](mfi-mail-loop-insight.md)<sup>1</sup>

- [Corregir la información de reglas de flujo de correo lento](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [Mapa de flujo de correo](mfi-mail-flow-map-report.md)

- [Nuevos dominios que se reenviarán información de correo](mfi-new-domains-being-forwarded-email.md)<sup>electrónico 2</sup>

- [Nuevos usuarios reenviar información de correo electrónico](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [Informe de dominios no aceptados](mfi-non-accepted-domain-report.md)

- [Informe de no entrega](mfi-non-delivery-report.md)

- [Información de flujo de correo entrante y saliente](mfi-outbound-and-inbound-mail-flow.md)

- [Información de colas](mfi-queue-alerts-and-queues.md)

- [Información e informes de clientes de autenticación SMTP](mfi-smtp-auth-clients-report.md)

- [Información de estado de flujo de correo de dominio superior](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> Esta información aparece en **el** área Recomendado para usted del panel flujo de correo solo después de detectar el problema. De lo contrario, no lo verá.

<sup>2</sup> Esta información no aparece en el panel flujo [](view-mail-flow-reports.md#forwarding-report) de correo, pero está visible en la página Informe de reenvío después de detectar el problema. De lo contrario, no lo verá.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Permisos necesarios para ver el panel flujo de correo

El panel flujo de correo está disponible para los miembros de los siguientes grupos de roles:

- **Administración de la** organización en el Centro de & seguridad (administradores globales).

- **[Administrador de Exchange](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** en Azure Active Directory.

- **Administrador de MailFlow** en el Centro de seguridad & cumplimiento. Si la cuenta no es también miembro de los grupos de roles Administración de la organización o Administrador de Exchange, tenga en cuenta los siguientes problemas:
  - El usuario debe iniciar sesión en el Centro de seguridad & cumplimiento directamente en <https://protection.office.com> .
  - El usuario solo tendrá permiso de solo lectura para el panel flujo de correo.
  - El usuario no tendrá acceso al Centro de administración de Microsoft 365.

Para obtener más información acerca de los permisos, vea Permisos en el Centro de seguridad [& cumplimiento](permissions-in-the-security-and-compliance-center.md) y Conceder a los usuarios acceso al Centro de seguridad [& cumplimiento](grant-access-to-the-security-and-compliance-center.md).

## <a name="where-to-find-the-mail-flow-dashboard"></a>Dónde encontrar el panel flujo de correo

Abra el Centro de seguridad & cumplimiento en <https://protection.office.com> , expanda Flujo de **correo** y, a continuación, **seleccione Panel**.

Para ir directamente al panel flujo de correo, abra <https://protection.office.com/mailflow/dashboard> .