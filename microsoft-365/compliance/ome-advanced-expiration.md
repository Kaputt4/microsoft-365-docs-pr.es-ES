---
title: Establecer una fecha de expiración para el correo electrónico cifrado por el cifrado avanzado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Con Office 365 avanzadas capacidades de cifrado de mensajes sobre el cifrado de mensajes de Office 365 (OME), puede ampliar su seguridad de correo electrónico estableciendo una fecha de expiración en los correos electrónicos a través de una plantilla personalizada de personalización de marca.
ms.openlocfilehash: 6790cc7103ad098419bde96b93738424626cd0cc
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "38687714"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Establecer una fecha de expiración para el correo electrónico cifrado por el cifrado avanzado de mensajes de Office 365

Office 365 Advanced Message Encryption se incluye en [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (precio de personal sin ánimo de lucro), Office 365 Enterprise E5 (precio de personal sin ánimo de lucro) y Office 365 Education A5. Si su organización tiene una suscripción que no incluye el cifrado avanzado de mensajes de Office 365, puede adquirirlo con el complemento de SKU de cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precio del personal sin ánimo de lucro) o el Office 365 Advanced Complemento de SKU de cumplimiento para Microsoft 365 E3, Microsoft 365 E3 (precio del personal sin ánimo de lucro) o SKU de Office 365.

Puede usar la expiración de mensajes en los correos electrónicos que los usuarios envían a los destinatarios externos que usan el portal OME para acceder a los correos electrónicos cifrados. Obliga a los destinatarios a usar el portal OME para ver y responder a los correos electrónicos cifrados enviados por la organización mediante una plantilla personalizada que especifica una fecha de expiración en Windows PowerShell.

Como administrador global de O365, cuando aplique la marca de su compañía para personalizar la apariencia de los mensajes de correo electrónico de su organización de Office 365, también puede especificar una expiración para estos mensajes de correo electrónico. Con Office 365 Advanced Message Encryption, puede crear varias plantillas para mensajes de correo electrónico cifrados que se originan en su organización. Mediante el uso de una plantilla, puede controlar durante cuánto tiempo los destinatarios tienen acceso al correo enviado por los usuarios.

Cuando un usuario final recibe un correo con una fecha de expiración establecida, el usuario ve la fecha de expiración en el correo electrónico del contenedor. Si un usuario intenta abrir un correo expirado, aparece un error en el portal OME.

Solo se pueden establecer fechas de caducidad para los correos electrónicos a los destinatarios externos.

Con Office 365 Advanced Message Encryption, siempre que aplique la personalización de marca personalizada, la Office 365 aplica el contenedor a correo electrónico que se ajusta a la regla de flujo de correo a la que se aplica la plantilla. Además, solo puede usar la expiración si usa la personalización de marca personalizada.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Crear una plantilla de personalización de marca personalizada para forzar la expiración del correo mediante PowerShell

1. [Conéctese a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) con una cuenta que tenga permisos de administrador global en su organización de Office 365.

2. Ejecute el cmdlet New-OMEConfiguration.

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

Donde:

- `Identity`es el nombre de la plantilla personalizada.

- `ExternalMailExpiryInDays`identifica el número de días que los destinatarios pueden conservar el correo antes de que expire. Puede usar cualquier valor entre 1 y 730 días.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Más información sobre el cifrado de mensajes avanzado de Office 365

- [Cifrado avanzado de mensajes de Office 365](ome-advanced-message-encryption.md)

- [Revocar el correo electrónico cifrado por el cifrado avanzado de mensajes de Office 365](revoke-ome-encrypted-mail.md)

- [Descripción de la Directiva de mensajes y el servicio de cumplimiento](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
