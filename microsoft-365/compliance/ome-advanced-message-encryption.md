---
title: Cifrado de mensajes avanzado
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
description: El cifrado de mensajes avanzado ayuda a las organizaciones a cumplir sus obligaciones de cumplimiento, ya que permite a los administradores hacer aún más con mensajes protegidos.
ms.openlocfilehash: 8c650c47c1853102e4e2d142040e49724ef707e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923960"
---
# <a name="advanced-message-encryption"></a>Cifrado de mensajes avanzado

El cifrado avanzado de mensajes de Office 365 se incluye en [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (precios de personal sin ánimo de lucro), Office 365 Enterprise E5 (precios de personal sin ánimo de lucro) y Office 365 Education A5. Si su organización tiene una suscripción que no incluye cifrado de mensajes avanzado de Office 365, puede adquirirla con el complemento SKU de cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precios de personal sin ánimo de lucro), o el complemento SKU de cumplimiento avanzado de Office 365 para Microsoft 365 E3, Microsoft 365 E3 (precios de personal sin ánimo de lucro), SKU de Office 365 o el complemento sku de protección de información y gobierno de Microsoft 365 E5/A5 para Microsoft 365 A3/E3.

El cifrado de mensajes avanzado ayuda a los clientes a cumplir las obligaciones de cumplimiento que requieren controles más flexibles sobre los destinatarios externos y su acceso a correos electrónicos cifrados. Con el cifrado de mensajes avanzado en Office 365, puede controlar los correos electrónicos confidenciales compartidos fuera de la organización con directivas automáticas. Estas directivas se configuran para identificar tipos de información confidencial como PII, Financial o Health ID, o puede usar palabras clave para mejorar la protección. Una vez configuradas las directivas, se emparejan las directivas con plantillas de correo electrónico personalizadas de marca y, a continuación, se agrega una fecha de expiración para un control adicional de los correos electrónicos que se ajustan a la directiva. Además, los administradores pueden controlar aún más los correos electrónicos cifrados a los que se accede externamente a través de un portal web seguro revocando el acceso al correo en cualquier momento.

Solo puede revocar y establecer una fecha de expiración para los correos electrónicos enviados a destinatarios externos.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Introducción al cifrado de mensajes avanzado de Office 365

En los siguientes artículos se describe cómo configurar y usar el cifrado de mensajes avanzado.

Su organización debe tener una suscripción que incluya cifrado de mensajes avanzado de Office 365. Para obtener información detallada acerca de las suscripciones admitidas, vea la descripción del servicio de cumplimiento y [directiva de mensajes.](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

Si aún no tiene office 365 Message Encryption configurado, vea [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).

Con cifrado de mensajes avanzado no se limita a una sola plantilla de personal de marca. En su lugar, puede crear y usar varias plantillas de personal de marca. Para obtener información, vea Agregar la marca de la organización [a los mensajes cifrados.](add-your-organization-brand-to-encrypted-messages.md)

Establecer una fecha de expiración para el correo electrónico cifrado por cifrado de mensajes avanzado [de Office 365](ome-advanced-expiration.md). Controle los correos electrónicos confidenciales compartidos fuera de la organización con directivas automáticas que mejoren la protección al expirar el acceso a través de un portal web seguro a los correos electrónicos cifrados.

Revocar el correo electrónico cifrado por cifrado de mensajes avanzado [de Office 365](revoke-ome-encrypted-mail.md). Controle los correos electrónicos confidenciales compartidos fuera de la organización y mejore la protección al revocar el acceso a través de un portal web seguro a los correos electrónicos cifrados.  

Con el cifrado de mensajes avanzado de Office 365, cada vez que aplica una plantilla de personalización de marca personalizada, Microsoft aplica un contenedor al correo electrónico que se ajusta a la regla de flujo de correo a la que aplica la plantilla. Solo puede revocar mensajes y aplicar fechas de expiración a los mensajes que los usuarios reciben a través del portal. En otras palabras, el correo electrónico que tiene una plantilla de personalización de marca personalizada aplicada. Para obtener más información y un ejemplo, vea las instrucciones de [Ensure all external recipients use the OME Portal to read encrypted mail](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail).