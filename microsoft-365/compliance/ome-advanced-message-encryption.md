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
ms.localizationpriority: medium
ms.date: 04/01/2022
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: El cifrado de mensajes avanzado ayuda a las organizaciones a cumplir sus obligaciones de cumplimiento, ya que permite a los administradores hacer aún más con mensajes protegidos.
ms.openlocfilehash: 74d94bdb837531fdbbb819c86f9dbb7dd80272e8
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634347"
---
# <a name="advanced-message-encryption"></a>Cifrado de mensajes avanzado

Cifrado de mensajes avanzado de Office 365 se incluye en [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (precios de personal sin ánimo de lucro), Office 365 Enterprise  E5 (precios de personal sin ánimo de lucro) y Office 365 Education A5. Para usar las funciones de revocación y expiración de cifrado de mensajes avanzados, habilite la Premium **cifrado** en Office 365 en la licencia de E5.

Si su organización tiene una suscripción que no incluye Cifrado de mensajes avanzado de Office 365, puede comprarla con el complemento SKU de Cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3  (Precios del personal sin ánimo de lucro), o el complemento sku de Cumplimiento avanzado de Office 365 para Microsoft 365 E3, Microsoft 365 E3 (precios de personal sin ánimo de lucro), Office 365 SKU o el Microsoft 365 E5/A5 Information Protection y complemento SKU de gobierno para Microsoft 365 A3/E3.

El cifrado de mensajes avanzado ayuda a los clientes a cumplir las obligaciones de cumplimiento que requieren controles más flexibles sobre los destinatarios externos y su acceso a correos electrónicos cifrados. Con el cifrado de mensajes avanzado en Office 365, puede controlar correos electrónicos confidenciales compartidos fuera de la organización con directivas automáticas. Estas directivas se configuran para identificar tipos de información confidencial como PII, Financial o Health ID, o puede usar palabras clave para mejorar la protección. Una vez configuradas las directivas, se emparejan las directivas con plantillas de correo electrónico personalizadas de marca y, a continuación, se agrega una fecha de expiración para un control adicional de los correos electrónicos que se ajustan a la directiva. Además, los administradores pueden controlar aún más los correos electrónicos cifrados a los que se accede externamente a través de un portal web seguro revocando el acceso al correo en cualquier momento.

Solo puede revocar y establecer una fecha de expiración para los correos electrónicos enviados a destinatarios externos.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Comenzar con Cifrado de mensajes avanzado de Office 365

En los siguientes artículos se describe cómo configurar y usar el cifrado de mensajes avanzado.

La organización debe tener una suscripción que incluya Cifrado de mensajes avanzado de Office 365. Para obtener información detallada acerca de las suscripciones admitidas, consulte [la descripción del servicio de cumplimiento y directiva de mensajes](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).

Si aún no ha configurado Office 365 cifrado de mensajes, consulte [Configurar nuevas funcionalidades Office 365 cifrado de mensajes](set-up-new-message-encryption-capabilities.md).

Con cifrado de mensajes avanzado, no se limita a una sola plantilla de personal de marca. En su lugar, puede crear y usar varias plantillas de personal de marca. Agregar personalización de marca personalizada también permite realizar un seguimiento de una revocación de mensajes cifrados. Para obtener información, consulta [Agregar la marca de la organización a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md). Al usar la personalización de marca personalizada, los destinatarios externos reciben un correo electrónico de notificación que contiene un vínculo al portal de OME. La regla de flujo de correo determina qué plantilla de personal de marca usan el correo electrónico de notificación y el Portal de OME. De esta forma, el contenido seguro no se envía fuera de la organización.

Solo puede revocar mensajes y aplicar fechas de expiración a los mensajes que los usuarios reciben a través del portal. En otras palabras, el correo electrónico que tiene una plantilla de personalización de marca personalizada aplicada. Para obtener más información y un ejemplo, vea las instrucciones de [Ensure all external recipients use the OME Portal to read encrypted mail](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail).

[Establezca una fecha de expiración para el correo electrónico cifrado por Cifrado de mensajes avanzado de Office 365](ome-advanced-expiration.md). Controle los correos electrónicos confidenciales compartidos fuera de la organización con directivas automáticas que mejoren la protección al expirar el acceso a través de un portal web seguro a los correos electrónicos cifrados.

[Revocar el correo electrónico cifrado por Cifrado de mensajes avanzado de Office 365](revoke-ome-encrypted-mail.md). Controle los correos electrónicos confidenciales compartidos fuera de la organización y mejore la protección al revocar el acceso a través de un portal web seguro a los correos electrónicos cifrados.  
