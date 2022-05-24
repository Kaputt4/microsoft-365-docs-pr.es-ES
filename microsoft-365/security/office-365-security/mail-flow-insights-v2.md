---
title: Información de flujo de correo en el panel Flujo de correo
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: overview
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Los administradores pueden obtener información sobre la información y los informes que están disponibles en el panel Flujo de correo del Centro de cumplimiento de seguridad &.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5850612fbd0de89e5eafe101f55d368b0f4b0c8f
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "65648731"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Reportes de flujo de Correo en el Centro de seguridad y cumplimiento

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Los administradores pueden usar el panel flujo de correo en el Centro de cumplimiento de seguridad & para detectar tendencias, información y realizar acciones para corregir problemas relacionados con el flujo de correo en su organización.

:::image type="content" source="../../media/mail-flow-dashboard-v2.png" alt-text="Panel flujo de correo en el Centro de cumplimiento de seguridad &" lightbox="../../media/mail-flow-dashboard-v2.png":::

Las conclusiones disponibles son:

- [Información de mensajes reenviados automáticamente](mfi-auto-forwarded-messages-report.md)
- [Corrección de la posible información del bucle de correo1](mfi-mail-loop-insight.md)<sup></sup>
- [Corrección de la información de reglas de flujo de correo lenta1](mfi-slow-mail-flow-rules-insight.md)<sup></sup>
- [Mapa de flujo de correo](mfi-mail-flow-map-report.md)
- [Nuevos dominios que se reenvía información de correo electrónico2](mfi-new-domains-being-forwarded-email.md)<sup></sup>
- [Nuevos usuarios que reenvía información de correo electrónico2](mfi-new-users-forwarding-email.md)<sup></sup>
- [Informe de dominios no aceptados](mfi-non-accepted-domain-report.md)
- [Informe de no entrega](mfi-non-delivery-report.md)
- [Información de flujo de correo entrante y saliente](mfi-outbound-and-inbound-mail-flow.md)
- [Información de colas](mfi-queue-alerts-and-queues.md)
- [Información e informes de clientes de autenticación SMTP](mfi-smtp-auth-clients-report.md)
- [Información de estado de flujo de correo de dominio superior](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> Esta información aparece en el área **Recomendado para usted** del panel Flujo de correo solo después de que se detecte el problema. De lo contrario, no lo verás.

<sup>2</sup> Esta información no aparece en el panel Flujo de correo, pero está visible en la página [Del informe de reenvío](view-mail-flow-reports.md#forwarding-report) una vez detectado el problema. De lo contrario, no lo verás.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Permisos necesarios para ver el panel flujo de correo

El panel Flujo de correo está disponible para los miembros de los siguientes grupos de roles:

- **Administración de la organización** en el Centro de cumplimiento de seguridad & (administradores globales).

- **[Exchange Administrador](/azure/active-directory/roles/permissions-reference#exchange-administrator)** en Azure Active Directory.

- **Administrador de MailFlow** en el Centro de cumplimiento de seguridad &. Si la cuenta no es también miembro de los grupos de roles Administración de la organización o Administrador de Exchange, tenga en cuenta los siguientes problemas:
  - El usuario debe iniciar sesión en el Centro de cumplimiento de seguridad & directamente en <https://protection.office.com>.
  - El usuario solo tendrá permiso de solo lectura para el panel flujo de correo.
  - El usuario no tendrá acceso al Centro de administración de Microsoft 365.

Para obtener más información sobre los permisos, vea [Permisos en el Centro de cumplimiento de seguridad &](permissions-in-the-security-and-compliance-center.md) y [Proporcionar a los usuarios acceso al Centro de cumplimiento de seguridad &](grant-access-to-the-security-and-compliance-center.md).

## <a name="where-to-find-the-mail-flow-dashboard"></a>Dónde encontrar el panel flujo de correo

Para ir directamente al panel Flujo de correo, abra <https://protection.office.com/mailflow/dashboard>.
