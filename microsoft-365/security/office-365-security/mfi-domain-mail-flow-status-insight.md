---
title: Información de estado del flujo de correo de dominio superior en el panel Flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información sobre el estado del flujo de correo de dominio superior en el panel flujo de correo del Centro de seguridad & cumplimiento para solucionar problemas de flujo de correo relacionados con sus registros MX.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 850e72fa0ad7a3f41450a1d0a2c02dd3df4a0cb5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207551"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Información de estado del flujo de correo de dominio superior en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La **información sobre el** estado [](mail-flow-insights-v2.md) del flujo de correo de dominio superior en el panel Flujo de correo del Centro de seguridad [& cumplimiento](https://protection.office.com) le proporciona el estado del flujo de correo actual de su organización.

Esta información le ayuda a identificar y solucionar problemas de dominios que están experimentando problemas ***de flujo de*** correo. Por ejemplo, el dominio no puede recibir correo electrónico externo porque el dominio ha expirado o el dominio tiene un registro MX incorrecto.

![Widget de estado de flujo de dominio superior en el panel Flujo de correo del Centro de seguridad & cumplimiento](../../media/mfi-top-domain-mail-flow-status-widget.png)

Al hacer clic **en Ver detalles** en el widget, aparece un control flotante Estado del dominio que muestra más detalles sobre el estado de cada dominio: 

- **Dominio**
- **Registro MX anterior**
- **Registro MX actual**
- **Estado de recepción de correo electrónico**
- **Estado del** dominio: una marca de verificación verde indica que el registro MX actual (en el momento en que hizo clic en el widget) coincide con el valor que tenemos en el registro y el dominio ha recibido correo electrónico durante las últimas dos horas.

  Una X roja indica que se ha cambiado el registro MX y que el dominio no ha recibido ningún correo electrónico durante las últimas 6 horas. Esto probablemente indica que el dominio ha expirado o que el registro MX se ha actualizado incorrectamente. Compruebe con el registrador de dominio o el servicio de hospedaje DNS para ver si el dominio ha expirado o si el registro MX del dominio es incorrecto.

Puede hacer clic **en Ver más** para ver la misma información para más dominios.

![Control remoto de detalles en la información de estado del flujo de correo de dominio superior](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Consulte también

Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).
