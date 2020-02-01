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
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="40c73-103">Desactivar la notificación de correo no deseado para Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="40c73-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="40c73-104">Puede enviar mensajes de correo no deseado, de suplantación de identidad (phishing) y de correo no deseado a Microsoft para su análisis con la opción de informes de correo no deseado de Outlook en la web (anteriormente conocido como Outlook Web App), tal como se describe en [informes de correo no deseado y estafas de suplantación de identidad en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span><span class="sxs-lookup"><span data-stu-id="40c73-104">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web (formerly known as Outlook Web App) junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span> <span data-ttu-id="40c73-105">Si no quiere usar estas opciones, los administradores pueden desactivarlas mediante el cmdlet [set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) .</span><span class="sxs-lookup"><span data-stu-id="40c73-105">If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) cmdlet.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="40c73-106">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="40c73-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="40c73-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="40c73-107"><a name="sectionSection0"> </a></span></span>

- <span data-ttu-id="40c73-108">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="40c73-108">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="40c73-109">Deberá tener permisos asignados para poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="40c73-109">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="40c73-110">Para ver qué permisos necesita, consulte el entrada "directivas de buzones de correo de Outlook en la web" en [permisos de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span><span class="sxs-lookup"><span data-stu-id="40c73-110">To see what permissions you need, see the "Outlook on the web mailbox policies" entry in [Exchange Online permissions](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span></span>

- <span data-ttu-id="40c73-111">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse al PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="40c73-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="40c73-112">Desactivar los informes de correo no deseado, phishing y no deseados en Microsoft</span><span class="sxs-lookup"><span data-stu-id="40c73-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="40c73-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="40c73-113"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="40c73-114">En primer lugar, ejecute el siguiente comando para obtener los nombres de las directivas de buzón de correo de Outlook en la web disponibles:</span><span class="sxs-lookup"><span data-stu-id="40c73-114">First, run the following command to get the names of your available Outlook on the web mailbox policies:</span></span>

```
Get-OwaMailboxPolicy | Format-Table Name
```

<span data-ttu-id="40c73-115">A continuación, use la siguiente sintaxis para habilitar o deshabilitar los informes de correo no deseado y no deseados para Microsoft en Outlook en la web:</span><span class="sxs-lookup"><span data-stu-id="40c73-115">Next, use the following syntax to enable or disable junk and not junk reporting to Microsoft in Outlook on the web:</span></span>

```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

<span data-ttu-id="40c73-116">En este ejemplo se desactiva la creación de informes en la Directiva de buzones de Outlook Web App predeterminada:</span><span class="sxs-lookup"><span data-stu-id="40c73-116">This example turns off reporting in the default Outlook web app mailbox policy:</span></span>

```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

<span data-ttu-id="40c73-117">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) y [set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="40c73-117">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="40c73-118">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="40c73-118">How do you know this worked?</span></span>
<span data-ttu-id="40c73-119"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="40c73-119"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="40c73-120">Ejecute **Get-OWAMailboxPolicy** para comprobar los valores de parámetro y, a continuación, Abra Outlook en la web para un usuario afectado (que tenga aplicada la Directiva de buzón de Outlook en la web) y compruebe que las opciones para informar de correo no deseado, suplantación de identidad y correo electrónico no deseado no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="40c73-120">Run **Get-OWAMailboxPolicy** to check the parameter values, and then open Outlook on the web for an affected user (who has the Outlook on the web mailbox policy applied to them) and verify that the options to report junk, phishing, and not junk are not available.</span></span> <span data-ttu-id="40c73-121">Aún podrá marcar los mensajes como correo no deseado, suplantación de identidad (phishing) y correo deseado, pero no podrá informar sobre ellos.</span><span class="sxs-lookup"><span data-stu-id="40c73-121">You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span>
