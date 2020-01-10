---
title: Corregir problemas de entrega de correo electrónico para el código de error 5.7.7 XX en Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo solucionar problemas de correo electrónico para el código de error 5.7.7 XX en Exchange Online (inquilino bloqueado del envío de correo).
ms.openlocfilehash: 4e82df78cfb83865142defb14cec0841ab29ba95
ms.sourcegitcommit: 55cb11c2475f40d0f1c64cf45446bf383d7d5f86
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002980"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a>Corregir problemas de entrega de correo electrónico para el código de error 5.7.7 XX en Exchange Online

En este tema se describe lo que puede hacer si ve el código de estado 550 5.7.7 XX en un informe de no entrega (también conocido como NDR, mensaje de devolución, notificación de estado de entrega o DSN). Verá esta notificación automática cuando se restringe el envío de correo electrónico de su inquilino de una forma u otra. Estos códigos de error normalmente se incluyen como 705 o 750.

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a>5.7.705: el inquilino ha superado la restricción de umbral: lo que debe saber

Una vez que los usuarios (de forma colectiva, como organización) envían una determinada cantidad de correo electrónico sospechoso a través del servicio, se puede impedir que todos los usuarios envíen correo electrónico hasta que se solucione el problema. Suele ser el resultado de un riesgo (más común) o el envío de correo masivo. Los usuarios recibirán un NDR que indica lo siguiente:

`550 5.7.705 Access denied, tenant has exceeded threshold`

En raras ocasiones, esto también podría suceder si renueva la suscripción después de que ya ha expirado. El servicio tarda tiempo en sincronizar la nueva información de suscripción (normalmente, no más de un día), pero, mientras tanto, puede bloquear el envío de correo electrónico a su organización. La mejor forma de evitar esto es asegurarse de que la suscripción no expira.

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a>5.7.750: restricción de correo electrónico del dominio no registrado: lo que debe saber

Office 365 permite que los inquilinos retransmitan algunos mensajes a través de Exchange Online Protection (EOP). Por ejemplo:

- Un buzón de Office 365 recibe correo electrónico de un remitente externo. El reenvío de correo se configura en el buzón de Office 365, de modo que el mensaje vuelve a la dirección de correo electrónico externa del usuario. Este escenario es más habitual en los entornos educativos en los que los alumnos quieren usar sus cuentas de correo electrónico personales para ver los mensajes relacionados con la escuela.

- Entornos híbridos que tienen servidores de correo electrónico locales que envían correo saliente a través de EOP.

### <a name="problems-with-unregistered-domains"></a>Problemas con dominios no registrados

El problema es cuando los servidores de correo electrónico en peligro retransmiten un gran volumen de correo no deseado a través de EOP. En casi todos los casos, los conectores están configurados correctamente, pero el correo electrónico se envía desde dominios no registrados (también conocidos como no aprovisionados). Office 365 permite una cantidad razonable de correo electrónico de dominios no registrados, pero debe configurar todos los dominios que use para enviar correo electrónico como un dominio aceptado.

Una vez comprometida, se impedirá que los inquilinos envíen correo electrónico saliente para dominios no registrados. Los usuarios recibirán un NDR que indica lo siguiente:

`550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains`

## <a name="unblocking-tenant-in-order-to-send-again"></a>Desbloqueo de inquilino para enviar de nuevo

Hay varias cosas que debe hacer si el inquilino tiene bloqueado el envío de correo electrónico:

1. Cambie la contraseña de sus cuentas de administrador. Si se bloquea el envío de un inquilino, lo más probable es que se haya puesto en peligro una cuenta de administrador. Cambiar las contraseñas es el primer paso para evitar que el atacante haga más daño.

2. [Habilite MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) para todos los administradores de la organización de Office 365.

3. Compruebe que todos los dominios de correo electrónico están registrados. Para obtener más información, vea [Agregar un dominio a Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) y [administrar dominios aceptados en Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

4. Busque [conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)inusuales. A menudo, los actores malintencionados crean conectores entrantes nuevos en la organización de Office 365 para enviar correo no deseado. Para ver los conectores existentes, consulte [validar conectores en Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors).

5. Compruebe si los usuarios están comprometidos como se describe en [responder a una cuenta de correo electrónico en peligro en Office 365](responding-to-a-compromised-email-account.md).

6. Bloquee los servidores de correo electrónico locales y compruebe que no estén comprometidos.

   > [!TIP]
   > Hay muchos factores aquí, especialmente si está usando servidores de terceros. En cualquier caso, tendrá que comprobar que el correo saliente no incluye correo no deseado.

7. Llame al soporte técnico de Microsoft y pídale que se desbloquee el espacio empresarial para enviar el correo electrónico de nuevo. El código de error es útil, pero tendrá que probar que su entorno se ha asegurado y no puede enviar correo no deseado. Para abrir un caso de soporte técnico, consulte [Contact Support for Business Products: ayuda de administración](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

## <a name="for-more-information"></a>Más información

[Protección contra correo no deseado de Office 365](anti-spam-protection.md)

[Guía de correo masivo en la sección límites de envío de la descripción del servicio de Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

[Informes de no entrega de correo electrónico en Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

[Configurar el reenvío de correo electrónico para un buzón de correo](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Cómo configurar una aplicación o dispositivo multifunción para enviar correos electrónicos mediante Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-office-3)

[Administrar dominios aceptados en Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
