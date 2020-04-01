---
title: Agregar compatibilidad para el correo electrónico entrante anónimo a través de IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: El administrador puede aprender a configurar la compatibilidad con el correo electrónico entrante anónimo desde orígenes IPv6 en Exchange Online y Exchange Online Protection.
ms.openlocfilehash: 67e839249d41381be22bbccf6b09d1616c387c66
ms.sourcegitcommit: 748bc3484b7ccbd65b558f495b6fa42196c3c571
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "43083646"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a>Agregar compatibilidad para el correo electrónico entrante anónimo sobre IPv6 en Office 365

Office 365 organizaciones con buzones de Exchange Online y organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online admiten el correo electrónico entrante anónimo a través de IPv6. El servidor de correo electrónico IPv6 de origen debe cumplir con los siguientes requisitos:

- La dirección IPv6 de origen debe tener un registro de búsqueda DNS inversa (PTR) válido que permita al destino buscar el nombre de dominio de la dirección IPv6.

- El remitente debe pasar la verificación SPF (definida en la norma [RFC 7208](https://tools.ietf.org/html/rfc7208)) o la [verificación de DKIM](https://dkim.org/) (definida en la norma [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).

Para que su organización pueda recibir correo electrónico entrante anónimo a través de IPv6, un administrador debe ponerse en contacto con el soporte técnico de Microsoft y solicitarlo:

1. Abra el centro de administración de 365 <https://admin.microsoft.com/adminportal/home> de Microsoft en y haga clic en **ayuda** (?).

2. En el control flotante **¿necesita ayuda?** , escriba algo descriptivo en el cuadro de búsqueda (por ejemplo, "solicitar correo IPv6 de entrada anónimo") y, a continuación, presione Entrar.

3. En la parte inferior de la página, haga clic en **soporte técnico**.

4. En la página **contacto de soporte técnico** que aparece, rellene y Compruebe la información (Desplácese hacia abajo si es necesario) y, a continuación, haga clic en **ponerse en contacto conmigo**.

Una vez habilitada la compatibilidad de mensajes IPv6 entrantes anónimos en la organización, el mensaje pasará por el filtrado de mensajes normal proporcionado por el servicio.

## <a name="troubleshooting"></a>Solución de problemas

- Si el servidor de correo electrónico de origen no tiene un registro de búsqueda DNS inversa IPv6, los mensajes se rechazarán con el siguiente error:

  > 450 4.7.25 servicio no disponible, enviar dirección IPv6 [2a01:111: F200:2004:: 240] debe tener el registro DNS inverso.

- Si el remitente no pasa la validación de SPF o DKIM, los mensajes se rechazarán con el siguiente error:

  > 450 4.7.26 servicio no disponible, mensaje enviado a través de IPv6 [2a01:111: F200:2004:: 240] debe pasar la validación SPF o DKIM.

- Si intenta recibir mensajes IPv6 anónimos antes de participar en el, el mensaje se rechazará con el siguiente error:

  > 550 5.2.1 servicio no disponible, [contoso.com] no acepta correo electrónico a través de IPv6.

## <a name="for-more-information"></a>Más información

[Compatibilidad para la validación de mensajes firmados con DKIM](support-for-validation-of-dkim-signed-messages.md)
