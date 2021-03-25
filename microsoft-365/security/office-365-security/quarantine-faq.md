---
title: Preguntas más frecuentes sobre mensajes en cuarentena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden ver preguntas y respuestas más frecuentes sobre los mensajes en cuarentena en Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 342f6b7f27c99352c4e5906799ce463b658e0c87
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207415"
---
# <a name="quarantined-messages-faq"></a>Preguntas más frecuentes sobre mensajes en cuarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En este tema se proporcionan preguntas y respuestas más frecuentes sobre mensajes de correo electrónico en cuarentena para organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online.

Para obtener preguntas y respuestas sobre la protección contra correo no deseado, consulte Preguntas más frecuentes sobre protección [contra correo no deseado](anti-spam-protection-faq.md).

Para obtener preguntas y respuestas acerca de la protección contra malware, vea Preguntas más frecuentes sobre protección [contra malware.](anti-malware-protection-faq-eop.md)

Para obtener preguntas y respuestas acerca de la protección contra la suplantación, vea Preguntas más frecuentes sobre la protección contra la [suplantación de seguridad](anti-spoofing-protection-faq.md).

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>¿Cómo puedo administrar los mensajes que se han puesto en cuarentena para malware?

Solo los administradores pueden administrar los mensajes que se han puesto en cuarentena para malware. Para obtener más información, vea [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).

## <a name="how-do-i-quarantine-spam"></a>¿Cómo puedo poner en cuarentena el correo no deseado?

De forma predeterminada, los mensajes clasificados como correo no deseado o correo electrónico masivo por filtrado de correo no deseado se entregan al buzón del usuario y se mueven a la carpeta Correo no deseado. Pero puede crear y configurar directivas contra correo no deseado para poner en cuarentena el correo no deseado o los mensajes de correo electrónico masivo en su lugar. Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>¿Cómo puedo dar a los usuarios acceso a la cuarentena?

Un usuario debe tener una cuenta válida para tener acceso a sus propios mensajes en cuarentena. EOP independiente requiere que los usuarios se represente como usuarios de correo en EOP (creados manualmente o creados mediante la sincronización de directorios). Para obtener más información acerca de la administración de usuarios en entornos EOP independientes, vea [Manage mail users in EOP](manage-mail-users-in-eop.md).

## <a name="what-messages-can-end-users-access-in-quarantine"></a>¿A qué mensajes pueden acceder los usuarios finales en cuarentena?

Los usuarios pueden acceder a correo no deseado, correo electrónico masivo y (a partir de abril de 2020) mensajes de suplantación de identidad donde son destinatarios. Los usuarios finales no pueden acceder a malware en cuarentena, phishing de elevada confianza o mensajes que se han puesto en cuarentena debido a la acción Entregar el mensaje a la cuarentena hospedada en reglas de flujo de correo (también conocidas como reglas de transporte).  Para obtener más información acerca de los usuarios que tienen acceso a mensajes en cuarentena, vea Buscar y liberar mensajes [en cuarentena como usuario.](find-and-release-quarantined-messages-as-a-user.md)

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>¿Cuánto tiempo se mantienen los mensajes en cuarentena?

Puede configurar el tiempo que los mensajes de correo no deseado, suplantación de identidad y correo masivo se mantienen en cuarentena mediante directivas contra correo no deseado. El valor predeterminado es 30 días, que también es el máximo. Para obtener más información, vea [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)

Para los mensajes que la acción de regla de flujo de correo ha puesto en cuarentena Entregar el mensaje a la cuarentena hospedada, los mensajes se mantienen en cuarentena durante 30 días. No puede configurar esta duración.

Una vez expirado el período de tiempo, los mensajes se eliminan y no se pueden recuperar.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>¿Puedo liberar o informar de más de un mensaje en cuarentena a la vez?

En el Centro de & cumplimiento, puede seleccionar y liberar hasta 100 mensajes a la vez.

Los administradores pueden usar los cmdlets [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) y [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage) en PowerShell de Exchange Online o PowerShell de EOP independiente para buscar y liberar mensajes en cuarentena en masa e informar de falsos positivos en masa.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>¿Se admiten caracteres comodín al buscar mensajes en cuarentena? ¿Puedo buscar mensajes en cuarentena para un dominio específico?

Los caracteres comodín no se admiten en el Centro de seguridad & cumplimiento. Por ejemplo, al buscar un remitente, debe especificar la dirección de correo electrónico completa. Sin embargo, puede usar caracteres comodín en PowerShell de Exchange Online o en PowerShell de EOP independiente.

Por ejemplo, copie el siguiente código de PowerShell en el Bloc de notas y guarde el archivo como .ps1 en una ubicación que sea fácil de encontrar (por ejemplo, C:\Data\QuarantineRelease.ps1).

A continuación, después de conectarse [a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) o [Exchange Online Protection PowerShell,](/powershell/exchange/connect-to-exchange-online-protection-powershell)ejecute el siguiente comando para ejecutar el script:

```powershell
& C:\Data\QuarantineRelease.ps1
```

El script realiza las siguientes acciones:

- Busque mensajes inéditos que se han puesto en cuarentena como correo no deseado de todos los remitentes del dominio fabrikam. El número máximo de resultados es de 50 000 (50 páginas de 1000 resultados).
- Guarde los resultados en un archivo CSV.
- Libere los mensajes en cuarentena correspondientes a todos los destinatarios originales.

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

Después de liberar un mensaje, no puede volver a liberarlo.