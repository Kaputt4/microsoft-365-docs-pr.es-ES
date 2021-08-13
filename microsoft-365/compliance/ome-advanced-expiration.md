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
description: Use Cifrado de mensajes avanzado de Office 365 para ampliar la seguridad del correo electrónico estableciendo una fecha de expiración en los correos electrónicos a través de una plantilla personalizada de marca.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5cc669a0aae02da413b0e288be9203743d29c20e0fcd870cb99b67154fdf66e
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53795847"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Establecer una fecha de expiración para el correo electrónico cifrado con el Cifrado de mensajes avanzado de Office 365

Cifrado de mensajes avanzado de Office 365 se incluye en [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (precios de personal sin ánimo de lucro), Office 365 Enterprise E5 (precios de personal sin ánimo de lucro) y Office 365 Educación A5. Si su organización tiene una suscripción que no incluye Cifrado de mensajes avanzado de Office 365, puede comprarla con el complemento SKU de Cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precios de personal sin ánimo de lucro) o el complemento sku de Cumplimiento avanzado de Office 365 para Microsoft 365 E3, Microsoft 365 E3 (precios de personal sin ánimo de lucro) o SKU de Office 365.

Puede usar la expiración de mensajes en los correos electrónicos que los usuarios envían a destinatarios externos que usan el Portal de OME para obtener acceso a correos electrónicos cifrados. Obliga a los destinatarios a usar el portal de OME para ver y responder a los correos electrónicos cifrados enviados por su organización mediante una plantilla personalizada de marca que especifica una fecha de expiración en Windows PowerShell.

Como administrador Office 365 global, al aplicar la marca de la empresa para personalizar la apariencia de los mensajes de correo electrónico de su organización, también puede especificar una expiración para estos mensajes de correo electrónico. Con Cifrado de mensajes avanzado de Office 365, puede crear varias plantillas para correos electrónicos cifrados que se originan en su organización. Con una plantilla, puede controlar cuánto tiempo los destinatarios tienen acceso al correo enviado por los usuarios.

Cuando un usuario final recibe correo que tiene una fecha de expiración establecida, el usuario ve la fecha de expiración en el correo electrónico contenedor. Si un usuario intenta abrir un correo expirado, aparecerá un error en el portal de OME.

Solo puede establecer las fechas de expiración de los mensajes de correo electrónico a destinatarios externos.

Con Cifrado de mensajes avanzado de Office 365, cada vez que aplique la personalización de marca personalizada, el Office 365 aplica el contenedor al correo electrónico que se ajusta a la regla de flujo de correo a la que aplica la plantilla. Además, solo puedes usar la expiración si usas personalización de marca personalizada.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Crear una plantilla de personalización de marca personalizada para forzar la expiración del correo mediante PowerShell

1. [Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) con una cuenta que tenga permisos de administrador global en su organización.

2. Ejecute el cmdlet New-OMEConfiguration.

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

Donde:

- `Identity` es el nombre de la plantilla personalizada.

- `ExternalMailExpiryInDays` identifica el número de días que los destinatarios pueden conservar el correo antes de que expire. Puede usar cualquier valor entre 1 y 730 días.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Más información sobre Cifrado de mensajes avanzado de Office 365

- [Cifrado avanzado de mensajes de Office 365](ome-advanced-message-encryption.md)

- [Revocar el correo electrónico cifrado por el cifrado avanzado de mensajes de Office 365](revoke-ome-encrypted-mail.md)

- [Descripción del servicio de cumplimiento y directiva de mensajes](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)