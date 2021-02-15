---
title: Establecer una fecha de expiración para el correo electrónico cifrado con el Cifrado de mensajes avanzado de Office 365
f1.keywords:
- NOCSH
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
description: Use el Cifrado de mensajes avanzado de Office 365 para ampliar la seguridad del correo electrónico estableciendo una fecha de expiración en los correos electrónicos a través de una plantilla personalizada con personalización de marca.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bbd018e55592e5b17149edf1a4dc0907c0184417
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769170"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Establecer una fecha de expiración para el correo electrónico cifrado con el Cifrado de mensajes avanzado de Office 365

El cifrado avanzado de mensajes de Office 365 se incluye en [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (precios para ong), Office 365 Enterprise E5 (precios para ong) y Office 365 Educación A5. Si su organización tiene una suscripción que no incluye el cifrado avanzado de mensajes de Office 365, puede comprarla con el complemento SKU de cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precios para el personal sin ánimo de lucro) o el complemento SKU de cumplimiento avanzado de Office 365 para Microsoft 365 E3, Microsoft 365 E3 (precios de personal para ong) u SKU de Office 365.

Puede usar la expiración de mensajes en los correos electrónicos que los usuarios envían a destinatarios externos que usan el Portal de OME para obtener acceso a los correos electrónicos cifrados. Obliga a los destinatarios a usar el portal de OME para ver y responder mensajes de correo electrónico cifrados enviados por su organización mediante una plantilla personalizada con personalización de marca que especifica una fecha de expiración en Windows PowerShell.

Como administrador global de Office 365, al aplicar la marca de su empresa para personalizar el aspecto de los mensajes de correo electrónico de su organización, también puede especificar una expiración para estos mensajes de correo electrónico. Con el cifrado avanzado de mensajes de Office 365, puede crear varias plantillas para los correos electrónicos cifrados que se originan en su organización. Con una plantilla, puede controlar durante cuánto tiempo los destinatarios tienen acceso al correo enviado por los usuarios.

Cuando un usuario final recibe un correo que tiene una fecha de expiración establecida, el usuario ve la fecha de expiración en el correo electrónico contenedor. Si un usuario intenta abrir un correo expirado, aparece un error en el portal de OME.

Solo puede establecer fechas de expiración para los mensajes de correo electrónico a destinatarios externos.

Con el cifrado avanzado de mensajes de Office 365, cada vez que aplica la personalización de marca, Office 365 aplica el contenedor al correo electrónico que se ajusta a la regla de flujo de correo a la que aplica la plantilla. Además, solo puede usar la expiración si usa la personalización de marca.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Crear una plantilla de personalización de marca personalizada para forzar la expiración del correo mediante PowerShell

1. [Conéctese a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) con una cuenta que tenga permisos de administrador global en su organización.

2. Ejecute el cmdlet New-OMEConfiguration.

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

Donde:

- `Identity` es el nombre de la plantilla personalizada.

- `ExternalMailExpiryInDays` identifica el número de días que los destinatarios pueden conservar el correo antes de que expire. Puede usar cualquier valor entre 1 y 730 días.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Más información sobre el cifrado avanzado de mensajes de Office 365

- [Cifrado avanzado de mensajes de Office 365](ome-advanced-message-encryption.md)

- [Revocar el correo electrónico cifrado por el cifrado avanzado de mensajes de Office 365](revoke-ome-encrypted-mail.md)

- [Descripción del servicio de cumplimiento y directiva de mensajes](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
