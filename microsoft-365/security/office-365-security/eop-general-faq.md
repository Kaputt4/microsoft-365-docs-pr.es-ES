---
title: Preguntas más frecuentes sobre EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Obtenga respuestas a las preguntas generales más comunes sobre el servicio de filtrado de correo electrónico hospedado en la nube de Exchange Online Protection (EOP).
ms.openlocfilehash: aa0b881250466c71cb05123216fcf9eccc64018d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202920"
---
# <a name="eop-general-faq"></a>Preguntas más frecuentes sobre EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Aquí se responde a las preguntas generales más comunes sobre el servicio de filtrado de correo electrónico hospedado en la nube de Exchange Online Protection (EOP). Para ver otros temas sobre preguntas frecuentes (P+F), visite los siguientes enlaces:

- [Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP](eop-queued-deferred-and-bounced-messages-faq.md)

- [Preguntas más frecuentes sobre administración delegada](delegated-administration-faq.md)

- [Preguntas más frecuentes sobre la protección contra correo electrónico no deseado](anti-spam-protection-faq.md)

- [Preguntas más frecuentes sobre la cuarentena](quarantine-faq.md)

- [Preguntas más frecuentes sobre la protección antimalware](anti-malware-protection-faq-eop.md)

- [Preguntas frecuentes sobre el seguimiento de mensajes](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>¿Qué es EOP?

EOP es un servicio de filtrado de correo electrónico hospedado en la nube diseñado para proteger a los clientes contra correo no deseado y malware, así como para implementar reglas de directiva personalizadas. EOP se incluye en cualquier suscripción de Microsoft 365 que contenga buzones de correo de Exchange Online. EOP también está disponible como una oferta independiente para ayudar a proteger los entornos de correo electrónico locales.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>¿Cómo puedo registrarme para obtener una prueba de EOP o adquirir EOP?

A través de Internet, en la página principal de [Protección en línea de Exchange](https://products.office.com/exchange/exchange-email-security-spam-protection). Tenga en cuenta que la funcionalidad para una versión de prueba es la misma que para una suscripción de pago, pero también incluye las características adicionales suministradas con el plan de suscripción de [ Exchange Enterprise CAL con servicios ](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview).

## <a name="how-is-eop-priced"></a>¿Qué precio tiene EOP?

Las licencias de EOP se conceden por usuario. Para obtener la información de precios más reciente, consulte la página principal de [Protección en línea de Exchange](https://products.office.com/exchange/exchange-email-security-spam-protection).

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>¿Cuánto tiempo se tarda en poner EOP operativo?

El filtrado comienza de manera inmediata después de cambiar el registro MX, según los pasos detallados en [Configurar un servicio de EOP](set-up-your-eop-service.md) y de que el correo pase por EOP. El registro MX puede tardar entre 24 y 48 horas en propagarse a través de DNS. Puede ajustar la configuración de protección en cualquier momento durante este proceso.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>¿Es necesario usar todas las características de Microsoft 365 para usar EOP? ¿Qué sucede si solo quiero protección de EOP y esto es todo?

Puede usar EOP para proteger los buzones locales sin usar otras características de Microsoft 365. Esto se conoce como una suscripción independiente. Puede encontrar una lista de características EOP en la [Descripción de servicio Protección en línea de Exchange](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>¿Por qué necesito un inquilino de Microsoft 365 al registrarse para el filtrado de correo electrónico a través de EOP?

Microsoft 365 es el nombre asignado a una colección de productos y servicios a los que se puede tener acceso a través de un inquilino de Microsoft 365. Piense en el inquilino de Microsoft 365 como el punto de partida al que puede agregar licencias para el filtrado de correo electrónico.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>¿Dispone EOP de un portal de comunicación donde pueda obtener información sobre problemas conocidos y soluciones previstas? ¿Qué pasa con las nuevas características?

El centro de administración de Microsoft 365 tendrá parte de esta información. Si se ve afectado por un evento de nivel de servicio, debería ver una alerta de comunicación (que suele ir acompañada de un icono de campana) tras iniciar sesión en el centro de administración de Microsoft 365. Le recomendamos que la lea y tome las medidas necesarias en los elementos que procedan.

Con respecto a las nuevas características de EOP, el [plan de desarrollo de Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) es un buen recurso para buscar información sobre las nuevas características nuevas. También publicaremos artículos de blog sobre nuevas características en el sitio web de [blogs de Microsoft 365](https://www.microsoft.com/microsoft-365/blog/) .

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>¿El servicio funciona con versiones anteriores de Exchange (como Exchange Server 2010) y entornos que no son Exchange?

Sí, el servidor es válido y se puede usar con cualquier agente de transferencia de correo SMTP.

## <a name="what-size-organization-can-use-the-service"></a>¿Qué tamaño debe tener la organización que use el servicio?

Cualquier tamaño. La red de EOP tiene la capacidad suficiente para gestionar el crecimiento, independientemente de lo rápido que crezca su organización.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>¿Qué permisos necesito para configurar EOP?

Para configurar EOP, debe ser un administrador global o un administrador de la compañía de Exchange (el grupo de roles de administración de la organización).

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>¿Cómo sé que mis datos e información privada están seguros?

Para obtener más información acerca de los pasos que se han realizado para garantizar la seguridad de sus datos y la información privada, incluida la información sobre los acuerdos de nivel de servicio (SLA), vaya al [Centro de confianza de Office 365](https://www.microsoft.com/trust-center).

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>¿Hay algún límite que deba conocer, como por ejemplo limitaciones del tamaño de los mensajes?

Sí. Para más información sobre los límites de EOP, vea [Límites de Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="does-eop-support-powershell"></a>¿Es compatible con EOP a PowerShell?

Sí, la funcionalidad completa de EOP está disponible a través de PowerShell: Exchange Online PowerShell para organizaciones con buzones de correo de Exchange Online; PowerShell independiente de EOP para organizaciones de EOP independientes. Para obtener más información, consulte [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) y [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell).
