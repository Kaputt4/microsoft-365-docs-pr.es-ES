---
title: Establecer una fecha de expiración para el correo electrónico cifrado mediante cifrado de mensajes avanzado de Microsoft Purview
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- tier1
- purview-compliance
description: Use Cifrado avanzado de mensajes de Microsoft Purview para ampliar la seguridad del correo electrónico estableciendo una fecha de expiración en los correos electrónicos a través de una plantilla personalizada de marca.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 96d9acafd7c192e24768bcc9cf3e015fffb4db4c
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68634594"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-microsoft-purview-advanced-message-encryption"></a>Establecer una fecha de expiración para el correo electrónico cifrado mediante cifrado de mensajes avanzado de Microsoft Purview

El cifrado avanzado de mensajes de Microsoft Purview se incluye en [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (precios del personal sin ánimo de lucro), Office 365 Enterprise E5 (precios del personal sin ánimo de lucro) y Office 365 Educación A5. Cumplimiento de Microsoft 365 E5 complemento de SKU para Microsoft 365 E3, Microsoft 365 E3 (precios del personal sin ánimo de lucro) o el complemento de SKU de Cumplimiento avanzado de Office 365 para Microsoft 365 E3, Microsoft 365 E3 (precios del personal sin ánimo de lucro) o SKU de Office 365.

Si su organización tiene una suscripción que no incluye el cifrado avanzado de mensajes de Microsoft Purview, puede comprarlo con el complemento de SKU de Cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precios del personal sin ánimo de lucro) o el Cumplimiento avanzado de Office 365 complemento de SKU para Microsoft 365 E3, Microsoft 365 E3 (precios del personal sin ánimo de lucro) o SKU de Office 365.

Puede usar la expiración de mensajes en los correos electrónicos que los usuarios envían a destinatarios externos que usan el Portal de OME para acceder a correos electrónicos cifrados. Obliga a los destinatarios a usar el portal de OME para ver y responder a los correos electrónicos cifrados enviados por su organización mediante una plantilla de marca personalizada que especifica una fecha de expiración en PowerShell.

Como administrador global Office 365, al aplicar la marca de la empresa para personalizar el aspecto de los mensajes de correo electrónico de la organización, también puede especificar una expiración para estos mensajes de correo electrónico. Con el cifrado avanzado de mensajes de Microsoft Purview, puede crear varias plantillas para correos electrónicos cifrados que se originan en su organización. Con una plantilla, puede controlar cuánto tiempo los destinatarios tienen acceso al correo enviado por los usuarios.

Cuando un usuario final recibe correo que tiene establecida una fecha de expiración, el usuario ve la fecha de expiración en el correo electrónico contenedor. Si un usuario intenta abrir un correo expirado, aparece un error en el portal de OME.

Solo puede establecer fechas de expiración de los correos electrónicos a destinatarios externos.

Con el cifrado avanzado de mensajes de Microsoft Purview, cada vez que aplique personalización de marca, el Office 365 aplica el contenedor al correo electrónico que se ajusta a la regla de flujo de correo a la que se aplica la plantilla. Además, solo puede usar la expiración si usa personalización de marca.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Creación de una plantilla de personalización de marca personalizada para forzar la expiración del correo mediante PowerShell

1. [Conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) con una cuenta que tenga permisos de administrador global en su organización.

2. Ejecute el cmdlet New-OMEConfiguration.

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

Donde:

- `Identity` es el nombre de la plantilla personalizada.

- `ExternalMailExpiryInDays` identifica el número de días que los destinatarios pueden conservar el correo antes de que expire. Puede usar cualquier valor entre 1 y 730 días.

## <a name="more-information-about-microsoft-purview-advanced-message-encryption"></a>Más información sobre el cifrado avanzado de mensajes de Microsoft Purview

- [Cifrado avanzado de mensajes](ome-advanced-message-encryption.md)

- [Revocar el correo electrónico cifrado mediante el cifrado de mensajes avanzado de Microsoft Purview](revoke-ome-encrypted-mail.md)

- [Descripción de la directiva de mensaje y del servicio de cumplimiento](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
