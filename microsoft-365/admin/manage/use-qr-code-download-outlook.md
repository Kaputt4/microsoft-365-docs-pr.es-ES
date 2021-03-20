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
description: Obtenga información sobre cómo usar un código QR para autenticar y descargar Outlook mobile.
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914971"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="c9d0c-103">Usar un código QR para iniciar sesión en las aplicaciones móviles de Outlook</span><span class="sxs-lookup"><span data-stu-id="c9d0c-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9d0c-104">Esta característica solo está disponible para las organizaciones que han activado La versión dirigida en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-104">This feature is only available to organizations who have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c9d0c-105">Para activar la versión dirigida y obtener más información sobre cómo funciona, vea Configurar las opciones de versión estándar o [dirigida.](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="c9d0c-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="c9d0c-106">Nos expandiremos a más organizaciones en las próximas semanas a través de la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="c9d0c-107">La vista previa pública proporciona acceso anticipado a las características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="c9d0c-108">Como administrador de Microsoft 365, puede permitir que los usuarios inicien sesión en la aplicación de Outlook para Android o iOS en sus dispositivos móviles sin tener que escribir su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="c9d0c-109">Al examinar un código QR, los usuarios pueden autenticar e iniciar sesión de forma segura en Outlook mobile.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="c9d0c-110">En Outlook en la web u otras aplicaciones de escritorio de Outlook, los usuarios pueden ver notificaciones que les informan de que pueden usar Outlook en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="c9d0c-111">El administrador puede administrar estas notificaciones mediante Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="c9d0c-112">Si los usuarios deciden enviarse un mensaje de texto SMS para descargar la aplicación en su dispositivo móvil, aparecerá un código QR en su equipo.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="c9d0c-113">Podrán examinar el código QR para iniciar sesión en Outlook en su teléfono o tableta.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="c9d0c-114">Este código QR es un token de corta duración que solo se puede canjear una vez.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="c9d0c-115">En algunos casos, los usuarios tendrán que volver a autenticarse en su equipo para generar el código QR.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-115">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="c9d0c-116">Usar Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9d0c-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="c9d0c-117">Esta característica está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-117">This feature is on by default.</span></span> <span data-ttu-id="c9d0c-118">Para deshabilitar esta característica, siga los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="c9d0c-119">[Conectarse a Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="c9d0c-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="c9d0c-120">Con PowerShell, puede deshabilitar las notificaciones que informan a los usuarios sobre las aplicaciones móviles de Outlook.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="c9d0c-121">Esto también impedirá que se muestra el flujo de inicio de sesión de código QR.</span><span class="sxs-lookup"><span data-stu-id="c9d0c-121">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="c9d0c-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c9d0c-122">Related topics</span></span>

[<span data-ttu-id="c9d0c-123">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="c9d0c-123">Set-OrganizationConfig</span></span>](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)