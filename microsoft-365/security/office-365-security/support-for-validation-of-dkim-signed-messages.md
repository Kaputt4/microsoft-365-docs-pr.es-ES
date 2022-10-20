---
title: Compatibilidad con la validación de mensajes firmados de Correo identificado de claves de dominio (DKIM)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- m365-security
description: Obtenga información sobre la validación de mensajes firmados de DKIM en Exchange Online Protection y Exchange Online
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 410180d764d0ed96d1cb13fe3c2a39604604778a
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68633138"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Compatibilidad para la validación de mensajes firmados con DKIM

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) y Exchange Online admiten la validación entrante de mensajes de correo identificado de claves de dominio ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)).

DKIM valida que un mensaje de correo electrónico no fue *suplantado* por otra persona y que se envió desde el dominio del que *dice* que procede. Vincula un mensaje de correo electrónico a la organización que lo envió. La verificación DKIM se usa automáticamente para todos los mensajes enviados con IPv6. Microsoft 365 también admite DKIM cuando se envía correo a través de IPv4. (Para obtener más información acerca de la compatibilidad con IPv6, consulte [Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)).

DKIM valida un mensaje firmado digitalmente que aparece en el encabezado DKIM-Signature de los encabezados del mensaje. Los resultados de una validación de DKIM-Signature se marcan en el encabezado Authentication-Results. El texto del encabezado del mensaje tiene un aspecto similar al siguiente (donde contoso.com es el remitente):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Para obtener más información sobre el encabezado Authentication-Results, vea RFC 7001 ([Campo de encabezado de mensaje para indicar el estado de autenticación de mensajes](https://www.rfc-editor.org/rfc/rfc7001.txt)). La implementación DKIM de Microsoft se ajusta a esta RFC.

Los administradores pueden crear [reglas de flujo de correo](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) de Exchange (también conocidas como reglas de transporte) en los resultados de la validación DKIM. Estas reglas de flujo de correo permitirán a los administradores filtrar o enrutar mensajes según sea necesario.
