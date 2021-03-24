---
title: Compatibilidad con la validación de mensajes firmados de claves de dominio (DKIM)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Obtenga información sobre la validación de mensajes firmados dkim en Exchange Online Protection y Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8695e25000390cf6c5d58adf63db1984c873d75b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072483"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Compatibilidad para la validación de mensajes firmados con DKIM

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) y Exchange Online admiten la validación entrante de los mensajes de correo identificado de claves de dominio[(DKIM).](https://www.rfc-editor.org/rfc/rfc6376.txt)

DKIM valida que un mensaje de correo electrónico no fue *suplantado* por otra persona y se envió desde el dominio del que *dice* que provenía. Vincula un mensaje de correo electrónico a la organización que lo envió. La verificación DKIM se usa automáticamente para todos los mensajes enviados con IPv6. Microsoft 365 también admite DKIM cuando se envía correo a través de IPv4. (Para obtener más información acerca de la compatibilidad con IPv6, consulte [Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)).

DKIM valida un mensaje firmado digitalmente que aparece en el DKIM-Signature encabezado de los encabezados de mensaje. Los resultados de una DKIM-Signature validación se marcan en el Authentication-Results encabezado. El texto del encabezado del mensaje tiene un aspecto similar al siguiente (donde contoso.com es el remitente):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Para obtener más información acerca del Authentication-Results, vea RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt). La implementación dkim de Microsoft se ajusta a esta RFC.

Los administradores pueden crear reglas [de flujo](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) de correo de Exchange (también conocidas como reglas de transporte) en los resultados de la validación DKIM. Estas reglas de flujo de correo permitirán a los administradores filtrar o enrutar mensajes según sea necesario.