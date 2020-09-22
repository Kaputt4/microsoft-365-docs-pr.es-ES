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
description: Los administradores pueden ver las preguntas más frecuentes y las respuestas sobre los mensajes en cuarentena en Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d52aa8b6d86421bbc03e03191d0e0ccd074ce782
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202464"
---
# <a name="quarantined-messages-faq"></a>Preguntas más frecuentes sobre los mensajes en cuarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En este tema se proporcionan preguntas frecuentes y respuestas sobre los mensajes de correo electrónico en cuarentena para organizaciones de Microsoft 365 con buzones en Exchange online o con organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online.

Para preguntas y respuestas sobre la protección contra correo no deseado, consulte [preguntas más frecuentes sobre protección contra correo no deseado](anti-spam-protection-faq.md).

Para preguntas y respuestas sobre la protección antimalware, consulte [preguntas más frecuentes sobre la protección contra malware](anti-malware-protection-faq-eop.md).

Para obtener preguntas y respuestas sobre la protección contra la suplantación de identidad, vea [preguntas más frecuentes sobre protección contra la suplantación de identidad](anti-spoofing-protection-faq.md).

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>¿Cómo se administran los mensajes que se pusieron en cuarentena para malware?

Solo los administradores pueden administrar los mensajes que se pusieron en cuarentena para obtener malware. Para obtener más información, consulte [Manage Quarantined messages and files as a admin](manage-quarantined-messages-and-files.md).

## <a name="how-do-i-quarantine-spam"></a>¿Cómo puedo poner en cuarentena el correo no deseado?

De forma predeterminada, los mensajes clasificados como correo no deseado o correo masivo por filtrado de correo no deseado se entregan al buzón del usuario y se mueven a la carpeta correo electrónico no deseado. Pero puede crear y configurar directivas contra correo no deseado para poner en cuarentena correo no deseado o mensajes de correo electrónico masivo en su lugar. Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>¿Cómo se concede a los usuarios acceso a la cuarentena?

Un usuario debe tener una cuenta válida para tener acceso a sus propios mensajes en cuarentena. EOP independiente requiere que los usuarios se representen como usuarios de correo en EOP (creados o creados manualmente mediante la sincronización de directorios). Para obtener más información acerca de la administración de usuarios en entornos de EOP independientes, vea [Manage Mail Users in EOP](manage-mail-users-in-eop.md).

## <a name="what-messages-can-end-users-access-in-quarantine"></a>¿Qué mensajes pueden hacer que los usuarios finales tengan acceso en cuarentena?

Los usuarios pueden tener acceso a correo no deseado, correo electrónico masivo y (a partir de abril de 2020) los mensajes de suplantación de identidad en los que son destinatarios. Los usuarios finales no pueden acceder a malware en cuarentena, phishing de alta confianza o mensajes que se pusieron en cuarentena debido **a la entrega del mensaje a la acción de cuarentena hospedada** en reglas de flujo de correo (también conocidas como reglas de transporte). Para obtener más información sobre los usuarios que tienen acceso a los mensajes en cuarentena, vea [Find and Release Quarantined messages as a User](find-and-release-quarantined-messages-as-a-user.md).

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>¿Cuánto tiempo se conservan los mensajes en cuarentena?

Puede configurar el tiempo que se conservan los mensajes de correo electrónico masivo, de suplantación de identidad (phishing) y masivo en cuarentena mediante directivas contra correo no deseado. El valor predeterminado es 30 días, que es también el máximo. Para obtener más información, vea [configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md) .

Para los mensajes puestos en cuarentena por la acción de regla de flujo de correo **Enviar el mensaje a la cuarentena hospedada**, los mensajes se mantienen en cuarentena durante 30 días. No puede configurar esta duración.

Una vez transcurrido el período de tiempo, los mensajes se eliminan y no se pueden recuperar.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>¿Puedo liberar o informar de más de un mensaje en cuarentena a la vez?

En el centro de seguridad & cumplimiento, puede seleccionar y publicar hasta 100 mensajes a la vez.

Los administradores pueden usar los cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) y [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) en Exchange Online PowerShell o el PowerShell independiente de EOP para buscar y liberar mensajes en cuarentena de forma masiva, así como para informar de falsos positivos en masa.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>¿Se admiten caracteres comodín al buscar mensajes en cuarentena? ¿Puedo buscar mensajes en cuarentena para un dominio específico?

No se admiten caracteres comodín en el centro de seguridad & cumplimiento. Por ejemplo, al buscar un remitente, debe especificar la dirección de correo electrónico completa. Pero, puede usar caracteres comodín en Exchange Online PowerShell o en PowerShell de EOP independiente.

Por ejemplo, ejecute el siguiente comando para buscar mensajes de correo no deseado en cuarentena de todos los remitentes en el dominio contoso.com:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

A continuación, ejecute el siguiente comando para liberar los mensajes a todos los destinatarios originales:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

Después de liberar un mensaje, no podrá volver a publicarlo.
