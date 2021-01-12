---
title: Preguntas más frecuentes sobre los mensajes en cuarentena
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
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden ver las preguntas más frecuentes y las respuestas sobre los mensajes en cuarentena en Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 58ddb5847706aef3d2c3b8ea8cd9a96fd65a9b3d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794417"
---
# <a name="quarantined-messages-faq"></a>Preguntas más frecuentes sobre los mensajes en cuarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En este tema se proporcionan preguntas y respuestas más frecuentes sobre los mensajes de correo electrónico en cuarentena para organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online.

Para obtener preguntas y respuestas acerca de la protección contra correo no deseado, consulte preguntas más frecuentes sobre protección contra [correo no deseado.](anti-spam-protection-faq.md)

Para obtener preguntas y respuestas acerca de la protección antimalware, consulte preguntas más frecuentes sobre protección [antimalware.](anti-malware-protection-faq-eop.md)

Para obtener preguntas y respuestas acerca de la protección contra la suplantación, consulte preguntas más frecuentes sobre la protección contra la [suplantación de seguridad.](anti-spoofing-protection-faq.md)

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>¿Cómo puedo administrar los mensajes que se han puesto en cuarentena en busca de malware?

Solo los administradores pueden administrar los mensajes que se han puesto en cuarentena en busca de malware. Para obtener más información, vea [Administrar mensajes y archivos en cuarentena como administrador.](manage-quarantined-messages-and-files.md)

## <a name="how-do-i-quarantine-spam"></a>¿Cómo poner en cuarentena el correo no deseado?

De forma predeterminada, los mensajes clasificados como correo no deseado o correo masivo mediante el filtrado de correo no deseado se entregan en el buzón del usuario y se mueven a la carpeta correo no deseado. Sin embargo, puede crear y configurar directivas contra correo no deseado para poner en cuarentena los mensajes de correo no deseado o de correo masivo en su lugar. Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>¿Cómo puedo dar acceso a los usuarios a la cuarentena?

Un usuario debe tener una cuenta válida para tener acceso a sus propios mensajes en cuarentena. EOP independiente requiere que los usuarios se represente como usuarios de correo en EOP (creados manualmente o creados mediante la sincronización de directorios). Para obtener más información acerca de la administración de usuarios en entornos de EOP independientes, vea Administrar usuarios [de correo en EOP.](manage-mail-users-in-eop.md)

## <a name="what-messages-can-end-users-access-in-quarantine"></a>¿A qué mensajes pueden acceder los usuarios finales en cuarentena?

Los usuarios pueden acceder a correo no deseado, correo electrónico masivo y mensajes de suplantación de identidad (a partir de abril de 2020) en los que son destinatarios. Los usuarios finales no pueden acceder a malware en cuarentena, suplantación de identidad de alta confianza o mensajes que se han puesto en cuarentena debido a la acción Entregar el mensaje a la cuarentena hospedada en reglas de flujo de correo (también conocidas como reglas de transporte).  Para obtener más información acerca de los usuarios que tienen acceso a mensajes en cuarentena, vea Buscar y liberar mensajes [en cuarentena como un usuario.](find-and-release-quarantined-messages-as-a-user.md)

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>¿Durante cuánto tiempo se mantienen los mensajes en cuarentena?

Puede configurar cuánto tiempo se mantienen en cuarentena los mensajes de correo no deseado, de suplantación de identidad y de correo masivo mediante directivas contra correo no deseado. El valor predeterminado es 30 días, que también es el máximo. Para obtener más información, vea [Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)

Para los mensajes que fueron puestos en cuarentena por la acción de regla de flujo de correo Entregar el mensaje a la cuarentena hospedada, los mensajes se mantienen en cuarentena durante 30 días. No puede configurar esta duración.

Una vez expirado el período de tiempo, los mensajes se eliminan y no se pueden recuperar.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>¿Puedo liberar o informar de más de un mensaje en cuarentena a la vez?

En el Centro de & cumplimiento, puede seleccionar y liberar hasta 100 mensajes a la vez.

Los administradores pueden usar los cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) y [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) en Exchange Online PowerShell o EOP PowerShell independiente para buscar y liberar mensajes en cuarentena de forma masiva y para notificar falsos positivos en masa.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>¿Se admiten caracteres comodín al buscar mensajes en cuarentena? ¿Puedo buscar mensajes en cuarentena para un dominio específico?

Los caracteres comodín no se admiten en el Centro de seguridad & cumplimiento. Por ejemplo, al buscar un remitente, debe especificar la dirección de correo electrónico completa. Pero puede usar caracteres comodín en Exchange Online PowerShell o EOP PowerShell independiente.

Por ejemplo, ejecute el siguiente comando para buscar mensajes de correo no deseado en cuarentena de todos los remitentes del dominio contoso.com:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

A continuación, ejecute el siguiente comando para liberar esos mensajes a todos los destinatarios originales:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

Después de liberar un mensaje, no puede liberarlo de nuevo.
