---
title: Cifrado avanzado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/16/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: El cifrado de mensajes avanzado ayuda a las organizaciones a cumplir sus obligaciones de cumplimiento, ya que permite a los administradores hacer aún más con los mensajes protegidos.
ms.openlocfilehash: 0e28bd283b6a7d1666d5db9b71040d2f377adffe
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626898"
---
# <a name="advanced-message-encryption"></a>Cifrado de mensajes avanzado

El cifrado avanzado de mensajes de Office 365 se incluye en [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (precios para el personal sin ánimo de lucro), Office 365 Enterprise E5 (precios de personal para ong) y Office 365 Educación A5. Si su organización tiene una suscripción que no incluye el cifrado avanzado de mensajes de Office 365, puede comprarla con el complemento SKU de cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precios para el personal sin ánimo de lucro), o el complemento SKU de cumplimiento avanzado de Office 365 para Microsoft 365 E3, Microsoft 365 E3 (precios de personal para ong), SKU de Office 365 o el complemento de SKU de protección de la información y gobierno de Microsoft 365 E5/A5 para Microsoft 365 A3/E3.

El cifrado de mensajes avanzado ayuda a los clientes a cumplir las obligaciones de cumplimiento que requieren controles más flexibles sobre los destinatarios externos y su acceso a los correos electrónicos cifrados. Con el cifrado avanzado de mensajes en Office 365, puede controlar los correos electrónicos confidenciales compartidos fuera de la organización con directivas automáticas. Estas directivas se configuran para identificar tipos de información confidencial, como id. de pii, financieros o de estado, o se pueden usar palabras clave para mejorar la protección. Una vez que haya configurado las directivas, debe emparejar las directivas con plantillas de correo electrónico personalizadas y, a continuación, agregar una fecha de expiración para un control adicional de los correos electrónicos que se ajustan a la directiva. Además, los administradores pueden controlar aún más los correos electrónicos cifrados a los que se accede externamente a través de un portal web seguro al revocar el acceso al correo en cualquier momento.

Solo puede revocar y establecer una fecha de expiración para los correos electrónicos enviados a destinatarios externos.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Introducción al cifrado avanzado de mensajes de Office 365

En los artículos siguientes se describe cómo configurar y usar el cifrado avanzado de mensajes.

Su organización debe tener una suscripción que incluya el cifrado avanzado de mensajes de Office 365. Para obtener información detallada sobre las suscripciones admitidas, vea la descripción del servicio de cumplimiento y la directiva [de mensajes.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

Si aún no tiene configurado el cifrado de mensajes de Office 365, consulte Configurar nuevas capacidades de cifrado de mensajes de [Office 365.](set-up-new-message-encryption-capabilities.md)

Con el cifrado de mensajes avanzado no se limita a una sola plantilla de personal de marca. En su lugar, puede crear y usar varias plantillas de personal de marca. Para obtener información, [consulte Agregar la marca de su organización a los mensajes cifrados.](add-your-organization-brand-to-encrypted-messages.md)

Establecer una fecha de expiración para el correo electrónico cifrado mediante el cifrado de mensajes avanzado [de Office 365](ome-advanced-expiration.md). Controle los correos electrónicos confidenciales compartidos fuera de la organización con directivas automáticas que mejoren la protección al expirar el acceso a través de un portal web seguro para los correos electrónicos cifrados.

Revocar el correo electrónico cifrado por el cifrado de mensajes avanzado de [Office 365.](revoke-ome-encrypted-mail.md) Controle los correos electrónicos confidenciales compartidos fuera de la organización y mejore la protección al revocar el acceso a través de un portal web seguro a los correos electrónicos cifrados.  

Con el cifrado avanzado de mensajes de Office 365, cada vez que aplica una plantilla de personalización de marca personalizada, Microsoft aplica un contenedor al correo electrónico que se ajusta a la regla de flujo de correo a la que se aplica la plantilla. Solo puede revocar mensajes y aplicar fechas de expiración a los mensajes que los usuarios reciben a través del portal. En otras palabras, el correo electrónico que tiene aplicada una plantilla de personalización de marca personalizada. Para obtener más información y un ejemplo, vea las instrucciones de Asegurarse de que todos los destinatarios externos usen el [Portal de OME para leer correo cifrado.](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)
