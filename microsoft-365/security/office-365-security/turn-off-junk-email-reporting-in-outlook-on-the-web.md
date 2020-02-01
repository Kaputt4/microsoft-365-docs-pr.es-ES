---
title: Desactivar la notificación de correo no deseado para Outlook en la Web
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: Como administrador de Office 365, puede desactivar la posibilidad de que los usuarios notifiquen el correo electrónico como correo no deseado.
ms.openlocfilehash: 0bca03786d0335c24e48340e588510f09d6f6a7e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598127"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>Desactivar la notificación de correo no deseado para Outlook en la Web

Puede enviar mensajes de correo no deseado, de suplantación de identidad (phishing) y de correo no deseado a Microsoft para su análisis con la opción de informes de correo no deseado de Outlook en la web (anteriormente conocido como Outlook Web App), tal como se describe en [informes de correo no deseado y estafas de suplantación de identidad en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Si no quiere usar estas opciones, los administradores pueden desactivarlas mediante el cmdlet [set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) .

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?
<a name="sectionSection0"> </a>

- Tiempo estimado para finalizar: 5 minutos

- Deberá tener permisos asignados para poder llevar a cabo estos procedimientos. Para ver qué permisos necesita, consulte el entrada "directivas de buzones de correo de Outlook en la web" en [permisos de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse al PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>Desactivar los informes de correo no deseado, phishing y no deseados en Microsoft
<a name="sectionSection1"> </a>

En primer lugar, ejecute el siguiente comando para obtener los nombres de las directivas de buzón de correo de Outlook en la web disponibles:

```
Get-OwaMailboxPolicy | Format-Table Name
```

A continuación, use la siguiente sintaxis para habilitar o deshabilitar los informes de correo no deseado y no deseados para Microsoft en Outlook en la web:

```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

En este ejemplo se desactiva la creación de informes en la Directiva de buzones de Outlook Web App predeterminada:

```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) y [set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?
<a name="sectionSection2"> </a>

Ejecute **Get-OWAMailboxPolicy** para comprobar los valores de parámetro y, a continuación, Abra Outlook en la web para un usuario afectado (que tenga aplicada la Directiva de buzón de Outlook en la web) y compruebe que las opciones para informar de correo no deseado, suplantación de identidad y correo electrónico no deseado no están disponibles. Aún podrá marcar los mensajes como correo no deseado, suplantación de identidad (phishing) y correo deseado, pero no podrá informar sobre ellos.
