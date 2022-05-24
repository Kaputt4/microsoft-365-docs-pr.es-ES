---
title: Agregar la compatibilidad para el correo electrónico entrante anónimo a través de IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administración puede aprender a configurar la compatibilidad con el correo electrónico entrante anónimo desde orígenes IPv6 en Exchange Online y Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 093ab458e8894105536e1c3dd46d2c911de440fd
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "65649107"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Agregar compatibilidad con el correo electrónico de entrada anónimo a través de IPv6 en Microsoft 365

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 organizaciones con buzones de Exchange Online y organizaciones independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online admiten el correo electrónico entrante anónimo a través de IPv6. El servidor de correo electrónico IPv6 de origen debe cumplir los dos requisitos siguientes:

- La dirección IPv6 de origen debe tener un registro de búsqueda inversa (PTR) válido que permita al destino encontrar el nombre de dominio de la dirección IPv6.

- El remitente debe pasar la verificación SPF (definida en la norma [RFC 7208](https://tools.ietf.org/html/rfc7208)) o la [verificación de DKIM](http://dkim.org/) (definida en la norma [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).

Antes de que su organización pueda recibir correo electrónico entrante anónimo a través de IPv6, un administrador debe ponerse en contacto con el soporte técnico de Microsoft y solicitarlo. Para obtener instrucciones sobre cómo abrir una solicitud de soporte técnico, consulte [Póngase en contacto con soporte técnico para productos empresariales Administración Ayuda](../../admin/get-help-support.md).

Una vez habilitada la compatibilidad con mensajes IPv6 entrantes anónimos en su organización, el mensaje pasará por el filtrado de mensajes normal proporcionado por el servicio.

## <a name="troubleshooting"></a>Solución de problemas

- Si el servidor de correo electrónico de origen no tiene un registro de búsqueda de DNS inverso IPv6, los mensajes se rechazarán con el siguiente error:

  > 450 4.7.25 El servicio no disponible, el envío de la dirección IPv6 [2a01:111:f200:2004::240] debe tener un registro DNS inverso.

- Si el remitente no pasa la validación SPF o DKIM, los mensajes se rechazarán con el siguiente error:

  > 450 4.7.26 El servicio no disponible, el mensaje enviado a través de IPv6 [2a01:111:f200:2004::240] debe pasar la validación SPF o DKIM.

- Si intenta recibir mensajes IPv6 anónimos antes de participar, el mensaje se rechazará con el siguiente error:

  > 550 5.2.1 El servicio no está disponible; [contoso.com] no acepta correo electrónico a través de IPv6.

## <a name="related-topics"></a>Temas relacionados

[Compatibilidad para la validación de mensajes firmados con DKIM](support-for-validation-of-dkim-signed-messages.md)
