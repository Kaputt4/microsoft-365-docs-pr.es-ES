---
title: Usar un código QR para iniciar sesión en las aplicaciones móviles de Outlook
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Aprenda a usar un código QR para autenticar y descargar Outlook Mobile.
ms.openlocfilehash: 2d62a49b93fa7bd5f2d747525de7244e8014e6a7
ms.sourcegitcommit: b8e9b2ecdc4927b67088c5fffb1585424c66fb10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50050783"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="034a6-103">Usar un código QR para iniciar sesión en las aplicaciones móviles de Outlook</span><span class="sxs-lookup"><span data-stu-id="034a6-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="034a6-104">Esta característica de Microsoft 365 está en versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="034a6-104">This Microsoft 365 feature is in public preview.</span></span> <span data-ttu-id="034a6-105">La versión preliminar pública proporciona acceso anticipado a las características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="034a6-105">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="034a6-106">Como administrador de Microsoft 365, puede permitir que los usuarios inicien sesión en la aplicación Outlook para Android o iOS en sus dispositivos móviles sin tener que escribir su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="034a6-106">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="034a6-107">Mediante el análisis de un código QR, los usuarios pueden autenticarse e iniciar sesión de forma segura en Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="034a6-107">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="034a6-108">En Outlook en la Web u otras aplicaciones de escritorio de Outlook, los usuarios pueden ver notificaciones que les informan de que pueden usar Outlook en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="034a6-108">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="034a6-109">El administrador puede administrar estas notificaciones mediante Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="034a6-109">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="034a6-110">Si los usuarios deciden enviarse un mensaje de texto SMS para descargar la aplicación en su dispositivo móvil, aparecerá un código QR en su equipo.</span><span class="sxs-lookup"><span data-stu-id="034a6-110">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="034a6-111">Podrán examinar el código QR para iniciar sesión en Outlook en su teléfono o tableta.</span><span class="sxs-lookup"><span data-stu-id="034a6-111">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="034a6-112">Este código QR es un token de corta duración que solo se puede canjear una vez.</span><span class="sxs-lookup"><span data-stu-id="034a6-112">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="034a6-113">En algunos casos, los usuarios tendrán que volver a autenticarse en su equipo para generar el código QR.</span><span class="sxs-lookup"><span data-stu-id="034a6-113">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="034a6-114">Usar Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="034a6-114">Use Exchange PowerShell</span></span>

<span data-ttu-id="034a6-115">Esta experiencia está en modo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="034a6-115">This experience is on by default.</span></span> <span data-ttu-id="034a6-116">Para deshabilitar esta característica, siga los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="034a6-116">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="034a6-117">[Conéctese a Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="034a6-117">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="034a6-118">Con PowerShell, puede deshabilitar las notificaciones que informan a los usuarios sobre las aplicaciones móviles de Outlook.</span><span class="sxs-lookup"><span data-stu-id="034a6-118">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="034a6-119">Esto también impedirá que se muestra el flujo de inicio de sesión del código QR.</span><span class="sxs-lookup"><span data-stu-id="034a6-119">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-Organization -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="034a6-120">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="034a6-120">Related topics</span></span>

[<span data-ttu-id="034a6-121">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="034a6-121">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)