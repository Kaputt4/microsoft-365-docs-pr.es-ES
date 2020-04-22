---
title: Preguntas más frecuentes sobre EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
description: 'En este tema se responden las preguntas generales más comunes acerca del servicio de filtrado de correo electrónico hospedado en la nube de Microsoft Exchange Online Protection (EOP). Para ver otros temas sobre preguntas frecuentes (P+F), visite los siguientes enlaces:'
ms.openlocfilehash: 899109a768399f53674b97fc8df2f71aa822316d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636257"
---
# <a name="eop-general-faq"></a>Preguntas más frecuentes sobre EOP

En este tema se responden las preguntas generales más comunes acerca del servicio de filtrado de correo electrónico hospedado en la nube de Microsoft Exchange Online Protection (EOP). Para ver otros temas sobre preguntas frecuentes (P+F), visite los siguientes enlaces:

- [Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP](eop-queued-deferred-and-bounced-messages-faq.md)

- [Preguntas más frecuentes sobre administración delegada](delegated-administration-faq.md)

- [Preguntas más frecuentes sobre la protección contra correo electrónico no deseado](anti-spam-protection-faq.md)

- [Preguntas más frecuentes sobre la cuarentena](quarantine-faq.md)

- [Preguntas más frecuentes sobre la protección antimalware](anti-malware-protection-faq-eop.md)

- [Preguntas frecuentes sobre el seguimiento de mensajes](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

**P. ¿Qué es EOP?**

R. EOP es un servicio de filtrado de correo electrónico hospedado en la nube diseñado para proteger a los clientes contra correo no deseado y malware, así como para implementar reglas de directiva personalizadas.

**P. ¿Cómo puedo registrarme para obtener una prueba de EOP o adquirir EOP?**

R. A través de Internet, en la página principal de [Protección en línea de Exchange](https://products.office.com/exchange/exchange-email-security-spam-protection). Tenga en cuenta que la funcionalidad para una versión de prueba es la misma que para una suscripción de pago, pero también incluye las características adicionales suministradas con el plan de suscripción de [ Exchange Enterprise CAL con servicios ](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview).

**P. ¿Qué precio tiene EOP?**

R. Las licencias de EOP se conceden por usuario. Para obtener la información de precios más reciente, consulte la página principal de [Protección en línea de Exchange](https://products.office.com/exchange/exchange-email-security-spam-protection).

**P. ¿Cuánto tiempo se tarda en poner EOP operativo?**

R. El filtrado comienza de manera inmediata después de cambiar el registro MX, según los pasos detallados en [Configurar un servicio de EOP](set-up-your-eop-service.md) y de que el correo pase por EOP. El registro MX puede tardar entre 24 y 48 horas en propagarse a través de DNS. Puede ajustar la configuración de protección del Centro de administración de Exchange (EAC) en cualquier momento durante este proceso.

**P. ¿tengo que usar todas las características de Microsoft 365 para usar EOP? ¿Qué sucede si solo quiero protección de EOP y esto es todo?**

A. Puede usar EOP para proteger los buzones locales sin usar otras características de Microsoft 365. Esto se conoce como una suscripción independiente. Puede encontrar una lista de características EOP en la [Descripción de servicio Protección en línea de Exchange](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

**P. ¿por qué necesito un inquilino de Microsoft 365 al registrarse para el filtrado de correo electrónico a través de EOP?**

A. Microsoft 365 es el nombre asignado a una colección de productos y servicios a los que se puede tener acceso a través de un inquilino de Microsoft 365. Piense en el inquilino de Microsoft 365 como el punto de partida al que puede agregar licencias para el filtrado de correo electrónico.

**P. ¿Dispone EOP de un portal de comunicación donde pueda obtener información sobre problemas conocidos y soluciones previstas? ¿Qué pasa con las nuevas características?**

R. El centro de administración de Microsoft 365 tendrá parte de esta información. Si se ve afectado por un evento de nivel de servicio, debería ver una alerta de comunicación (que suele ir acompañada de un icono de campana) tras iniciar sesión en el centro de administración de Microsoft 365. Le recomendamos que la lea y tome las medidas necesarias en los elementos que procedan.

Con respecto a las nuevas características de EOP, el [plan de desarrollo de Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) es un buen recurso para buscar información sobre las nuevas características nuevas. También publicaremos artículos de blog sobre nuevas características en el sitio web de [blogs de Microsoft 365](https://www.microsoft.com/microsoft-365/blog/) .

**P. ¿El servicio funciona con versiones anteriores de Exchange (como Exchange Server 2010) y entornos que no son Exchange?**

R. Sí, el servidor es válido y se puede usar con cualquier agente de transferencia de correo SMTP.

**P. ¿Qué tamaño debe tener la organización que use el servicio?**

R. Cualquier tamaño. La red de EOP tiene la capacidad suficiente para gestionar el crecimiento, independientemente de lo rápido que crezca su organización.

**¿Qué permisos necesito para configurar EOP?**

Para configurar EOP, debe ser un administrador global o un administrador de la compañía de Exchange (el grupo de roles de administración de la organización).

**P. ¿Cómo sé que mis datos e información privada están seguros?**

R. Para obtener más información acerca de los pasos que se han realizado para garantizar la seguridad de sus datos y la información privada, incluida la información sobre los acuerdos de nivel de servicio (SLA), vaya al [Centro de confianza de Office 365](https://www.microsoft.com/trust-center).

**P. ¿Hay algún límite que deba conocer, como por ejemplo limitaciones del tamaño de los mensajes?**

R. Sí. Para más información sobre los límites de EOP, vea [Límites de Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

**P. ¿es compatible EOP con Windows PowerShell?**

A. Sí, la funcionalidad completa de EOP está disponible a través de PowerShell. Para obtener más información, vea [PowerShell de Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).
